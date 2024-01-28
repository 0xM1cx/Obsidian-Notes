**SQL Injection (SQLi)** is a web security vulnerability that allows an attacker to interfere with the queries that an application makes to its database. This can allow an attacker to view data that they are not normally able to retrieve. This might include data that belongs to other uses, or any data that application can access. In many cases, an attacker can modify or delete this data, causing persistent changes to the application's content or behavior.

In some situations, an attacker can escalate a SQL injection attack to compromise the underlying server or other back-end infrastructure. It can also enable them to perform DOS attacks. 

## How to detect SQLi Vulnerabilities
You can detect SQL injection manually using a systematic set of test against every entry point in the application. To do this, you would typically submit:
- The single quote character `'` and look for errors or other anomalies.
- Some SQL-specific syntax that evaluates to the base (original) value of the entry point, and to a different value, and look for systematic differences in the application responses.
- Boolean conditions such as `OR 1=1` and `OR 1=2`, and look for differences in the application's responses.
- Payloads designed to trigger time delays when executed within a SQL query, and look for differences in the time taken to respond.
- OAST payloads designed to trigger an out-of-band network interaction when executed within a SQL query, and monitor any resulting interactions.

## Retrieving Hidden Data
Imagine a shopping application that displays products in different categories. When the user clicks on the **Gifts** category, their browser requests the URL:
```http
https://insecure-website.com/products?category=Gifts
```
This causes the application to make a SQL query to retrieve details of the relevant products from the database:
```sql
SELECT * FROM products WHERE category = 'Gifts' AND released = 1
```
This query returns all details in the `products` table where the `category` is `Gifts` and `released` is `1`. The `released = 1` is a restriction that is used to hide products that are not release. We could assume for unreleased products, `released = 0`

The app doesn't implement any defenses against SQL injection attacks. This means an attacker can construct the following attack:
```http
https://insecure-website.com/products?category=Gifts'--
```
This results in the SQL query:
```sql
SELECT * FROM products WHERE category = 'Gifts'--' AND released = 1
```
This results in all the products being displayed, including those that are not yet released. 

You can also use a similar attack to cause the application to display all the products in any category, including categories that they don't know about:
```http
https://insecure-website.com/products?category=Gifts'+OR+1=1--
```
This results in the SQL query:
```sql
`SELECT * FROM products WHERE category = 'Gifts' OR 1=1--' AND released = 1`
```
The modified query returns all items where either the `category` is `Gifts`, or `1` is equal to `1`. As `1=1` is always true, the query returns all items.

>**Warning**. Take care when injecting the condition `OR 1=1` into a SQL query. Even if it appears to be harmless in the context you're injecting into, it's common for applications to use data from a single request in multiple different queries. If your condition reaches an `UPDATE` or `DELETE` statement, for example, it can result in an accidental loss of data.

## Subverting application logic
Imagine an application that lets users log in with a username and password. If a user submits the username `wiener` and the password `bluecheese`, the application checks the credentials by performing the following SQL query. 
```sql
SELECT * FROM users WHERE username = 'wiener' AND password = 'bluecheese'
```

If the query returns the details of a user, then the login is successful. Otherwise, it is rejected.

In this case, an attacker can log in as any user without the need for a password. They can do this using the SQL comment sequence `--` to remove the password check from the `WHERE` clause of the query. For example, submitting the username `administrator'--` and a black password results in the following query: 
```sql
SELECT * FROM users WHERE username = 'administrator'--' AND password = ''
```
This query returns the user whose `username` is `administrator` and successfully logs the attacker in as the user. 

## SQL injection UNION attacks
When an application is vulnerable to SQL injection, and the results of the query are returned within the application's responses, you can use the `UNION` keyword to retrieve data from other tables within the database.

The `UNION` keyword enables you to execute one or more additional `SELECT` queries and append the results to the original query. For example:

```sql
SELECT a, b FROM table1 UNION SELECT c, d FROM table2
```

This SQL query returns a single result set with two columns, containing values from columns `a` and `b` in `table1` and columns `c` and `d` in `table2`.

For a `UNION` query to work, two key requirements must be met:
- The individual queries must return the same number of columns.
- The data types in each column must be compatible between the individual queries.

To carry out a SQL injection UNION attack, make sure that your attack meets these two requirements. This normally involves finding out:
- How many columns are being returned from the original query.
- Which columns returned from the original query are of a suitable data type to hold the results from the injected query.

### Determining the number of columns required
There are two effective methods to determine how many  columns are being returned from the original query. 

One method involves injecting a series of `ORDER BY` clauses and incrementing the specified column index until an error occurs. For example, if the injection point is a quoted string within the `WHERE` clause of the original query, you would submit:
```sql
' ORDER BY 1--
' ORDER BY 2--
' ORDER BY 3--
```

This series of payload modifies the original query to order the result by different columns in the result set. The column in an `ORDER BY` clause can be specifies by its index, so you don't need to know the names of any column. When the specified column index exceeds the number of actual columns in the result set, the database returns an error, such as:
```sql
The ORDER BY position number 3 is out of range of the number of items in the selected list.
```
The application might actually return the database error in its HTTP response, but it may also issue a generic error response. In other cases, it may simply return no results at all. Either way, as long as you can detect some difference in the response, you can infer how many column are being returned from the query. 


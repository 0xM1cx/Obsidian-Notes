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
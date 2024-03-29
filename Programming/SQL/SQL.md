```toc
```
## What is SQL
***SQL or Structured Query Language*** is a powerful and standard query language for relational database systems. We use SQL to perform **CRUD(Create, Read, Update, Delete)** operations on databases along with other various operations.

**Database**. Is an organized collection of data so that it can be easily accessed. To manage these databases, ***Database Management Systems(DBMS)*** are used.

*Types of DBMS*
- Non-Relational
- Relational
---
**Non-RDBMS** -> Data is stored in ***key-value pairs***. Example:
![[Pasted image 20220501164749.png]]

Here, customers' data are stored in key-value pairs.
**Commonly used Non-RDBMS:** MongoDB, Amazon DynamoDB, Redis, etc.

**Relational DBMS** -> In RDBMS, data is stored in **tabular format**. For example,
![[Pasted image 20220501165017.png]]
Here, `customers` is a table inside the database.
The first row is the attribute of the table. Each row after that contains the data fo a customer.

In RDBMS, two or more tables may be related to each other. Hence the term "**Relational**" means. For example,
![[Pasted image 20220501165136.png]]
Here, orders and customers are related through `customer_id`.
**Commonly used RDBMS:** <u>MySQL, PostgreSQL, MSSQL, Oracle</u> etc
> NOTE
> To access data from these relational databases, SQL is used.

---
# Introduction to SQL
**Structured Query Language (SQL)** is a standard query language that is used to work with relational databases. SQL is used in all RDBMS such as MySQL, Oracle, MSSQL, PostgreSQL.

We use SQL to:
-   **create databases**
-   **create tables in a database**
-   **read data from a table**
-   **insert data in a table**
-   **update data in a table**
-   **delete data from a table**
-   **delete database tables**
-   **delete databases**
-   **and many more database operations**

Syntax Example
**Read Data From a Table**
```sql
SELECT first_name, last_name FROM Customers;
```
The columns highlighted in ***purple*** are the ones who will be selected.
![[Pasted image 20220501165616.png]]

---

# SQL Select
The SQL `SELECT` statement is used to select (retrieve) data from a database table. For example,
```sql
SELECT first_name, last_name
FROM Customers;
```
![[Pasted image 20220501170019.png]]

## SQL SELECT ALL
To select all columns from a database table, we use the `*` character. For example,
```sql
SELECT * FROM Customers
```
Here, the SQL command selects all columns of the Customers table.
![[Pasted image 20220501170148.png]]

## SQL SELECT WHERE Clause
A `SELECT` statement can have an optional `WHERE` clause. The `WHERE` clause allows us to fetch records from a database table that matches specified condition(s). For example,
```sql
SELECT *
FROM Customers
WHERE last_name = 'Doe';
```
Here, the SQL command selects all customers from the Customers table with last_name **Doe**.![[Pasted image 20220501170404.png]]
> NOTE
> In SQL, we must enclose textual data inside either single or double quotations like `'Doe'`.

## SQL Operators
The `WHERE` clause uses operators to construct conditions. Some of the commonly used operators are:
**Equal to Operator (=)**

```sql
SELECT *
FROM Customers
WHERE first_name = 'John';
```

This SQL command selects all customers from the Customers table having first_name **Joe**.

**Greater than (>)**

```sql
SELECT *
FROM Customers
WHERE age > 25;
```

This SQL command selects all customers from the Customers table having age **greater than 25**.

**AND Operator (AND)**
The SQL `AND` operator selects data if all conditions are `TRUE`

```sql
SELECT *
FROM Customers
WHERE last_name = 'Doe' AND country = 'USA';
```

This SQL command selects all customers from the Customers table having last_name **Doe** and `country` **USA**.

**OR Operator**
The SQL `OR` operator selects data if any one condition is `TRUE`. For example,
``` sql
SELECT first_name, last_name
FROM Customers
WHERE country = 'USA' OR last_name = 'Doe';
```

**NOT Operator**
The SQL `NOT` operator selects data if the given condition is `FALSE`. For example:
```sql 
SELECT first_name, last_name
FROM Customers
WHERE NOT country = 'USA';
```

---
### Combining Multiple Operators
It is also possible to combine multiple `AND`, `OR` and `NOT` operators in an SQL statement. For example,

Let's suppose we want to select customers where the country is either **USA** or **UK**, and the age is **less than 26**.
```sql
SELECT *
FROM Customers
WHERE (country = 'USA' OR country = 'UK') AND age < 26;
```
![[Pasted image 20220502174620.png]]

---
## SELECT DISTINCT
The SQL `SELECT DISTINCT` statement selects unique rows from a database table. For example,
```sql
SELECT DISTINCT country
FROM Customers;
```
Here, the SQL command selects unique countries from the Customers table.
![[Pasted image 20220502174929.png]]

### DISTINCT with COUNT
If we need to count the number of unique rows, we can use the `COUNT()` function with `DISTINCT`.
```sql
SELECT COUNT(DISTINCT country)
FROM Customers;
```
Here, the SQL command returns the count of unique countries.
![[Pasted image 20220502175606.png]]

## SELECT AS
The `AS` keyword is used to give columns or tables a temporary name that can be used to identify that column or table later. For example:
```sql
SELECT first_name AS name
FROM Customers;
```
Here, the SQL command selects the first_name of Customers. However, its column name will be name instead of first_name in the result set.
![[Pasted image 20220502180320.png]]

We can also use aliases with more than one column. For example
```sql
SELECT customer_id AS cid, first_name AS name
FROM Customers;
```
Here, the SQL command selects customer_id as cid and first_name as name.

### SQL AS with Expressions
We can combine data from multiple columns and represent data in a single column using the `CONCAT()` function. For example,
```sql
SELECT CONTACT(first_name, ' ', last_name) AS full_name
FROM Customers;
```
Here, the SQL command selects first_name and last_name. And, the name of the column will be full_name in the result set.
![[Pasted image 20220502180756.png]]

## SELECT TOP
The `SELECT TOP` command is used to select a fixed number of rows from a database. For example,
```sql
SELECT TOP 2 *
FROM Customers;
```
Here, the SQL command selects the first **2** rows from the table.
![[Pasted image 20220502181124.png]]

> **Note**: The `TOP` clause is not supported in all Database Management Systems (DBMS). Different DMBS use different keywords to select a fixed number of rows.

For example,
| **Keyword** | **Database System** |
| --- | --- |
| `TOP` | SQL Server, MS Access |
| `LIMIT` | MySQL, PostgreSQL, SQLite |
| `FETCH FIRST` | Oracle |

## SQL Limit
This keyword is used with **MySQL**, **PostgreSQL**, **SQLite**. This is used if you want to specify the number of rows that will be returned with the `SELECT` statement.

### LIMIT With OFFSET Clause
The `offset` keyword is used to specify starting rows from where to select rows. 
```sql 
SELECT first_name, last_name FROM Customers LIMIT 2 OFFSET 3;
```

In the example above, SQL commands selects 2 rows starting from the fourth row. `OFFSET 3` means the first 3 rows are excluded.

## TOP Clause
The `TOP` keyword is used with **SQL Server** and **MS Access**. This is used to retrieve the data from the top of the table. It retrieves only the first few set of rows from the top of the desired table.
```sql
SELECT TOP 2 first_name, last_name FROM Customers;
```

Here, the SQL command selects `first_name` and `last_name` of the first 2 rows.

## FETCH FIRST Clause
This clause is used with the **ORACLE database system**. It is used as `FETCH FIRST n ROWS ONLY`
```sql
SELECT * FROM Customers
FETCH FIRST 2 ROWS ONLY;
```

Here, the SQL command selects the first 2 rows from the table.

## SQL IN Operator
This is used with the `WHERE` clause to match values in a list.
```sql
SELECT first_name, country
FROM Customers
WHERE country IN ("USA", "UK");
```
Here, the SQL command selects rows if the `country` is either **USA** or **UK**

### IN Operator with Columns
This operator can also be used to select rows in which a certain value exist in the given field.
``` sql
SELECT first_name, country
FROM Customers
WHERE "USA" IN (country);
```

### NOT IN Operator
This operator excludes the rows that matches the value in the list. It returns all the rows except the excluded rows.
```sql
SELECT first_name, country
FROM Customers
WHERE country NOT IN ('UK', 'UAE');
```
In the example above, it selects a specific row if the **UK** or **UAE** is not in the `country` column.

> The **IN** operator is reversed by **NOT** operator. They are basically two operators combined.

### IN Operator with Duplicate Values
The IN operator ignores duplicate values in the list.
```sql
--- Example the commands below
SELECT first_name, country
FROM Customers
WHERE country IN ('USA', 'UK', 'USA');

--- Is equivalent to
SELECT first_name, country
FROM Customers
WHERE country IN ('USA', 'UK');
```

### IN operator with Subquery
A **subquery** is a query that is nested inside a SELECT, INSERT, UPDATE or DELETE statement or inside another subquery.

Suppose we want details of customers who have placed an order. Here's how we can do that using a subquery.
```sql
SELECT customer_id, first_name
FROM Customers
WHERE customer_id IN (
	SELECT customer_id
	FROM Orders
);
```

Here, the query
1. Selects the `customer_id` from `Orders` table
2. Select rows from `Customers` table where `customer_id` is in the result set of subquery.

## SQL Between Operator
This operator is used with the `WHERE` clause to match values in a range.
```sql
SELECT item, amount
FROM Orders
WHERE amount BETWEEN 300 AND 500;
```
This selects all items, amounts that have amounts **BETWEEN** 300 and 500. Including 300 and 500.

### NOT BETWEEN Operator
This operator is used to exclude the rows that match values in the range. It returns all the rows except the excluded rows.
```sql
SELECT item, amount
FROM Orders
WHERE amount NOT BETWEEN 300 AND 500;
```
This selects all item, amount except the rows that have amounts between 300 and 500.

### BETWEEN Operator with Text
This operator also works with text.
```sql
SELECT item, amount
FROM Orders
WHERE item BETWEEN 'I' AND 'L';
```
Here, the command selects all orders where the item names lies between **I** and **L**.

If we need to include all the words that start withe **L** as well we can use `~`. For example,
```sql
SELECT item, amount
FROM Orders
WHERE item BETWEEN 'I' AND 'L~'
```

## SQL IS NULL and IS NOT NULL
`IS NULL` is a condition used to select rows if the specified field is `NULL`. Example, 
```sql
SELECT * FROM Employee
WHERE email IS NULL;
```
The query above selects rows that do not have an email.
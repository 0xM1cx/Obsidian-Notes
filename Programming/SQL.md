### What is SQL
***SQL or Structured Query Language*** is a powerful and standard query language for relational database systems. We use SQL to perfom CRUD(Create, Read, Update, Delete) operations on databases along with other various operations.

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
**1. Equal to Operator (=)**

```sql
SELECT *
FROM Customers
WHERE first_name = 'John';
```

This SQL command selects all customers from the Customers table having first_name **Joe**.

**2. Greater than (>)**

```sql
SELECT *
FROM Customers
WHERE age > 25;
```

This SQL command selects all customers from the Customers table having age **greater than 25**.

**3. AND Operator (AND)**

```sql
SELECT *
FROM Customers
WHERE last_name = 'Doe' AND country = 'USA';
```

This SQL command selects all customers from the Customers table having last_name **Doe** and `country` **USA**.
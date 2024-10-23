# SQL Queries:

This section is made to teach the basic SQL queries and keywords used to extract information from a database. Here we'll review basic SQL queries and learn how to organize output. We'll also use the `Chinook` example database.

---

## Basic SQL Query:

All SQL queries use the essential keywords `SELECT`, and `FROM`. Use these keywords everytime you want to query a database. These keywords help SQL identify what data you need from a database and the table you're returning it from.

As an example, if we wanted to return `customerid`, `city`, and `country` data from the `customers` table of the `Chinook` database we can use the commands:

`SELECT customerid, city, country`

`FROM customers;`

---

## SELECT:

The `SELECT` keyword specifies which columns to return `FROM` the specified table. In the previous example we chose to return the `customerid`, `city, and `country` columns. To indicate we wanted to return multiple columns, we separate the column names with a comma `,`. 

If we wanted to output all columns we can follow `SELECT` with an asterisk `*`

`SELECT *`

NOTE: Use the asterisk `*` argument with caution. The `Chinook` database is relatively small, but when working with large databases and tables the final output may become difficult to understand, and slow to run.

---

## FROM:

The `SELECT` keyword is always followed with the `FROM` keyword. `FROM table_to_query` is the correct syntax. `FROM` is typically written on a new line and always followed with the name of the table we want to query. 

When you want to end the query here we use a semicolon `;` to tell SQL that this is the entire query.

NOTE: Line breaks are not necessary in SQL queries, but are often used to make the query easier to understand. 

`SELECT * FROM customers` would be a perfectly fine query returning all columns from the `customers` table

---

## ORDER BY:

Databases can be very complicated, and this is where other SQL keywords come in handy. `ORDER BY` is an important keyword for organizing the data extracted from a query. 

`ORDER BY` sequences the records returned by a query based on a specified column or columns. By default `ORDER BY` sequences in ascending order. To `ORDER BY` descending order we must use a modifier.

### Sorting in ascending order:

To use the `ORDER BY` keyword, write it at the end of the query and specify a column to base the sort on. As an example we'll create a query that returns the `customerid`, `city`, and `country` columns from the `customers` table, and sorts the records by the `city` column:

`SELECT customerid, city, country

FROM customers

ORDER BY city;`

or

`SELECT customerid, city, country FROM customers ORDER BY city;`

The `ORDER BY` keywords sorts the records based on the column specified after this keyword. By default `ORDER BY` sequences in ascending order. This means:

* if you choose a column containing numeric data, it sorts the output from smallest number first and largest number last.

* if the column contains alphabetic character stings it orders the records starting from the beggining of the alphabet to the end.

### Sorting in descending order:

`ORDER BY` can also be used with the `DESC` keyword to specify that we want a column sorted in descending order:

`SELECT customerid, city, country

FROM customers

ORDER BY city DESC;`

or

`SELECT customerid, city, country FROM customers ORDER BY city DESC;`

Now when we query we'll get cities whose name begin with letters closest to the end of the alphabet first.

### Sorting based on multiple columns:

We can also choose multiple columns to order by. For example, if we wanted to first choose the `country` and then the `city` columns. SQL then sorts the output by `country`, and for rows with the same `country`, it then sorts them based on `city`.

Example query:

`SELECT customerid, city, country

FROM customers

ORDER BY country, city`

or

`SELECT customerid, city, country FROM customers ORDER BY country, city`

---

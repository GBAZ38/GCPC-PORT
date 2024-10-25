# Joining tables when querying databases

Sometimes when we use SQL to query databases it can be useful to join multiple tables. this is useful to gather data from different tables in a database.

For example, if we have two tables, one table for vulnerabilities of specific operating systems and one of machines in a company including operating systems being used, we can combine the lists and determine which machines are vulnerable.

## syntax of joins:

since we're working with two tables, we need to tell SQL what tables we'er picking columns from. The way we do this is to write the name of the table folllowed by the column we'd like seperated by a period (`table.column`).

**ex:**

`employees.employee_id`

returns the `employee_id` column from the `employees` table

## Inner join

![Inner_join_VD](/SCREENSHOTS/Inner_joins.png)

`INNER JOIN` only returns the rows where there is a match, but like other types of joins, it returns all specified columns from all joined tables. For example, if the query joins two tables with `SELECT *`, all columns in both of the tables are returned.

**Note**: If a column exists in both of the tables, it is returned twice when `SELECT *` is used.

If for example if we wanted to get a deeper understanding of the employees accessing our machines from two different tables. We can accomplish this by joining the two tables. **First**: Identify the shared column that we'll use to connect the two tables. To do so we use a **primary key** and the first table to connect to another table where the **foreign key** is. The primary key of the first table will be the foreign key of the second. The primary key is a primary key in the first table because it has a unique value for every row in the first table, and no empty values. We don't have a guarantee that the primary key column in the second table follows the same criteria since it's a foreign key and not a primary key.

**Next**, we'll use a type of join called an **INNER JOIN**. An INNER JOIN returns rows matching on a specified column that exists in more than one table. Tables usually contain many more rows, but to further explain what we mean by INNER JOIN, let's focus on just four rows from the `employees` table and four rows from the `machines` table. We'll also look at just a few columns of each table for this example. Let's say we choose `employee_id` in both tables to perform an INNER JOIN. Let's look at the two rows where there is a match. Both tables have `1188` and `1189` in their respective employee_id columns, so they are considered a match. The results of the join is the two rows that have `1188` and `1189` and all columns from both tables.

### Null

In SQL, `NULL` represents a missing value due to any reason. In the example above, this might be machines that are not assigned to any employee. Now, let's bring this into SQL and do an INNER JOIN on the full tables. Let's imagine we want to join these tables in order to get a list of users and their `office` location that also shows what operating system they use on their machines. `employee_id` is a common column between these tables, and we can use this to join them. But we won't need to show this column in the results. First, let's start with a basic query that indicates we want to select the `username`, `office`, and `operating_system` columns. We want `employees` to be our first or left table, so we'll use that in our `FROM` statement. Now, we write the part of the query that tells SQL to join the `machines` table with the `employees` table:

## JOIN syntax:

`SELECT username, office, operating_system`

`FROM employees`

`INNER JOIN machines ON employees.employee_id = machines.employee_id;`

`INNER JOIN` tells SQL to perform the INNER JOIN. Then, we name the second table we want to combine with the first. This is called the right table. In this case, we want to join `machines` with the `employees` table that was already identified after `FROM`. Lastly, we tell SQL what column to base the join on. In our case, we're using the `employee_id` column. Since we're using two tables, we have to identify the table and follow that with the column name. So, we have `employees.employee_id` And `machines.employee_id`.

The results of our query displays the records that match on the employee_id column. Notice that these records contain columns from both tables, but only the ones we've indicated through our SELECT statement.

## Outer joins

In some situations, we might need all of the entries from one or both of our tables. This is where we need to use outer joins.

There are three types of outer joins: **LEFT JOIN**, **RIGHT JOIN**, and **FULL OUTER JOIN**. Similar to inner joins, outer joins combine two tables together; however, they don't necessarily need a match between columns to return a row. Which rows are returned depends on the type of join.

### LEFT JOIN:

![Left_join_VD](/SCREENSHOTS/Left_joins.png)

`LEFT JOIN` returns all of the records of the first table, but only returns rows of the second table that match on a specified column. Like we did in the previous example, let's examine this type of join by looking at just four rows of two tables with a small number of columns. `Employees` is the left table, or the first table, and `machines` is the right table, or the second table. Let's join on the `employee_id` column. There's a matching value in this column for two of the four records. When we execute the join, SQL returns only these rows with the matching value, all other rows from the left table, and all columns from both tables. Records from the employees table that didn't match but were returned through the `LEFT JOIN` contain `NULL` values in columns that came from the `machines` table. 

### RIGHT JOIN:

![Right_join_VD](/SCREENSHOTS/Right_joins.png)

`RIGHT JOIN` returns all of the records of the second table but only returns rows from the first table that match on a specified column. With a `RIGHT JOIN` on the previous example, the full result returns matching rows from both, all the rows from the second table, and all the columns in both tables. For the values that don't exist in either table, we are left with a `NULL` value. 

### FULL OUTER JOIN:

![Full_outer_join_VD](/SCREENSHOTS/Full_outer_joins.png)

`FULL OUTER JOIN` returns all records from both tables. Using our same example, a `FULL OUTER JOIN` returns all columns from all tables. If a row doesn't have a value for a particular column, it returns NULL. For example, the `machines` table do not have any rows with `employee_id 1190`, so the values for that row and the columns that came from the machines table is `NULL`. 

---

EZPZ

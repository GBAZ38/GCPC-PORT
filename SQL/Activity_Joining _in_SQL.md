## Activity overview:

As a security analyst, you’ll often find that you need data from more than one table.

A **relational database** is a structured database containing tables that are related to each other.

**SQL joins** enable you to combine tables that contain a shared column. This is helpful when you need to connect information that appears in different tables.

In this lab activity, we use SQL joins to connect separate tables and retrieve needed information.

---

## Scenario:

In this scenario, you’ll investigate a recent security incident that compromised some machines.

You are responsible for getting the required information from the database for the investigation.

Here’s how you’ll do this task: **First**, you’ll use an inner join to identify which employees are using which machines. **Second**, you’ll use left and right joins to find machines that do not belong to any specific user and users who do not have any specific machine assigned to them. **Finally**, you’ll use an inner join to list all login attempts made by all employees.

---

# Task 1. Match employees to their machines:

First, you must identify which employees are using which machines. The data is located in the `machines` and `employees` tables.

You must use a SQL inner join to return the records you need based on a connecting column. In the scenario, both tables include the `device_id` column, which you’ll use to perform the join.

1. Run the following query to retrieve all records from the `machines` table:

`SELECT *`

`FROM machines;`

You’ll note that this query is not sufficient to perform the join and retrieve the information you need.

2. Complete the query to perform an inner join between the `machines` and `employees` tables on the `device_id` column.

`SELECT *`

`FROM machines`

`INNER JOIN employees ON machines.device_id = employees.device_id;`

# Task 2. Return more data:

You now must return the information on all machines and the employees who have machines. Next, you must do the reverse and retrieve the information of all employees and any machines that are assigned to them.

To achieve this, you’ll complete a left join and a right join on the `employees` and `machines` tables. The results will include all records from one or the other table. You must link these tables using the common `device_id` column.

1. Run the following SQL query to connect the `machines` and `employees` tables through a left join: 

`SELECT *`

`FROM machines`

`LEFT JOIN employees ON machines.device_id = employees.device_id;`

2. Run the following SQL query to connect the machines and employees tables through a right join:

`SELECT *`

`FROM machines`

`RIGHT JOIN employees ON machines.device_id = employees.device_id;`

# Task 3. Retrieve login attempt data:

To continue investigating the security incident, you must retrieve the information on all employees who have made login attempts. To achieve this, you’ll perform an inner join on the `employees` and `log_in_attempts` tables, linking them on the common `username` column.

* Run the following SQL query to perform an inner join on the `employees` and `log_in_attempts` tables.

`SELECT *`

`FROM employees`

`INNER JOIN log_in_attempts ON employees.username = log_in_attempts.username;`

---
EZPZ

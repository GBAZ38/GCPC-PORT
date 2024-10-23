## Activity overview:

As a security analyst, knowing how to make better queries to retrieve specific pieces of data can help you find the security-related information you need more efficiently.

In this lab activity, you’ll apply basic filters to SQL queries to retrieve information from a MariaDB database.

MariaDB is a popular open source relational database that is compatible with MySQL.

This activity provides you with a great opportunity to apply what you’ve learned and add filters to SQL queries.

---

## Scenario:

In this scenario, you need to get specific information about employees, their machines, and the departments they’re in. Your team needs this data to perform various tasks, such as running updates, posting a privacy notice in certain departments, and sending an alert to an employee with an issue on a machine.

You are responsible for finding the required information by querying a database. You’ll add filters to your queries to locate the information more quickly.

Here’s how you’ll do this task: First, you’ll list all organization machines and their operating systems. Second, you’ll list all machines with the operating system OS 2. Third, you’ll list all the employees in the Finance and Sales departments. Fourth, you’ll obtain information about machines.

---

# Task 1. List all organization machines:

In this task, you need to get a list of all organization machines and their operating systems. The data is contained in the `machines` table. You’ll need to use the `SELECT` keyword to return specific columns.

* Run a SQL query to retrieve only the `device_id` and `operating_system` columns from the `machines` table.

`SELECT device_id, operating_system`

`FROM machines;`

---

# Task 2. Retrieve a list of the machines with OS 2:

In this task, you need to obtain a list of all machines with the `'OS 2'` operating system because these machines need an update. To get this information, you’ll run your first SQL query with a filter.

* Select all the records from the `machines` table with a value of `'OS 2'` in the `operating_system` column. 

`SELECT device_id, operating_system`

`FROM machines`

`WHERE operating_system = 'OS 2';`

---

# Task 3. List employees in specific departments:

In this task, you need to retrieve a list of all the employees in the Finance and Sales departments to obtain their office numbers. A notice about handling confidential financial information will be posted to these offices.

* Filter the rows returned from `department` column in the `employees` table to include only employees from the `'Finance'` department.

`SELECT *`

`FROM employees`

`WHERE department = 'Finance'`

* Modify the previous query so that it returns employees who are in the 'Sales' department.

`SELECT *`

`FROM employees`

`WHERE department = 'Sales'`

---

# Task 4. Identify employee machines:

Your team recently discovered that there are issues with machines in the South building. In this task, you need to obtain certain employee and computer information.

A machine in `'South-109'` has an issue. You need to determine which employee uses that computer so you can send them an alert.

* Write a query to identify which employee uses the office in `'South-109'`. (The data must be returned from the `office` column in the `employees` table.)

`SELECT office, username`

`FROM employees`

`WHERE office = 'South-109';`

Next, your team has determined that there is an issue with all the machines in the South building. Offices in the organization are named with the building name, a hyphen, and the office number in that building (for example, `'South-109'`).


* Modify the query you used in the previous step so that it returns information on all the employees in the `'South'` building. Use the `LIKE` operator with `%` in this query.

`SELECT *`

`FROM employees`

`WHERE office LIKE 'South%';`

---

EZPZ

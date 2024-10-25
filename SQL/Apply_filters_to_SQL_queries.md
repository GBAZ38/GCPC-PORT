# Activity Overview

This document is meant to showcase my experience using SQL. This document is meant to prove my skills to potential employers or recruitors. This document is connected to the [Activity_Filter_with_AND_OR_and_NOT.md](https://github.com/GBAZ38/GCPC-PORT/blob/main/SQL/Activity_Filter_with_AND_OR_and_NOT.MD) lab I completed through the Google Cybersecurity Professional course. Here I will explain the queries I performed in hopes to clarify, and elaborate.

---

## Scenario

You are a security professional at a large organization. Part of your job is to investigate security issues to help keep the system secure. You recently discovered some potential security issues that involve login attempts and employee machines.

Your task is to examine the organization’s data in their **employees** and **log_in_attempts** tables. You’ll need to use SQL filters to retrieve records from different datasets and investigate the potential security issues.

**Note:** This scenario involves the same queries as the ones the [Activity_Filter_with_AND_OR_and_NOT.md](https://github.com/GBAZ38/GCPC-PORT/blob/main/SQL/Activity_Filter_with_AND_OR_and_NOT.MD) lab. 

---

## Table Formats:

The `organization` database contains the following two tables: 

* `log_in_attempts`

* `employees`

### log_in_attempts:

The `log_in_attempts` table has the following columns:

* `event_id`: The identification number assigned to each login event

* `username`: The username of the employee

* `login_date`: The date the login attempt was recorded

* `login_time`: The time the login attempt was recorded

* `country`: The country where the login attempt occurred

* `ip_address`: The IP address of that employee’s machine

* `success`: The success of the login attempt; FALSE indicates a failed attempt

In the MariaDB shell, these columns are returned as:

![MariaDB_Columns1](/SCREENSHOTS/MariaDB1.png)

### employees:

The `employees` table has the following columns:

* `employee_id`: The identification number assigned to each employee

* `device_id`: The identification number assigned to each device used by the employee

* `username`: The username of the employee

* `department`: The department the employee is in

* `office`: The office the employee is located in

In the MariaDB shell, these columns are returned as:

![MariaDB_Columns2](/SCREENSHOTS/MariaDB2.png)

---

## Retrieve after hours failed login attempts:

You recently discovered a potential security incident that occurred after business hours. To investigate this, you need to query the **log_in_attempts** table and review after hours login activity. Use filters in SQL to create a query that identifies all failed login attempts that occurred after 18:00.

To query the **log_in_attempts** table on review after hours login attempts we first need to define after hours. In this scenario after hours is considered to be after 18:00. So we'll begin by querying all columns from the **log_in_attempts** table. We can then use the `WHERE` keyword along with the greater than (`>`) operator to only return login attempts that occured after 18:00. On the same line we also use the `AND` keyword to specify our secondary condition, that the login attempt failed, using the equals (`=`) operator. Our finished SQL query resembles:

`SELECT *`

`FROM log_in_attempts`

`WHERE login_time > '18:00:00' AND success = 0;`

---

## Retrieve login attempts on specific dates:

A suspicious event occurred on 2022-05-09. To investigate this event, you want to review all login attempts which occurred on this day and the day before. Use filters in SQL to create a query that identifies all login attempts that occurred on 2022-05-09 or 2022-05-08. 

We want to retrieve all login attempts that occurred on `'2022-05-09'` and `'2022-05-08'`. The `login_date` column in the `log_in_attempts` table contains information on the dates when login attempts were made. We fist query to return all columns in the `log_in_attempts` table. Again we use the keyword `WHERE` to specify that our query should only return logins occuring on the date of 2022-05-09. We follow this with the `OR` operator to also return any login attempts made on 2022-05-08. our final SQL query looks like:

`SELECT *`

`FROM log_in_attempts`

`WHERE login_date = '2022-05-09' OR login_date = '2022-05-08';`

---

## Retrieve login attempts outside of Mexico:

There’s been suspicious activity with login attempts, but the team has determined that this activity didn't originate in Mexico. Now, you need to investigate login attempts that occurred outside of Mexico. Use filters in SQL to create a query that identifies all login attempts that occurred outside of Mexico. 

To query SQL for login attempts made outside of the country of Mexico we need to query the `log_in_attempts` table again. We use the `NOT` operator to specify that we only want our results to contain countries which are not Mexico or Mex. Using the `LIKE` operator we are able to specify the string data we do not want returned. We also use the percentage sign (`%`) operator to ensure we exclude results that contain either string data of Mex or Mexico. The final query is:

`SELECT *`

`FROM log_in_attempts`

`WHERE NOT country LIKE 'MEX%';`

---

## Retrieve employees in Marketing:

Your team wants to perform security updates on specific employee machines in the Marketing department. You’re responsible for getting information on these employee machines and will need to query the **employees** table. Use filters in SQL to create a query that identifies all employees in the Marketing department for all offices in the East building.

To filter for employees located in the east building we use the `LIKE` keyword again. We also use the `AND` keyword to specify that we'd like to filter using multiple conditions. We again use the percentage sign (`%`) operator to ensure we return all offices in the east building.

`SELECT *`

`FROM employees`

`WHERE department = 'marketing' AND office LIKE 'East%';`

---

## Retrieve employees in Finance or Sales:

Your team now needs to perform a different security update on machines for employees in the Sales and Finance departments. Use filters in SQL to create a query that identifies all employees in the Sales or Finance departments.

To query for all sales and finance department employees we use the equals (`=`) and the `OR` operators to ensure our query only returns data whose department is either finance or sales.

`SELECT *`

`FROM employees`

`WHERE department = 'finance' OR department = 'sales';`

---

## Retrieve all employees not in IT:

Your team needs to make one more update to employee machines. The employees who are in the Information Technology department already had this update, but employees in all other departments need it. Use filters in SQL to create a query which identifies all employees not in the IT department.

To ensure our query only returns data that does not contain the information technology department we use the `NOT` and equals (`=`) operators

`SELECT *`

`FROM employees`

`WHERE NOT department = 'information technology';`

---

# Summary:

This document contains examples of SQL queries that filter for specific data. Specifically this document showcases the use of the `AND`, `OR`, and `NOT` operators along with some other basic operators and keywords. 

# Task 1. Retrieve employee device data:

In this task, you need to obtain information on employee devices because your team needs to update them. The information you need is in the machines table in the `organization` database.

## First:

We need to retrieve all the information about the employee devices.

* Run the following query to select all device information from the machines table:

`SELECT *`

`FROM machines;`

The output returns all the contents of the `machines` table

## Next:

We want to focus of the email client running on various devices.

* Run the following query to select only the `device_id` and `email_client` columns from the `machines` table. Replace `X` with `device_id` and `Y` with `email_client`:

`SELECT X, Y FROM machines;`

(carefull not to accidently exit the database query by messing up and hitting ctrl + c)

## Now:

We need information on the operating systems used on various devices and their last patch date.

* Complete the query to return only the `device_id`, `operating_system`, and `OS_patch_date` columns from the `machines` table. Replace `X`, `Y`, and `Z` with the columns that you need to return:

`SELECT X, Y, Z FROM machines;`

---

# Task 2. Investigate login activity:

In this task, you need to analyze the information from the `log_in_attempts` table to determine if any unusual activity has occurred.

## First

We nee to investigate the locations where login attempts were made to ensure that they’re in expected areas (the United States, Canada, or Mexico).

* Write a SQL query to select the `event_id` and `country` columns from the `log_in_attempts` table.

`SELECT event_id, country FROM log_in_attempts;`

## Next:

We need to check if login attempts were made outside of the organization's working hours.

* Write a SQL query that selects the `username`, `login_date`, and `login_time` columns from the `log_in_attempts` table.

`SELECT username, login_date, login_time FROM log_in_attempts;`

## Now

We need to get a complete picture of all login attempts.

* Write a SQL query that selects all columns from the `log_in_attempts` table, using a single symbol after the SELECT keyword.

`SELECT * FROM log_in_attempts;`

---

# Task 3. Order login attempts data:

In this task, you need to use the `ORDER BY` keyword. You'll sequence the data that your query returns according to the login date and time.

## First:

We need to sort the information by date.

* Run the following query, which orders `log_in_attempts` data by `login_date`:

`SELECT *`

`FROM log_in_attempts`

`ORDER BY login_date;`

## Now;

We need to further organize the previous results by ordering them by `login_time`.

* Modify the query from the previous step by adding the login time to the `ORDER BY` clause. You must replace `X` with the appropriate column name:

`SELECT *`

`FROM log_in_attempts`

`ORDER BY login_date, X;`

`SELECT *`

`FROM log_in_attempts`

`ORDER BY login_date, login_time;`

---

EZPZ

# Operators_for_filtering_dates_and_numbers:

There are three common datatypes we find in data bases: 
* string 
- numeric 
* date and time

String data is data consisting of an ordered sequence of characters. These strings can consist of letters, numbers, or symbols

Numeric data is data consisting of numbers. unlike strings we can use mathamatical operations on numeric data such as multiplication, addition, subtraction, or division.

Date and time data is data that represents a date and/or time.

We previously filtered string data in [The_WHERE_clause_and_basic_operators](https://github.com/GBAZ38/GCPC-PORT/blob/main/SQL/The_WHERE_clause_and_basic_operators.MD "My notes on filtering string data"). Now we'll work with numeric and date and time data.

For example we could filter patch dates to find machines that need an update, or we could filter login attempts to those made within a specific date and time

---

## Operators:

These are some of the common operators we can use when filtering for date and time and numeric data types:

* `=` Equals

* `>` Greater than

* `<` Less than

* `<>` Not equal to

* `>=` Greater than or equal to

* `<=` Less than or equal to

For example if we want to find login attempts made after 6pm, you can identify these attempts by using the greater than operator in SQL

`SELECT *`

`FROM log_in_attempts`

`where time > '18:00';`

This returns a list of login attempts made after 6pm.

---

## BETWEEN:

We can also filter for numbers and dates by uising the `BETWEEN` operator. `Between` is an operator that filters for numbers or dates within a range. an example of this would be looking for all patches installed within a certain range. If we wanted to search for patches installed between March 1st 2021 to September 1st 2021.

`SELECT *`

`FROM machines`

`WHERE OS_patch_date BETWEEN '2021-03-01' AND '2021-09-01';`

This outputs a list of all machines patched between those two dates.

---

**Important note:** To filter for strings, dates, and times we use quotation marks (`'`) to specify what we're looking for. When searching and filtering number we do not use quotation marks(`'`).

---

## Numbers, dates, and times in cybersecurity

Security analysts work with more than just **string data**, or data consisting of an ordered sequence of characters. 

They also frequently work with **numeric data**, or data consisting of numbers. A few examples of numeric data that you might encounter in your work as a security analyst include:

* the number of login attempts

* the count of a specific type of log entry

* the volume of data being sent from a source

* the volume of data being sent to a destination

You'll also encounter **date and time data**, or data representing a date and/or time. As a first example, logs will generally timestamp every record. Other time and date data might include:

* login dates

* login times

* dates for patches 

* the duration of a connection

---

## Comparison operators:

In SQL, filtering numeric and date and time data often involves operators. You can use the following operators in your filters to make sure you return only the rows you need:

![Operators/Use table](/SCREENSHOTS/Operator_use_table.png)

**Note:** You can also use `!=` as an alternitive operator for not equal to.

---

## Incorporating operators into filters:

These comparison operators are used in the `WHERE` clause at the end of a query. The following query uses the `>` operator to filter the `birthdate` column:

`SELECT firstname, lastname, birthdate`

`FROM employees`

`WHERE birthrate > '1970-01-01';`

This query returns the first and last names of employees born after, but not on, `'1970-01-01'` (or January 1, 1970). If you were to use the `>=` operator instead, the results would also include results on exactly `'1970-01-01'`.

In other words, the `>` operator is exclusive and the `>=` operator is inclusive.  An **exclusive operator** is an operator that does not include the value of comparison. An **inclusive operator** is an operator that includes the value of comparison. 

## BETWEEN:

Another operator used for numeric data as well as date and time data is the `BETWEEN` operator. `BETWEEN` filters for numbers or dates within a range. For example, if you want to find the first and last names of all employees hired between January 1, 2002 and January 1, 2003, you can use the `BETWEEN` operator as follows:

`SELECT firstname, lastname, hiredate`

`FROM employees`

`WHERE hiredate BETWEEN '2002-01-01' AND '2003-01-01';`

**Note:** The `BETWEEN` operator is inclusive. This means records with a `hiredate` of January 1, 2002 or January 1, 2003 are included in the results of the previous query.

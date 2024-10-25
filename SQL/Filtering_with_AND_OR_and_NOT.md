# Filtering with AND, OR, and NOT operators:
When working with real security questions we often have to filter for multiple conditions. vulnerabilities often depend on more than one factor. a specific vulnerability may affect a specific OS and email client. 

To find the possible vulnerabilities we need to find machines using both the specific email clirnt and OS

---

# AND operator:

We can make a query with multiple conditions that must be met by using the 'AND' operator between two separate conditions. 

'AND' is an operator that specifies that both conditions must be met simultaneously. In order to be included the data must meet both conditions. 

We can use SQL to find the machines that meet our criteria. The example provided requires us to find machines that have both a specific OS and email client. 

'SELECT *'

'FROM machines'

'WHERE OS = 'OS1' AND email_client = 'email_client1';'

---

# OR operator:

The OR operator specifies that either condition can be met. This means that as long as one of the specified conditions are met, the data will be included in the response to our request.

To use the OR operator to filter machines that have either OS1 or OS3, we can use this SQL statement:

'SELECT *'

'FROM machjnes'

'WHERE OS = 'OS1' OR OS = 'OS3';'

Executing this query should return machines with either ''OS1'' or ''OS2'' as their OS value. 

---

# NOT

The 'NOT' operator negates a condition. Essentially it selects every condition that is not our condition. For example if we wanted SQL to return all devices except the ones that are using ''OS3'', we can use the following query:

'SELECT *'

'FROM machines'

'WHERE OS NOT OS3''

We place NOT after WHERE and before the condition of the filter. Executing this query gives us a list of machines that aren't running 'OS3', and now we know which machines we need to update. 

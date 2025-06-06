# Scenario
You are a security professional at a large organization. Part of your job is to investigate security issues to help keep the system secure. You recently discovered some potential security issues that involve login attempts and employee machines.

Your task is to examine the organization’s data in their `employees` and `log_in_attempts` tables. You’ll need to use SQL filters to retrieve records from different datasets and investigate the potential security issues.

# Project Description
I will be using SQL filters to filter through the organization's database to investigate some suspicious activities. I would need to specifically obtain information about employees such as their assigned computers, and their assigned departments. I will have to complete the following tasks:

1. Retrieve all failed login attempts after business hours.
2. Retrieve all login attempts that occured on specific dates.
3. Retrieve logins that didn't originate in Mexico.
4. Retrieve information about certain employees in the Marketing department.
5. Retrieve information about employees in the Finance or the Sales department.
6. Retrieve information about employees who are not in the Information Technology department.

# Retrieve after hours failed login attempts
So there was a potential security incident that occured after business hours, therefore I would need to query the `log_in_attempts` table for failed login attempts after '18:00'. I will run the following SQL query:
```
SELECT * FROM log_in_attempts WHERE login_time > '18:00' AND success = 0;
```
This will yield me the following table:

![](Images/C4M4/Screenshot%2025-06-01%163811.png)

Note that the `success` value being '0' means `FALSE`; this indicates that the login attempt was unsuccessful. It seems there were 19 failed login attempts being made after business hours.

# Retrieve login attempts on specifc dates
A suspicious event occurred on 2022-05-09. To investigate this event, I want to review all login attempts which occurred on this day and the day before. I will need to run the following SQL query:
```
SELECT * FROM log_in_attempts WHERE login_date = '2022-05-08' OR login_date = '2022-05-09';
```
This query yields this large table:

![](Images/C4M4/Screenshot%2025-06-01%164230.png)

Looks like there were 75 login attempts in these two specific days.

# Retrieve login attempts outside of Mexico
There’s been suspicious activity with login attempts, but the team has determined that this activity didn't originate in Mexico. Now, I need to investigate login attempts that occurred outside of Mexico. I will run this query:
```
SELECT * FROM log_in_attempts WHERE NOT country LIKE 'MEX%';
```
Which gives me:

![](Images/C4M4/Screenshot%2025-06-01%164606.png)

In this query, I had to use the '`%`' symbol next to '`MEX`' as a wildcard because the table in the `country` column has both `MEX` and `MEXICO` values. The `LIKE` operator allows me to search for certain values that has patterns that match what I am describing (doesn't necessarily have to be the exact value). Using the `%` symbol and the `LIKE` operator will return any strings with just `MEX` or additional characters after `MEX` (basically any string so as long as the string starts with 'MEX'). We can see that there were 144 login attempts made outside of Mexico.

# Retrieve employees in Marketing
My team wants to perform security updates on specific employee machines in the Marketing department. I'm responsible for getting information on these employee machines and will need to query the `employees` table. The query I must run will be similar to the previous query where I have to use the wildcard symbol '`%`' again:
```
SELECT * FROM employees WHERE department = 'Marketing' AND office LIKE 'East%';
```
Which gives me this table:

![](Images/C4M4/Screenshot%2025-06-01%165126.png)

We can see that there are different offices in the East building, therefore to retrieve all the East building offices, I would need to use the '`%`' symbol after `East`. I also needed to use an `AND` operator because I needed employees that are both in the Marketing department AND have offices in the East building.

# Retrieve employees in Finance or Sales
My team now needs to perform a different security update on machines for employees in the `Sales` and `Finance` departments. The query will be similar to the last one:
```
SELECT * FROM employees WHERE department = 'Finance' OR department = 'Sales';
```
Which gives me:

![](Images/C4M4/Screenshot%2025-06-01%165431.png)

Here I used the `OR` operator because employees can't both be in the Finance department and the Sales department. So to return employees from either department, I would need an `OR` operator.

# Retrieve all employees not in IT
My team needs to make one more update to employee machines. The employees who are in the Information Technology department already had this update, but employees in all other departments need it.

```
SELECT * FROM employees WHERE NOT department = 'Information Technology';
```
Which gives us this long table:

![](Images/C4M4/Screenshot%2025-06-01%165750.png)

Here I had to use the `NOT` operator to make it easier for me. If I didn't use the `NOT` operator, I would have to list and type out all the departments in the organization except the IT department -- this would be a waste of time. The `NOT` operator allows me so select all departments at once except the IT department.

# Summary
In this project, I applied filters and used operators in the SQL queries to get the desired information on login attempts and employee machines. There were two tables being used here, one being `log_in_attempts` to find suspicious activity, and the other being `employees` to find machines that needed updating. The filters and operators I used here include the `AND`, `OR`, `NOT` (to filter for the specific information needed), `LIKE` and the percent sign (`%`) (to filter for patterns).
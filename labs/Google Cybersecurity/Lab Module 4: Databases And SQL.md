# Lab Module 4: Databases And SQL

This lab covers querying, filtering, and joining data from a database using MariaDB SQL. It provides practical experience in retrieving and analyzing information for security purposes.

---

## Table of Contents
1. [Activity 1: Perform a SQL query](#activity-1-perform-a-sql-query)
2. [Activity 2: Filter a SQL query](#activity-2-filter-a-sql-query)
3. [Activity 3: Apply more filters in SQL](#activity-3-apply-more-filters-in-sql)
4. [Activity 4: Filter with AND, OR, and NOT](#activity-4-filter-with-and-or-and-not)
5. [Activity 5: Complete a join](#activity-5-complete-a-join)
6. [Reflection and Conclusion](#reflection-and-conclusion)

---

## Activity 1: Perform a SQL query

**Objectives:**
- Return information on employee devices
- Examine login attempts
- Sort the data returned from a query

**Scenario:**  
Determine which employee devices must be updated and investigate user login activity for unusual events. Data is in the `machines` and `log_in_attempts` tables.

**Sample Tables:**

### `machines` table

| device_id | email_client | operating_system | OS_patch_date |
|-----------|--------------|----------------|---------------|
| 101       | Outlook      | OS 1           | 2023-01-10    |
| 102       | Gmail        | OS 2           | 2022-12-15    |
| 103       | Thunderbird  | OS 2           | 2022-12-20    |
| 104       | Outlook      | OS 3           | 2023-02-01    |

### `log_in_attempts` table

| event_id | username   | login_date | login_time | country | success |
|----------|-----------|------------|------------|---------|--------|
| 1        | alice     | 2022-05-08 | 09:00:00   | USA     | 1      |
| 2        | bob       | 2022-05-09 | 18:30:00   | CAN     | 0      |
| 3        | charlie   | 2022-05-10 | 06:30:00   | MEX     | 1      |
| 4        | diana     | 2022-05-11 | 20:15:00   | USA     | 0      |

**Tasks and SQL Queries:**

1. Retrieve all information about employee devices:
```sql
SELECT * FROM machines;
```
| device_id | email_client | operating_system | OS_patch_date |
| --------- | ------------ | ---------------- | ------------- |
| 101       | Outlook      | OS 1             | 2023-01-10    |
| 102       | Gmail        | OS 2             | 2022-12-15    |
| 103       | Thunderbird  | OS 2             | 2022-12-20    |
| 104       | Outlook      | OS 3             | 2023-02-01    |



2. Select only the device_id and email_client columns:
```sql
SELECT device_id, email_client FROM machines;
```
| device_id | email_client |
| --------- | ------------ |
| 101       | Outlook      |
| 102       | Gmail        |
| 103       | Thunderbird  |
| 104       | Outlook      |



3. Select device_id, operating_system, and OS_patch_date columns:
```sql
SELECT device_id, operating_system, OS_patch_date FROM machines;
```
| device_id | operating_system | OS_patch_date |
| --------- | ---------------- | ------------- |
| 101       | OS 1             | 2023-01-10    |
| 102       | OS 2             | 2022-12-15    |
| 103       | OS 2             | 2022-12-20    |
| 104       | OS 3             | 2023-02-01    |



4. Investigate login attempts by location:
```sql
SELECT event_id, country FROM log_in_attempts;
```
| event_id | country |
| -------- | ------- |
| 1        | USA     |
| 2        | CAN     |
| 3        | MEX     |
| 4        | USA     |



5. Check login attempts outside working hours:
```sql
SELECT username, login_date, login_time FROM log_in_attempts;
```
| username | login_date | login_time |
| -------- | ---------- | ---------- |
| alice    | 2022-05-08 | 09:00:00   |
| bob      | 2022-05-09 | 18:30:00   |
| charlie  | 2022-05-10 | 06:30:00   |
| diana    | 2022-05-11 | 20:15:00   |



6. Select all login attempts:
```sql
SELECT * FROM log_in_attempts;
```
| event_id | username | login_date | login_time | country | success |
| -------- | -------- | ---------- | ---------- | ------- | ------- |
| 1        | alice    | 2022-05-08 | 09:00:00   | USA     | 1       |
| 2        | bob      | 2022-05-09 | 18:30:00   | CAN     | 0       |
| 3        | charlie  | 2022-05-10 | 06:30:00   | MEX     | 1       |
| 4        | diana    | 2022-05-11 | 20:15:00   | USA     | 0       |



7. Order login attempts by date:
```sql
SELECT *
FROM log_in_attempts
ORDER BY login_date;
```
| event_id | username | login_date | login_time | country | success |
| -------- | -------- | ---------- | ---------- | ------- | ------- |
| 1        | alice    | 2022-05-08 | 09:00:00   | USA     | 1       |
| 2        | bob      | 2022-05-09 | 18:30:00   | CAN     | 0       |
| 3        | charlie  | 2022-05-10 | 06:30:00   | MEX     | 1       |
| 4        | diana    | 2022-05-11 | 20:15:00   | USA     | 0       |



8. Order login attempts by date and time:
```sql
SELECT *
FROM log_in_attempts
ORDER BY login_date, login_time;
```
| event_id | username | login_date | login_time | country | success |
| -------- | -------- | ---------- | ---------- | ------- | ------- |
| 1        | alice    | 2022-05-08 | 09:00:00   | USA     | 1       |
| 2        | bob      | 2022-05-09 | 18:30:00   | CAN     | 0       |
| 3        | charlie  | 2022-05-10 | 06:30:00   | MEX     | 1       |
| 4        | diana    | 2022-05-11 | 20:15:00   | USA     | 0       |



---
## Activity 2: Filter a SQL query

**Objectives:**
- Apply filters to SQL queries
- Retrieve information about employees, machines, and departments

**Scenario:** Retrieve specific information about employees, their machines, and departments using filters in SQL.  

**Sample Tables:**

### `machines` table

| device_id | operating_system |
|-----------|----------------|
| 101       | OS 1           |
| 102       | OS 2           |
| 103       | OS 2           |
| 104       | OS 3           |

### `employees` table

| employee_id | name   | department | office   | device_id |
|-------------|--------|-----------|----------|-----------|
| 1           | Alice  | Finance   | North-101 | 101       |
| 2           | Bob    | Sales     | South-109 | 102       |
| 3           | Charlie| Marketing | East-170 | 103       |
| 4           | Diana  | IT        | West-220 | 104       |

**Tasks and SQL Queries:**
1. Retrieve device_id and operating_system columns:
```sql
SELECT device_id, operating_system FROM machines;
```
| device_id | operating_system |
| --------- | ---------------- |
| 101       | OS 1             |
| 102       | OS 2             |
| 103       | OS 2             |
| 104       | OS 3             |



2. Retrieve machines with 'OS 2':
```sql
SELECT device_id, operating_system
FROM machines
WHERE operating_system = 'OS 2';
```
| device_id | operating_system |
| --------- | ---------------- |
| 102       | OS 2             |
| 103       | OS 2             |



3. Retrieve employees in the Finance department:
```sql
SELECT *
FROM employees
WHERE department = 'Finance';
```
| employee_id | name  | department | office    | device_id |
| ----------- | ----- | ---------- | --------- | --------- |
| 1           | Alice | Finance    | North-101 | 101       |



4. Retrieve employees in the Sales department:
```sql
SELECT *
FROM employees
WHERE department = 'Sales';
```
| employee_id | name | department | office    | device_id |
| ----------- | ---- | ---------- | --------- | --------- |
| 2           | Bob  | Sales      | South-109 | 102       |



5. Identify the employee using office 'South-109':
```sql
SELECT *
FROM employees
WHERE office = 'South-109';
```
| employee_id | name | department | office    | device_id |
| ----------- | ---- | ---------- | --------- | --------- |
| 2           | Bob  | Sales      | South-109 | 102       |



6. Retrieve all employees in the South building:
```sql
SELECT *
FROM employees
WHERE office LIKE 'South-%';
```
| employee_id | name | department | office    | device_id |
| ----------- | ---- | ---------- | --------- | --------- |
| 2           | Bob  | Sales      | South-109 | 102       |



---
## Activity 3: Apply more filters in SQL

**Objectives:**
- Filter data by dates, times, and numeric values
- Use operators such as =, >, <, >=, <=, and <>

**Scenario:** Investigate login attempts using filters with numeric and date/time operators to analyze unusual activity.

**Sample Table: `log_in_attempts`**

| event_id | username | login_date | login_time | success | country |
|----------|---------|------------|-----------|--------|---------|
| 100      | Alice   | 2022-05-08 | 08:30:00  | 1      | USA     |
| 101      | Bob     | 2022-05-09 | 06:45:00  | 0      | CAN     |
| 102      | Charlie | 2022-05-10 | 07:15:00  | 1      | MEX     |
| 103      | Diana   | 2022-05-11 | 06:30:00  | 0      | USA     |
| 104      | Bob     | 2022-05-12 | 08:00:00  | 1      | USA     |

**Tasks and SQL Queries:**
1. Retrieve login attempts after '2022-05-09':
```sql
SELECT *
FROM log_in_attempts
WHERE login_date > '2022-05-09';
```
| event_id | username | login_date | login_time | success | country |
| -------- | -------- | ---------- | ---------- | ------- | ------- |
| 102      | Charlie  | 2022-05-10 | 07:15:00   | 1       | MEX     |
| 103      | Diana    | 2022-05-11 | 06:30:00   | 0       | USA     |
| 104      | Bob      | 2022-05-12 | 08:00:00   | 1       | USA     |



2. Retrieve login attempts on or after '2022-05-09':
```sql
SELECT *
FROM log_in_attempts
WHERE login_date >= '2022-05-09';
```
| event_id | username | login_date | login_time | success | country |
| -------- | -------- | ---------- | ---------- | ------- | ------- |
| 101      | Bob      | 2022-05-09 | 06:45:00   | 0       | CAN     |
| 102      | Charlie  | 2022-05-10 | 07:15:00   | 1       | MEX     |
| 103      | Diana    | 2022-05-11 | 06:30:00   | 0       | USA     |
| 104      | Bob      | 2022-05-12 | 08:00:00   | 1       | USA     |



3. Retrieve login attempts between '2022-05-09' and '2022-05-11':
```sql
SELECT *
FROM log_in_attempts
WHERE login_date BETWEEN '2022-05-09' AND '2022-05-11';
```
| event_id | username | login_date | login_time | success | country |
| -------- | -------- | ---------- | ---------- | ------- | ------- |
| 101      | Bob      | 2022-05-09 | 06:45:00   | 0       | CAN     |
| 102      | Charlie  | 2022-05-10 | 07:15:00   | 1       | MEX     |
| 103      | Diana    | 2022-05-11 | 06:30:00   | 0       | USA     |



4. Retrieve login attempts before '07:00:00':
```sql
SELECT *
FROM log_in_attempts
WHERE login_time < '07:00:00';
```
| event_id | username | login_date | login_time | success | country |
| -------- | -------- | ---------- | ---------- | ------- | ------- |
| 101      | Bob      | 2022-05-09 | 06:45:00   | 0       | CAN     |
| 103      | Diana    | 2022-05-11 | 06:30:00   | 0       | USA     |



5. Retrieve login attempts between '06:00:00' and '07:00:00':
```sql
SELECT *
FROM log_in_attempts
WHERE login_time BETWEEN '06:00:00' AND '07:00:00';
```
| event_id | username | login_date | login_time | success | country |
| -------- | -------- | ---------- | ---------- | ------- | ------- |
| 101      | Bob      | 2022-05-09 | 06:45:00   | 0       | CAN     |
| 103      | Diana    | 2022-05-11 | 06:30:00   | 0       | USA     |



6. Retrieve login attempts with event_id ≥ 100:
```sql
SELECT event_id, username, login_date
FROM log_in_attempts
WHERE event_id >= 100;
```
| event_id | username | login_date |
| -------- | -------- | ---------- |
| 100      | Alice    | 2022-05-08 |
| 101      | Bob      | 2022-05-09 |
| 102      | Charlie  | 2022-05-10 |
| 103      | Diana    | 2022-05-11 |
| 104      | Bob      | 2022-05-12 |



7. Retrieve login attempts with event_id between 100 and 150:
```sql
SELECT event_id, username, login_date
FROM log_in_attempts
WHERE event_id BETWEEN 100 AND 150;
```
| event_id | username | login_date |
| -------- | -------- | ---------- |
| 100      | Alice    | 2022-05-08 |
| 101      | Bob      | 2022-05-09 |
| 102      | Charlie  | 2022-05-10 |
| 103      | Diana    | 2022-05-11 |
| 104      | Bob      | 2022-05-12 |



---
## Activity 4: Filter with AND, OR, and NOT

**Objectives:**
- Apply multiple conditions in SQL queries
- Use AND, OR, and NOT operators

**Scenario:** Analyze employee login attempts and departmental information using multiple conditions and negations.

**Sample Tables:**

### Table: `log_in_attempts`

| event_id | username | login_date | login_time | success | country |
|----------|---------|------------|-----------|--------|---------|
| 100      | Alice   | 2022-05-08 | 08:30:00  | 1      | USA     |
| 101      | Bob     | 2022-05-09 | 19:00:00  | 0      | CAN     |
| 102      | Charlie | 2022-05-10 | 17:15:00  | 1      | MEX     |
| 103      | Diana   | 2022-05-11 | 20:30:00  | 0      | USA     |
| 104      | Eve     | 2022-05-12 | 16:00:00  | 1      | MEX     |

### Table: `employees`

| emp_id | username | department          | office     |
|--------|---------|-------------------|-----------|
| 1      | Alice   | Finance           | East-170  |
| 2      | Bob     | Sales             | South-109 |
| 3      | Charlie | Marketing         | East-320  |
| 4      | Diana   | Information Technology | West-205 |
| 5      | Eve     | Marketing         | East-170  |

**Tasks and SQL Queries:**
1. Failed login attempts after 18:00:
```sql
SELECT *
FROM log_in_attempts
WHERE login_time > '18:00' AND success = 0;
```
| event_id | username | login_date | login_time | success | country |
| -------- | -------- | ---------- | ---------- | ------- | ------- |
| 101      | Bob      | 2022-05-09 | 19:00:00   | 0       | CAN     |
| 103      | Diana    | 2022-05-11 | 20:30:00   | 0       | USA     |



2. Failed login attempts on '2022-05-08' or '2022-05-09':
```sql
SELECT *
FROM log_in_attempts
WHERE login_date = '2022-05-08' OR login_date = '2022-05-09';
```
| event_id | username | login_date | login_time | success | country |
| -------- | -------- | ---------- | ---------- | ------- | ------- |
| 100      | Alice    | 2022-05-08 | 08:30:00   | 1       | USA     |
| 101      | Bob      | 2022-05-09 | 19:00:00   | 0       | CAN     |



3. Login attempts not originating in Mexico:
```sql
SELECT *
FROM log_in_attempts
WHERE NOT country LIKE 'MEX%';
```
| event_id | username | login_date | login_time | success | country |
| -------- | -------- | ---------- | ---------- | ------- | ------- |
| 100      | Alice    | 2022-05-08 | 08:30:00   | 1       | USA     |
| 101      | Bob      | 2022-05-09 | 19:00:00   | 0       | CAN     |
| 103      | Diana    | 2022-05-11 | 20:30:00   | 0       | USA     |



4. Employees in Marketing department and East building:
```sql
SELECT *
FROM employees
WHERE department = 'Marketing' AND office LIKE 'East-%';
```
| emp_id | username | department | office   |
| ------ | -------- | ---------- | -------- |
| 3      | Charlie  | Marketing  | East-320 |
| 5      | Eve      | Marketing  | East-170 |



5. Employees in Finance or Sales department:
```sql
SELECT *
FROM employees
WHERE department = 'Finance' OR department = 'Sales';
```
| emp_id | username | department | office    |
| ------ | -------- | ---------- | --------- |
| 1      | Alice    | Finance    | East-170  |
| 2      | Bob      | Sales      | South-109 |



6. Employees not in Information Technology:
```sql
SELECT *
FROM employees
WHERE NOT department = 'Information Technology';
```
| emp_id | username | department | office    |
| ------ | -------- | ---------- | --------- |
| 1      | Alice    | Finance    | East-170  |
| 2      | Bob      | Sales      | South-109 |
| 3      | Charlie  | Marketing  | East-320  |
| 5      | Eve      | Marketing  | East-170  |



---
## Activity 5: Complete a join

**Objectives:**
- Use INNER JOIN, LEFT JOIN, and RIGHT JOIN to combine tables
- Retrieve information from multiple related tables

**Scenario:** Investigate employee machines and login attempts using INNER JOIN, LEFT JOIN, and RIGHT JOIN in SQL.

**Sample Tables:**

### Table: `employees`

| emp_id | username | department | device_id |
|--------|---------|-----------|-----------|
| 1      | Alice   | Finance   | 101       |
| 2      | Bob     | Sales     | 102       |
| 3      | Charlie | Marketing | 103       |
| 4      | Diana   | IT        | NULL      |
| 5      | Eve     | Marketing | 104       |

### Table: `machines`

| device_id | device_name | operating_system |
|-----------|------------|----------------|
| 101       | Laptop-A   | OS 1           |
| 102       | Laptop-B   | OS 2           |
| 103       | Laptop-C   | OS 2           |
| 105       | Laptop-E   | OS 1           |

### Table: `log_in_attempts`

| event_id | username | login_date | login_time | success |
|----------|---------|------------|-----------|--------|
| 100      | Alice   | 2022-05-08 | 08:30:00  | 1      |
| 101      | Bob     | 2022-05-09 | 19:00:00  | 0      |
| 102      | Charlie | 2022-05-10 | 17:15:00  | 1      |
| 103      | Eve     | 2022-05-11 | 20:30:00  | 0      |

**Tasks and SQL Queries:**
1. Inner join between machines and employees on device_id:
```sql
SELECT *
FROM machines
INNER JOIN employees ON machines.device_id = employees.device_id;
```
| device_id | device_name | operating_system | emp_id | username | department | device_id |
| --------- | ----------- | ---------------- | ------ | -------- | ---------- | --------- |
| 101       | Laptop-A    | OS 1             | 1      | Alice    | Finance    | 101       |
| 102       | Laptop-B    | OS 2             | 2      | Bob      | Sales      | 102       |
| 103       | Laptop-C    | OS 2             | 3      | Charlie  | Marketing  | 103       |



2. Left join to show all machines and their assigned employees:
```sql
SELECT *
FROM machines
LEFT JOIN employees ON machines.device_id = employees.device_id;
```
| device_id | device_name | operating_system | emp_id | username | department | device_id |
| --------- | ----------- | ---------------- | ------ | -------- | ---------- | --------- |
| 101       | Laptop-A    | OS 1             | 1      | Alice    | Finance    | 101       |
| 102       | Laptop-B    | OS 2             | 2      | Bob      | Sales      | 102       |
| 103       | Laptop-C    | OS 2             | 3      | Charlie  | Marketing  | 103       |
| 105       | Laptop-E    | OS 1             | NULL   | NULL     | NULL       | NULL      |



3. Right join to show all employees and their assigned machines:
```sql
SELECT *
FROM machines
RIGHT JOIN employees ON machines.device_id = employees.device_id;
```
| device_id | device_name | operating_system | emp_id | username | department | device_id |
| --------- | ----------- | ---------------- | ------ | -------- | ---------- | --------- |
| 101       | Laptop-A    | OS 1             | 1      | Alice    | Finance    | 101       |
| 102       | Laptop-B    | OS 2             | 2      | Bob      | Sales      | 102       |
| 103       | Laptop-C    | OS 2             | 3      | Charlie  | Marketing  | 103       |
| NULL      | NULL        | NULL             | 4      | Diana    | IT         | NULL      |
| 104       | Laptop-D?   | OS ?             | 5      | Eve      | Marketing  | 104       |



4. Inner join between employees and log_in_attempts on username:
```sql
SELECT *
FROM employees
INNER JOIN log_in_attempts ON employees.username = log_in_attempts.username;
```
| emp_id | username | department | device_id | event_id | username | login_date | login_time | success |
| ------ | -------- | ---------- | --------- | -------- | -------- | ---------- | ---------- | ------- |
| 1      | Alice    | Finance    | 101       | 100      | Alice    | 2022-05-08 | 08:30:00   | 1       |
| 2      | Bob      | Sales      | 102       | 101      | Bob      | 2022-05-09 | 19:00:00   | 0       |
| 3      | Charlie  | Marketing  | 103       | 102      | Charlie  | 2022-05-10 | 17:15:00   | 1       |
| 5      | Eve      | Marketing  | 104       | 103      | Eve      | 2022-05-11 | 20:30:00   | 0       |



---

## Reflection

During this lab module, I gained practical experience in using SQL to retrieve, filter, and combine data from relational databases. By performing a series of activities—from basic SELECT queries to applying complex filters and joining multiple tables—I strengthened my understanding of how to analyze and manipulate data efficiently.  

Key skills I developed include:

- **Querying data with SELECT**: I practiced retrieving specific columns or all columns from tables, allowing me to focus on the information relevant to security analysis tasks.  
- **Filtering data with WHERE, AND, OR, NOT, and BETWEEN operators**: I learned how to narrow down query results based on multiple criteria, including numeric, date, and time values, which is crucial when investigating security incidents.  
- **Sorting data using ORDER BY**: I understood how to organize information chronologically or by specific fields to detect patterns or anomalies in employee activity.  
- **Joining tables (INNER, LEFT, RIGHT JOINs)**: I gained hands-on experience combining data from multiple tables, enabling me to obtain a complete picture of employees, their devices, and login attempts.  
- **Using sample data for analysis**: Creating hypothetical tables and reviewing expected query outputs helped me visualize results and anticipate real-world scenarios in a corporate environment.  

Overall, this lab reinforced the importance of structured data retrieval and analysis in cybersecurity. It demonstrated how SQL is a powerful tool to monitor systems, investigate incidents, and support informed decision-making.  

---

## Conclusion

This lab provided a strong foundation in database management and SQL, equipping me with essential skills for a security analyst role. I can now:

1. Efficiently retrieve and filter data to investigate incidents or system activity.  
2. Apply logical operators and conditional statements to extract meaningful insights.  
3. Combine multiple data sources through SQL joins to generate comprehensive reports.  

Mastering these SQL techniques enhances my ability to monitor and secure organizational systems, investigate unusual activities, and maintain data integrity. These skills are fundamental for any cybersecurity professional and will directly support my future work in system administration, security auditing, and data-driven decision-making.

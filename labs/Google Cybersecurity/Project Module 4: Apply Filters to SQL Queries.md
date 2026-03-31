# Project Module 4: Apply Filters to SQL Queries

## Project Description
In this activity, I used SQL queries to investigate potential security incidents involving login attempts and employee devices. By applying filtering techniques such as AND, OR, NOT, and LIKE, I retrieved relevant records from the database. This analysis helped identify suspicious activity, ensured proper targeting for security updates, and supported incident response efforts, demonstrating practical cybersecurity skills.

---

## Retrieve After Hours Failed Login Attempts

A potential security incident occurred after business hours (after 18:00). To investigate, I filtered for failed login attempts that occurred after 18:00.

### Query:
```sql
SELECT *
FROM log_in_attempts
WHERE login_time > '18:00:00'
AND success = 0;
```
### Explanation:
- login_time > '18:00:00' filters for login attempts after 6 PM.
- success = 0 ensures only failed login attempts are returned.
- AND combines both conditions to refine the results.

**Security Impact:** This query helps identify potentially unauthorized access attempts outside normal working hours, which supports timely incident response.

---

## Retrieve Login Attempts on Specific Dates

A suspicious event occurred on May 9, 2022. To investigate, I retrieved login attempts on May 8 and May 9, 2022.

### Query:
```sql
SELECT *
FROM log_in_attempts
WHERE login_date = '2022-05-09'
OR login_date = '2022-05-08';
```

### Explanation:
- Filters records for the two specific dates.
- OR ensures results include login attempts from either date.

**Security Impact:** This allows analysis of events surrounding a specific incident to determine patterns or anomalies.

---

## Retrieve Login Attempts Outside of Mexico

Some suspicious activity did not originate from Mexico. I needed to investigate all login attempts outside Mexico.

### Query:
```sql
SELECT *
FROM log_in_attempts
WHERE country NOT LIKE 'MEX%';
```

### Explanation:
- NOT LIKE 'MEX%' excludes any country starting with MEX (e.g., MEX, MEXICO).
- % is a wildcard representing any number of characters.

**Security Impact:** This helps focus on non-local login attempts that may indicate unauthorized or unusual access.

---

## Retrieve Employees in Marketing

To perform security updates, I identified employees in the Marketing department located in the East building.

### Query:
```sql
SELECT *
FROM employees
WHERE department = 'Marketing'
AND office LIKE 'East%';
```

### Explanation:
- department = 'Marketing' filters employees by department.
- office LIKE 'East%' matches all offices in the East building.
- AND ensures both conditions are applied.

**Security Impact:** This query targets only relevant employees for security updates, minimizing disruption while maintaining system security.

---

## Retrieve Employees in Finance or Sales

To apply a different security update, I needed all employees in Finance or Sales.

### Query:
```sql
SELECT *
FROM employees
WHERE department = 'Finance'
OR department = 'Sales';
```

### Explanation:
- Filters employees in either the Finance or Sales departments.
- OR allows results to include either condition.

**Security Impact:** Ensures updates are applied to the correct employee groups without affecting unrelated departments.

---

## Retrieve All Employees Not in IT

Employees outside the Information Technology (IT) department required a specific security update. I retrieved all employees not in IT.

### Query:
```sql
SELECT *
FROM employees
WHERE department != 'Information Technology';
```

### Explanation:
- != 'Information Technology' excludes IT employees.
- This is an efficient way to target all non-IT employees.

**Security Impact:** This ensures updates are applied only where needed, maintaining operational stability in IT systems while enforcing security measures.

---

### Summary

In this activity, I applied SQL filtering techniques to investigate security-related data and target specific employee machines for updates. I utilized AND, OR, and NOT operators, as well as LIKE with wildcards, to refine query results. By combining date, time, and department filters, I was able to identify suspicious login attempts and ensure security updates were applied efficiently. These skills are essential for cybersecurity analysts to support incident response and maintain system integrity.

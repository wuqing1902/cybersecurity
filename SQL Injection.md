# SQL Injection Overview

<br>

## 1. Brief Introduction
SQL Injection (SQLi) is a type of security vulnerability where attackers can manipulate the SQL queries of an application by inserting malicious input. This can allow unauthorized access to data or control over the database.

<br><br>

## 2. Potential Impact
- **Obtain Login Access**: Attackers can bypass authentication and log in without valid credentials.
- **Modify or Delete Data**: Malicious users can alter or remove database records.
- **Extract Information Across Tables**: Attackers can access data from multiple tables in the database.
- **Steal Sensitive Data**: Information such as passwords, personal data, or financial records can be exposed.

<br><br>

## 3. How to Verify This Vulnerability
- **Submit a Single Quote (')**: Check if the system returns an SQL syntax error, indicating input is directly used in queries.
- **Boolean Testing (Boolean Conditions)**: Use logical payloads like `' OR 1=1 --` and `' OR 1=2 --` to see if the application's behavior changes. If it does, this confirms SQL queries are affected by user input.

<br><br>

## 4. Prevention
- **Use Parameterized Queries (Prepared Statements)**: Keep SQL logic and user input separate so input cannot alter query structure.
- **Whitelisting**: Only allow expected, safe input values to reduce the chance of malicious input.
- **Avoid String Concatenation**: Never build SQL queries by directly joining strings with user input, as this makes injection possible.

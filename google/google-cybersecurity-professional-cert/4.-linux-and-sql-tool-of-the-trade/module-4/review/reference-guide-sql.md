# Reference Guide, SQL

Here’s a **fun and ADHD-friendly** reference guide for SQL commands!

***

### **🎮 SQL Command Cheat Sheet**

#### **1. Query a Database: SELECT, FROM, and ORDER BY**

* **SELECT** – Choose which columns to return.
  * Example:\
    `SELECT employee_id`\
    `SELECT *` (returns all columns)
* **FROM** – Specify the table you’re querying.
  * Example:\
    `FROM employees`
* **ORDER BY** – Sort results by a column.
  * Example:\
    `ORDER BY department`\
    `ORDER BY city DESC` (descending)\
    `ORDER BY country, city` (multiple columns)

***

#### **2. Apply Filters to Queries: WHERE, AND, OR, etc.**

* **WHERE** – Apply conditions to your query.
  * Example:\
    `WHERE title = 'IT Staff'`
* **AND** – Both conditions must be true.
  * Example:\
    `WHERE region = 5 AND country = 'USA'`
* **OR** – Either condition can be true.
  * Example:\
    `WHERE country = 'Canada' OR country = 'USA'`
* **BETWEEN** – Filter within a range.
  * Example:\
    `WHERE hiredate BETWEEN '2002-01-01' AND '2003-01-01'`
* **LIKE** – Search for patterns.
  * Example:\
    `WHERE title LIKE 'IT%'`\
    `WHERE state LIKE 'N_'`
* **NOT** – Exclude a condition.
  * Example:\
    `WHERE NOT country = 'Mexico'`
* **Comparison Operators**:
  * **=**: Equals
  * **>**: Greater than
  * **>=**: Greater than or equal to
  * **<**: Less than
  * **<=**: Less than or equal to
  * **<>** or **!=**: Not equal to
  * Example:\
    `WHERE birthdate > '1970-01-01'`\
    `WHERE date != '2023-05-14'`

***

#### **3. Wildcards for Patterns (% and \_)**

* **%** – Replaces any number of characters.
  * Example:\
    `'a%'` (starts with 'a')\
    `'%a'` (ends with 'a')\
    `'%a%'` (contains 'a')
* **\_** – Replaces a single character.
  * Example:\
    `'a_'` (starts with 'a' and is followed by one character)\
    `'_a_'` (one character before and after 'a')

***

#### **4. Join Tables: INNER, LEFT, RIGHT, and FULL OUTER JOIN**

* **INNER JOIN** – Returns only matching rows.
  * Example:\
    `SELECT * FROM employees INNER JOIN machines ON employees.device_id = machines.device_id;`
* **LEFT JOIN** – Returns all rows from the left table, and matching rows from the right table.
  * Example:\
    `SELECT * FROM employees LEFT JOIN machines ON employees.device_id = machines.device_id;`
* **RIGHT JOIN** – Returns all rows from the right table, and matching rows from the left table.
  * Example:\
    `SELECT * FROM employees RIGHT JOIN machines ON employees.device_id = machines.device_id;`
* **FULL OUTER JOIN** – Returns all rows from both tables.
  * Example:\
    `SELECT * FROM employees FULL OUTER JOIN machines ON employees.device_id = machines.device_id;`

***

#### **5. Perform Calculations with Aggregate Functions**

* **COUNT** – Count the number of rows.
  * Example:\
    `SELECT COUNT(firstname)`
* **SUM** – Add up values in a column.
  * Example:\
    `SELECT SUM(cost)`
* **AVG** – Find the average of a column.
  * Example:\
    `SELECT AVG(height)`

***

Now you’ve got the essentials to **crush SQL queries** with **filters**, **joins**, and **calculations**! Keep this guide handy, and you’ll be flying through SQL tasks in no time. 🚀🎉

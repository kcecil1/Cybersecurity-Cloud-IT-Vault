Here’s a fun and ADHD-friendly guide to **comparing different types of SQL joins**!

---

### **🧩 SQL Joins: Combining Tables Like Puzzle Pieces!**

Imagine you have two different puzzle pieces (tables) that you want to fit together. **Joins** help you combine them in SQL, but depending on which type of join you use, you get different pieces of the puzzle!

---

### **🔗 Types of Joins: Inner and Outer**

There are **two main types of joins**: **Inner Joins** and **Outer Joins**. Let’s break them down!

---

### **🎯 Inner Join: Only Match Where the Pieces Fit!**

- **INNER JOIN** returns only the rows that match between the two tables. Think of it as combining the two tables, but only keeping the rows where the columns match perfectly.

- **Example:**
  ```
  SELECT username, operating_system, employees.device_id
  FROM employees
  INNER JOIN machines ON employees.device_id = machines.device_id;
  ```

- **Result**: You’ll only get employees who are matched with a machine based on **device_id**. No match? No result! It's like finding the puzzle pieces that fit together perfectly.

![[Pasted image 20241003162652.png]]

---

### **👈 Left Join: Keep All the Left Table!**

- **LEFT JOIN** returns **all rows** from the **left table** (the first one you specify) and only matching rows from the right table. If there’s no match, SQL will fill in the blanks with **NULL**.

- **Example:**
  ```
  SELECT *
  FROM employees
  LEFT JOIN machines ON employees.device_id = machines.device_id;
  ```

- **Result**: You get **all employees** and their machines—if they don’t have a machine, the machine columns will show **NULL**. It’s like keeping all the puzzle pieces from the left table and adding matches from the right.

![[Pasted image 20241003162716.png]]

---

### **👉 Right Join: Keep All the Right Table!**

- **RIGHT JOIN** does the **same** as LEFT JOIN, but in reverse! It returns all rows from the **right table** (the second one you specify) and only matching rows from the left table.

- **Example:**
  ```
  SELECT *
  FROM employees
  RIGHT JOIN machines ON employees.device_id = machines.device_id;
  ```

- **Result**: You get **all machines** and any employees that match—if a machine isn’t assigned to an employee, the employee columns will show **NULL**. It’s like keeping all the pieces from the right and adding left matches.

![[Pasted image 20241003162752.png]]

---

### **🌍 Full Outer Join: Keep Everything!**

- **FULL OUTER JOIN** gives you **everything** from **both tables**. Whether there’s a match or not, you get it all! If there’s no match, you get **NULLs** in the missing spots.

- **Example:**
  ```
  SELECT *
  FROM employees
  FULL OUTER JOIN machines ON employees.device_id = machines.device_id;
  ```

- **Result**: You get **all employees and all machines**—if there’s no match, SQL fills in the missing parts with **NULL**. It’s like merging **all puzzle pieces** from both tables, whether they fit or not!

![[Pasted image 20241003162821.png]]

---

### **📝 Quick Recap: Different Joins, Different Results!**

- **INNER JOIN**: Only keeps rows that match between both tables. 🧩🧩
- **LEFT JOIN**: Keeps **all rows** from the **left table** and matches from the right. 🧩🔲
- **RIGHT JOIN**: Keeps **all rows** from the **right table** and matches from the left. 🔲🧩
- **FULL OUTER JOIN**: Keeps **all rows** from **both tables**. 🧩🧩 + 🔲🔲

---

Now you know how to choose the right **join** for your SQL queries! 🎉 Each join type helps you get just the right pieces from your tables to answer important questions. Keep practicing, and soon you’ll be joining tables like a pro! 🚀
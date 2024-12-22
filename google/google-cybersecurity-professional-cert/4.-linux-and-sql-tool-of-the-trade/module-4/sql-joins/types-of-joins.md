# Types of joins

Here’s a fun and ADHD-friendly guide to **outer joins in SQL**!

***

#### **🔗 Outer Joins: Grabbing Everything (Even if It Doesn’t Match)!**

You’ve already learned about **INNER JOINS**—where you only get rows that match. Now, let’s level up and learn about **OUTER JOINS**—they’re all about grabbing rows even if they **don’t match**! Ready? Let’s dive in!

***

#### **🧩 What Are Outer Joins?**

While **inner joins** only return rows where there’s a match, **outer joins** give you a bit more flexibility. Even if there’s no match, SQL will still return **all rows** from one or both tables!

There are **three types** of outer joins:

1. **LEFT JOIN** 🌟
2. **RIGHT JOIN** 🌟
3. **FULL OUTER JOIN** 🌟

***

#### **👈 LEFT JOIN: “Give Me All from the Left Table!”**

* **LEFT JOIN** returns **all rows** from the **left table** (the first table you specify), and only matching rows from the **right table**. If there’s no match in the right table, you get a **NULL**.
* **Example**: You want all **employees** (left table) and their **machines** (right table), even if some employees don’t have a machine.

```
SELECT employees.employee_id, machines.operating_system
FROM employees
LEFT JOIN machines
ON employees.employee_id = machines.employee_id;
```

* The result: All employees, and if they don’t have a machine, you’ll see **NULL** for their machine.

***

#### **👉 RIGHT JOIN: “Give Me All from the Right Table!”**

* **RIGHT JOIN** is like **LEFT JOIN**, but reversed. It returns **all rows** from the **right table** and only matching rows from the **left table**. If there’s no match, you’ll see **NULL** in the left table’s columns.
* **Example**: You want all **machines** (right table) and the **employees** (left table) assigned to them, even if some machines don’t have an assigned employee.

```
SELECT employees.employee_id, machines.operating_system
FROM employees
RIGHT JOIN machines
ON employees.employee_id = machines.employee_id;
```

* The result: All machines, and if a machine doesn’t have an employee assigned, the **employee\_id** will be **NULL**.

***

#### **🌍 FULL OUTER JOIN: “Give Me Everything from Both Tables!”**

* **FULL OUTER JOIN** is the **biggest net** you can cast. It grabs **everything** from **both tables**! If there’s no match, you get **NULLs** on both sides.
* **Example**: You want **all employees** and **all machines**, even if there’s no match between them.

```
SELECT employees.employee_id, machines.operating_system
FROM employees
FULL OUTER JOIN machines
ON employees.employee_id = machines.employee_id;
```

* The result: Every row from **both** tables, with **NULLs** where there’s no match.

***

#### **🧠 Pro Tip: You Don’t Need to Memorize Everything!**

As a security analyst, you don’t need to memorize all the joins. You just need to understand **which join to use** and look up the specifics when you need them!

***

#### **🎯 Key Takeaways:**

* **LEFT JOIN**: Grabs everything from the **left table** and matches from the right. If no match, you get **NULLs** in the right table.
* **RIGHT JOIN**: Grabs everything from the **right table** and matches from the left. If no match, you get **NULLs** in the left table.
* **FULL OUTER JOIN**: Grabs **everything from both tables** and fills in the gaps with **NULLs**.

***

Now you know how to **join everything** even if things don’t match! 🎉 Keep practicing, and you’ll be an outer join master in no time! 🌟

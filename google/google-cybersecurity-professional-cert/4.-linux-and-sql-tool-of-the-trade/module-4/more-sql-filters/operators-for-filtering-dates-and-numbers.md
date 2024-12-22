# Operators for filtering dates and numbers

Here’s a fun and ADHD-friendly breakdown of **operators for filtering dates and numbers in SQL**!

***

#### **🎯 Filtering with Operators: Let’s Get Specific!**

You already know SQL can filter strings, numbers, and dates. But let’s explore **operators** a bit more and how they help you **laser-focus** your queries! 🌟

***

#### **🔢 Working with Numbers and Dates in Cybersecurity**

As a **security analyst**, you won’t just work with words. You’ll also need to filter **numbers** and **dates** like:

* **Login attempts** (How many times did someone try to log in?)
* **Log entry counts** (How many suspicious logs came in?)
* **Data volume** (How much data is moving?)
* **Login dates/times** (When did someone log in?)
* **Patch dates** (When were security patches applied?)

***

#### **💥 Operators: Your Filtering Tools**

Here are the operators you’ll use to **compare** numbers and dates:

| **Operator** | **Meaning**                |
| ------------ | -------------------------- |
| `<`          | Less than                  |
| `>`          | Greater than               |
| `=`          | Equal to                   |
| `<=`         | Less than or equal to      |
| `>=`         | Greater than or equal to   |
| `<>`         | Not equal to (or use `!=`) |

***

#### **🕵️‍♂️ Exclusive vs. Inclusive Operators: What’s the Difference?**

* **Exclusive** (e.g., `>`): **Excludes** the exact value you’re comparing.
  * Example: `birthdate > '1970-01-01'` means anyone **born after** January 1, 1970.
* **Inclusive** (e.g., `>=`): **Includes** the value you’re comparing.
  * Example: `birthdate >= '1970-01-01'` means anyone **born on or after** January 1, 1970.

***

#### **🔗 BETWEEN: The Operator for Ranges**

Need to find data **within a range**? That’s where **BETWEEN** comes in!

* **Example:** Want to find employees hired between **January 1, 2002** and **January 1, 2003**? Here’s how you do it:

```
SELECT firstname, lastname, hiredate
FROM employees
WHERE hiredate BETWEEN '2002-01-01' AND '2003-01-01';
```

This will return employees hired **on or between** those two dates, because **BETWEEN is inclusive**!

***

#### **📝 Key Takeaways: Your Operator Toolbox**

* **<** and **>** are **exclusive**—they don’t include the comparison value.
* **<=**, **>=**, and **BETWEEN** are **inclusive**—they include the comparison value.
* Use these operators in your **WHERE** clause to filter for **numbers** or **dates** like a pro!

***

Now you’re ready to filter numbers and dates with precision using operators! 🎉 Keep practicing, and you’ll be an SQL master in no time! 🎯

# Continuous learning in SQL

Here’s a fun and ADHD-friendly guide to **continuous learning in SQL** and how to use **aggregate functions**!

***

#### **🧠 Aggregate Functions: SQL’s Super Math Powers!**

SQL doesn’t just help you filter data or join tables—it can also **do math** for you with **aggregate functions**! These are like superpowers that let SQL **calculate** over a bunch of rows and give you one nice, clean result.

***

#### **🔢 What Are Aggregate Functions?**

**Aggregate functions** are built-in tools in SQL that let you crunch numbers and count rows! The **key point**? You get a single number back (instead of a bunch of rows).

Here are a few you’ll love:

1. **COUNT**: Tells you how many rows there are.
2. **AVG**: Finds the **average** of a column’s numbers.
3. **SUM**: Adds up all the numbers in a column.

***

#### **👨‍💻 Using Aggregate Functions: Syntax Time!**

To use an aggregate function, just:

1. Type `SELECT` and the function name (like `COUNT`, `AVG`, or `SUM`).
2. Put the column you want to calculate on in **parentheses**.
3. Sit back and let SQL do the work!

***

#### **🔍 Example 1: How Many Customers Are There?**

You can use the **COUNT** function to count rows in the `customers` table.

* **Example**: Count all customers:

```
SELECT COUNT(firstname)
FROM customers;
```

* **Result**: SQL returns **59**—that’s the number of customers! (It ignores any **NULL** values.)

***

#### **🇺🇸 Example 2: How Many Customers from the USA?**

Add a **filter** to count **only customers from the USA**:

```
SELECT COUNT(firstname)
FROM customers
WHERE country = 'USA';
```

* **Result**: SQL finds **13** customers from the USA!

***

#### **💡 Other Fun Aggregate Functions:**

*   **AVG**: Want to know the **average** age of your customers or average transaction amount? Use **AVG**!

    ```
    SELECT AVG(age)
    FROM customers;
    ```
*   **SUM**: Add up all sales or log-in attempts with **SUM**!

    ```
    SELECT SUM(log_in_attempts)
    FROM users;
    ```

***

#### **🔗 Keep Learning SQL: It’s Everywhere!**

You’ve already learned so much about SQL, but there’s **so much more** to explore! Here’s how to keep your SQL skills sharp:

1. **Get Curious**: Ask yourself what cool data you can get from your database. Then, figure out how to do it in SQL.
2. **Search Online**: There’s a treasure trove of SQL tutorials and examples. Search for **more aggregate functions** or advanced SQL tricks!
3. **Practice**: Try querying new databases, so you get hands-on experience with different data.

***

#### **🎯 Key Takeaways:**

* **Aggregate functions** are your secret weapon for crunching data in SQL.
  * **COUNT** = Count the rows.
  * **SUM** = Add up the numbers.
  * **AVG** = Find the average.
* Keep learning SQL by exploring new functions and practicing on new databases.

***

Now you’ve unlocked the power of **aggregate functions** in SQL! 🎉 Ready to count, sum, and average your way through your data? Let’s keep this SQL adventure going! 🚀

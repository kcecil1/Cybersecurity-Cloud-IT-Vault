# Filter dates and numbers

Here’s a fun and ADHD-friendly breakdown of **SQL filtering with new data types**!

***

#### **🎯 Filtering New Data Types: Let's Level Up!**

You’ve already learned how to filter **strings** (like usernames). Now we’re moving on to two more super-important data types in SQL: **numbers** and **dates & times**! 🚀

***

#### **💡 Three Common Data Types:**

1. **Strings:** Ordered sequences of characters (letters, numbers, symbols).
   * **Example:** `analyst10` (username).
2. **Numeric:** Data made up of **numbers**. You can do math with these!
   * **Example:** Number of **login attempts**.
3. **Date & Time:** Dates and times.
   * **Example:** `March 1st, 2021`, or `18:00` (6 PM).

***

#### **🔢 Working with Numbers and Dates: Let's Get Specific!**

As a **security analyst**, you’ll often need to **filter by numbers and dates**. Here are some common operators you’ll use:

* **=** (equal to)
* **>** (greater than)
* **<** (less than)
* **!=** (not equal to)
* **>=** (greater than or equal to)
* **<=** (less than or equal to)

***

#### **🕵️‍♂️ Example: Find Log-in Attempts After 6 PM**

Let’s say you want to find **log-in attempts made after 6 PM** (because that’s kinda suspicious!). Here's how you do it:

1. **Start with SELECT** to grab all the columns from the **log\_in\_attempts** table.
2. Use **WHERE** to apply the condition: **time > '18:00'**.

The SQL query looks like this:

```
SELECT *
FROM log_in_attempts
WHERE time > '18:00';
```

This will return all log-ins after **6 PM**!

***

#### **📅 Example: Filter Dates with BETWEEN!**

Want to see which machines were **patched between two dates**? Easy! You can use the **BETWEEN** operator to specify the range.

* **Example:** Find all patches installed between **March 1st, 2021**, and **September 1st, 2021**.

Here’s the SQL query:

```
SELECT *
FROM machines
WHERE OS_patch_date BETWEEN '2021-03-01' AND '2021-09-01';
```

This gives you all the patches installed during that time!

***

#### **💡 Key Reminder: Strings vs. Numbers**

* For **strings, dates, and times**, use **quotation marks** around the value (e.g., `'18:00'` or `'2021-03-01'`).
* For **numbers**, no quotation marks are needed.

***

#### **📝 Quick Recap: What Did We Learn?**

* You can now filter **numbers** and **dates** just like you did with strings.
* Use operators like `>`, `<`, `=`, and **BETWEEN** to set ranges and conditions.
* Quotation marks for **strings** and **dates**, but no quotes for **numbers**!

***

Now you’re ready to tackle **numbers** and **dates** in your SQL queries! 🎉 Stay tuned for the next video where you’ll learn how to **combine multiple conditions** for even cooler filters! 🚀

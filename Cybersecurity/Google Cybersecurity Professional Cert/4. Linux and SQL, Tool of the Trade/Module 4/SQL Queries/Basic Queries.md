Here’s a fun and ADHD-friendly summary of **running your first SQL query**!

---

### **🎯 First SQL Query: Let’s Find Those Computers!**

Imagine you’re a security analyst, and you need to figure out which computer has been assigned to a specific employee. How do you do that? **With SQL!**

---

### **🛠️ SQL Keywords: SELECT & FROM**

- **SELECT** tells SQL which **columns** you want.  
  - Example: We’re selecting **employee_id** and **device_id**.
  
- **FROM** tells SQL which **table** to pull the info from.  
  - Example: We’re pulling from the **employees table**.

**Easy way to remember it:** Think of it like sending a friend to buy groceries:  
“**SELECT** apples and bananas **FROM** the big box!”

---

### **💡 Writing the Query**  

Here’s the magic query we’re using:

```
SELECT employee_id, device_id 
FROM employees;
```

- Notice how we separate the two columns with a **comma**. It’s like saying, "I want apples **and** bananas!" 🍏🍌
- SQL keywords aren’t **case-sensitive** (you can write `SELECT` or `select`), but we usually capitalize them to make it **easier to read**.
- Always end your statement with a **semicolon (;)** – it’s like saying, "I’m done, run this!"

---

### **🚀 Run the Query!**  

Press **Enter** to run the query, and boom 💥—you’ll see which employees are using which computers. You just ran your **first SQL query**!

---

### **🔍 Want More Info? Use SELECT * (Select All)**  

What if you need more info, like what department they’re in or their username? Easy! Just use an **asterisk** (`*`) to select **all columns**.

Here’s how it looks:

```
SELECT * 
FROM employees;
```

Now you get **everything**—like getting the whole fruit basket instead of just apples and bananas!

---

### **🎉 Congrats! You Did It!**

You just wrote and ran a basic SQL query—**high-five**! 🖐️ In the next lesson, we’ll learn how to add **filters** to your queries to find even more specific data. 

---

SQL is like asking questions, and now you’ve learned how to ask the **right ones**! Keep going, and you’ll become an SQL pro in no time!
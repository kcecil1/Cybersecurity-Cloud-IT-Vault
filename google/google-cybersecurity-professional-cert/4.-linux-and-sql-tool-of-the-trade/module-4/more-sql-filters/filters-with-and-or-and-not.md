# Filters with AND, OR, and NOT

Here’s a fun and ADHD-friendly breakdown of **SQL operators** for filtering with multiple conditions!

***

#### **🔗 Multiple Conditions: Let’s Level Up Your Filters!**

Sometimes, you need to filter based on **more than one condition**—just like finding the perfect apple that’s both **large** AND **fresh**! Here’s how SQL helps you narrow things down using operators like **AND**, **OR**, and **NOT**.

***

#### **🍎 AND Operator: The “Must Meet Both” Rule**

* **AND** = **Both conditions must be true**.
  * Example: You want large apples that are **both fresh AND big**.
*   In SQL, it’s like saying:\
    "Give me all the machines running **OS 1** and **Email Client 1**."

    ```
    SELECT *
    FROM machines
    WHERE operating_system = 'OS 1'
    AND email_client = 'Email Client 1';
    ```

    The result? Only machines with **both OS 1 and Email Client 1**!

***

#### **🌀 OR Operator: The “Either or Both” Rule**

* **OR** = Either one condition or the other (or even both!) can be true.
  * Example: You want **either OS 1 or OS 3** because both need patches.
*   In SQL, it’s like saying:\
    "Show me machines with **OS 1 OR OS 3**."

    ```
    SELECT *
    FROM machines
    WHERE operating_system = 'OS 1'
    OR operating_system = 'OS 3';
    ```

    The result? You get machines with **either OS 1 or OS 3**!

***

#### **🚫 NOT Operator: The “Exclude This” Rule**

* **NOT** = Exclude anything that matches this condition.
  * Example: You want any fruit that is **NOT an apple** (because you’ve had enough apples).
*   In SQL, it’s like saying:\
    "Show me all machines **NOT running OS 3**."

    ```
    SELECT *
    FROM machines
    WHERE NOT operating_system = 'OS 3';
    ```

    The result? You get all machines that are **not running OS 3**!

***

#### **📝 Quick Recap:**

* **AND** = Both conditions must be true.
  * **Example:** Large **AND** fresh apples!
* **OR** = Either condition can be true.
  * **Example:** Machines with **OS 1 OR OS 3**.
* **NOT** = Exclude this condition.
  * **Example:** Show me all machines that **are not** using OS 3.

***

Now you’ve got the **AND, OR, and NOT** operators in your SQL toolbox! These will help you tackle **complex queries** like a pro. 🎉 Ready for the next adventure? We’ll be learning how to **join tables** together soon!🚀

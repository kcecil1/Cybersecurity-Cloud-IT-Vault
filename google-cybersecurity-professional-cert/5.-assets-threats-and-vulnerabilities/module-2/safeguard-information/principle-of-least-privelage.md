# Principle of least privelage

#### ADHD-Friendly Breakdown: Principle of Least Privilege (PoLP)

***

**What is PoLP?**

* **Definition**: Grant users only the minimum access they need to do their job or task.
* **Purpose**: Protects **Confidentiality**, **Integrity**, and **Availability** (CIA triad).
* **Goal**: Reduce risks like data breaches, accidental misuse, and tampering.

***

**Why PoLP Matters**

1. **Limits Access, Reduces Risk**:
   * Keeps sensitive data safe.
   * Prevents accidental or malicious data misuse.
   * Simplifies system monitoring.
2. **Makes Attacks Harder**:
   * Attackers can’t easily escalate privileges.
   * Clear connections between users and resources stop unauthorized actions.

***

**Implementation Essentials**

1. **Define Users**:
   * **Users** can be people (employees, contractors) or things (devices, software).
   * Every user needs an account, managed in a directory service.
2. **Determine Access**:
   * Ask:
     * **Who is the user?**
     * **What access do they really need?**

***

**Types of User Accounts:**

1. **Guest Accounts**: Temporary access for customers or contractors.
2. **User Accounts**: Standard access for employees.
3. **Service Accounts**: Access for applications/software.
4. **Privileged Accounts**: Admin-level access (use sparingly!).

***

**How PoLP Reduces Risk:**

* Example: A support agent can only see your data **while helping you.**
  * When done, access is revoked.
  * **This is dynamic, need-based access.**

***

**Auditing PoLP**

To keep least privilege effective, regularly **audit accounts**:

1. **Usage Audits**:
   * What resources are users accessing?
   * Can unused privileges be removed?
2. **Privilege Audits**:
   * Check for **privilege creep** (excess access over time).
   * Align access with job roles.
3. **Account Change Audits**:
   * Review logs for suspicious activity (e.g., password resets).
   * Ensure changes are authorized.

***

**Pro Tip: Password Security**

Even perfectly set-up accounts fail without strong passwords. Always enforce password best practices!

***

**The Big Takeaway**

The principle of least privilege minimizes risk, but only when paired with ongoing **auditing** and **strong access controls**. It’s a cornerstone of cybersecurity, ensuring data stays safe while users have just enough access to do their jobs.

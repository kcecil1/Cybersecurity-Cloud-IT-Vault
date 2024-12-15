# Authentication, authorization, and accounting

**Scenario Contextualization:**\
You’ve just joined the security team of a small, rapidly growing online marketing firm. The company manages sensitive client data, including marketing analytics, proprietary campaign strategies, and personnel files for consultants. Recently, there have been two worrying incidents:

1. **Incident A:** A contractor’s account remained active months after his contract ended, allowing unexpected access to payroll data.
2. **Incident B:** An internal employee’s single sign-on (SSO) credentials were compromised, granting unauthorized access to multiple applications at once.

Your task is to apply the concepts of authentication, authorization, and accounting (AAA), along with identity and access management (IAM) frameworks, to propose security measures that mitigate these vulnerabilities and improve the firm’s overall security posture. Consider the principles of least privilege, separation of duties, mandatory access control (MAC), discretionary access control (DAC), and role-based access control (RBAC) in your recommendations.

***

**Interactive Exercises:**

1.  **Analyze the Contractor Access Issue:**

    * **Background:** Robert Taylor, Jr., a contractor whose engagement ended in 2019, recently accessed payroll systems in 2023. This suggests that his account was never properly deprovisioned and still had admin privileges.

    **Your Questions:** a. Which principles of access control (least privilege, separation of duties) were violated here, and how?\
    b. What steps or controls (e.g., automated user provisioning/deprovisioning, temporary account policies, or time-based expiration) can you implement to prevent this from happening again?\
    c. Would you use MAC, DAC, or RBAC for managing contractor access and why?
2.  **SSO and MFA Challenge:**

    * **Background:** An employee’s single sign-on credentials were compromised, granting a threat actor access to multiple systems at once. While SSO improves user convenience, it also creates a single point of failure if not combined with additional factors of authentication.

    **Your Questions:** a. How could MFA have helped mitigate the damage from the compromised SSO credentials?\
    b. Propose a two-factor or three-factor authentication setup for employees. Which factors (knowledge, ownership, characteristic) would you use, and why?\
    c. How does implementing MFA align with the IAM goal of ensuring the right user is accessing the right resource at the right time?
3.  **Authorization Framework Selection:**

    * **Background:** The company wants to ensure that employees only have the privileges necessary for their job functions and no more.

    **Your Questions:** a. Consider a scenario where the marketing team should only have access to marketing analytics data but not HR files. Which access control model (MAC, DAC, or RBAC) would be most efficient to implement, and why?\
    b. Explain how separation of duties can be enforced in a company where a single employee previously held both data analysis and data approval permissions, leading to potential abuse.\
    c. Provide a concrete example of how you would assign roles and permissions under an RBAC model for a marketing specialist, an HR manager, and an IT administrator.
4.  **Accounting and Audit Logs:**

    * **Background:** The security team realizes that investigating after-the-fact requires solid auditing and accounting controls. They want to improve session logging, detect anomalies early, and trace unauthorized activities back to a user or device.

    **Your Questions:** a. Which pieces of information would you want your access logs to record to quickly detect suspicious activities?\
    b. Describe how session cookies, session IDs, and tokens help maintain security during user sessions. Also, explain the risks if these tokens are hijacked.\
    c. How would you use audit logs to detect unusual login patterns (e.g., repeated failed attempts, access from unexpected IP addresses), and what steps would you take once suspicious activity is identified?

***

***

\
Your Questions: a. Which principles of access control (least privilege, separation of duties) were violated here, and how?

**Teaching Explanation:**

In this scenario, two key principles of access control were not properly followed: **least privilege** and **separation of duties**.

1. **Least Privilege:**
   * **What is it?** The least privilege principle states that users should only have the minimum level of access required to perform their job responsibilities.
   * **How was it violated?** The contractor, whose work ended in 2019, still had an active account with administrative-level privileges in 2023. Since he no longer needed access to company data—especially not payroll records—retaining high-level permissions went against the idea of only granting the minimal necessary rights.
2. **Separation of Duties (SoD):**
   * **What is it?** The separation of duties principle ensures that no single individual has enough authority to execute high-risk tasks from start to finish on their own. This minimizes opportunities for fraud or misuse.
   * **How was it violated?** While the example directly shows a failure in revoking access, it also implies a lack of role separation. A contractor should not continue holding privileges that allow them to access sensitive areas like payroll data once they are no longer employed. If proper separation of duties were in place, the contractor’s role would have been clearly defined and restricted, and their access would have automatically ended, ensuring that tasks involving sensitive financial data required another authorized role or user.

**In summary:** By not revoking the contractor’s account or downgrading their privileges after their contract ended, the company failed to maintain the least privilege standard, and by allowing a single role to retain too much authority beyond the user’s employment period, they also undermined the principle of separation of duties.

***

b. What steps or controls (e.g., automated user provisioning/deprovisioning, temporary account policies, or time-based expiration) can you implement to prevent this from happening again?

**Teaching Explanation:**

To prevent the issue of former contractors or employees retaining access to systems, several proactive measures can be implemented. These revolve around ensuring that access is systematically granted when needed and automatically removed when it’s no longer required.

**Key Steps and Controls:**

1. **Automated User Provisioning/Deprovisioning:**
   * **What is it?** Provisioning means creating accounts and assigning the appropriate access rights when a user starts. Deprovisioning means disabling or removing these accounts and privileges immediately when a user leaves.
   * **How does it help?** By automating these processes, the system can ensure that once a contract or employment period ends, the user’s account is promptly disabled, preventing lingering access.
2. **Temporary or Contractor Account Policies:**
   * **What are they?** These policies involve creating accounts with a defined end-date or a contract-based expiration period.
   * **How does it help?** For short-term or contract workers, you can set an account to automatically expire at the end of their contract. After that date, access is terminated without needing manual intervention.
3. **Time-Based Expiration / Time-Limited Access:**
   * **What is it?** This approach ties user account validity or certain permissions to a specific timeframe.
   * **How does it help?** If a contractor needs access for only three months, their privileges automatically expire after three months, ensuring they cannot access the system indefinitely.
4. **Regular Access Reviews and Audits:**
   * **What are they?** Scheduled checks where HR, IT, and security teams review who has access to what resources.
   * **How does it help?** These periodic reviews catch any outdated accounts and ensure that employees and contractors only retain necessary privileges.
5. **Integration with HR Systems:**
   * **What is it?** Linking user accounts to a company’s HR database so that when an employee or contractor’s status changes (e.g., termination), the system automatically updates their access.
   * **How does it help?** This seamless connection ensures that when someone’s employment status changes, their access rights are immediately adjusted without a separate manual process.

**In summary:** By automating access granting and removal, setting accounts to expire automatically, and regularly reviewing who has access, you create a more robust system that prevents former contractors or employees from maintaining unauthorized access long after they should have been removed.

***

c. Would you use MAC, DAC, or RBAC for managing contractor access and why?

**Teaching Explanation:**

When deciding on an access control model for managing contractors, you need to consider how control over resource access is assigned, maintained, and revoked.

1. **Mandatory Access Control (MAC):**
   * **What is it?** Under MAC, access to resources is dictated by a central authority based on a classification system (e.g., “Confidential,” “Secret,” “Top Secret”). Users cannot change permissions on their own.
   * **Pros/Cons:** MAC is very strict and often used in highly secure, government-like contexts. It may be overly complex and restrictive for a small, growing firm and doesn’t easily adapt to the changing roles and short-term nature of contractor access.
2. **Discretionary Access Control (DAC):**
   * **What is it?** With DAC, the data owners (like system administrators or even users) decide who gets access. Permissions can be granted, changed, or revoked by individuals.
   * **Pros/Cons:** While DAC is more flexible and easy to set up, it can become messy. Over time, contractors might accumulate too many permissions because access decisions are often made informally by individuals, leading to inconsistencies and potential security gaps.
3. **Role-Based Access Control (RBAC):**
   * **What is it?** RBAC assigns permissions based on job roles rather than individuals. For example, “Contractor” might be a defined role with a specific set of permissions suitable for temporary staff.
   * **Pros/Cons:** RBAC is generally simpler to manage and maintain. Adding or removing someone’s access involves assigning or unassigning them to a role rather than individually editing permissions. This makes handling short-term workers like contractors much more efficient. Once a contract ends, removing the “Contractor” role from the user’s account immediately revokes their privileges.

**Why RBAC for Contractors?**\
By using RBAC, you can clearly define a “Contractor” role with limited, job-specific privileges. When the contractor is hired, you simply assign them to that role. When their contract ends, you remove the role assignment and their access is revoked automatically. This reduces the risk of lingering access and makes it easier to consistently apply the principle of least privilege.

***

***

a. How could MFA have helped mitigate the damage from the compromised SSO credentials?

***

**Teaching Explanation:**

Multi-Factor Authentication (MFA) is an additional security layer that requires a user to provide two or more pieces of evidence (factors) before being granted access. If the single sign-on (SSO) credentials (username and password) are compromised, MFA acts as a barrier that prevents unauthorized access—even if the attacker knows the username and password.

**How MFA Could Mitigate the Damage:**

1. **Requires an Additional Factor Beyond Username and Password:**\
   If SSO credentials are stolen, without MFA, the attacker can immediately log in to all connected systems. With MFA, the attacker would also need a second factor—such as a one-time code sent to a smartphone, a fingerprint scan, or a security token. Without access to this second factor, the stolen credentials alone aren’t enough to gain entry.
2. **Reduces the Impact of a Single Point of Failure:**\
   SSO provides convenience by letting one set of credentials open the door to multiple applications. But if those credentials are compromised, the attacker can potentially access everything. Adding MFA ensures that even if the “front door” (SSO credentials) is unlocked by an attacker, they still face another locked door (the second factor) before they can get inside.
3. **Deter and Alert Security Teams:**\
   If attackers try to log in with compromised credentials and fail the MFA step, security logs and alerts can be triggered. This helps detect suspicious activity early, prompting administrators to take immediate action—like resetting passwords, disabling accounts, or investigating the breach attempt.

**In summary:**\
MFA ensures that possessing the correct username and password is not enough for an attacker to gain access, significantly limiting the damage that can be done when SSO credentials are compromised.

***

b. Propose a two-factor or three-factor authentication setup for employees. Which factors (knowledge, ownership, characteristic) would you use, and why? \
\
c. How does implementing MFA align with the IAM goal of ensuring the right user is accessing the right resource at the right time?

***

**Teaching Explanation:**

**b. Proposing a Two-Factor or Three-Factor Authentication Setup:**

When designing an MFA system, you choose from three primary categories of factors:

* **Knowledge factors:** Something the user knows (e.g., passwords, PINs)
* **Ownership factors:** Something the user has (e.g., a security token, smartphone with an authenticator app, a smart card)
* **Inherence/Characteristic factors:** Something the user is (e.g., a fingerprint, facial recognition, retinal scan)

**Two-Factor Example:**

* **First Factor (Knowledge):** The user’s password (something they know).
* **Second Factor (Ownership):** A one-time code generated by a smartphone authenticator app or sent via SMS to the user’s phone (something they have).

**Why this combination?**

* Passwords are familiar and widely used.
* Authenticator apps or text messages provide a second layer that is more difficult for attackers to compromise without physically possessing the user’s phone or SIM card.

**Three-Factor Example (Adding a Biometric):**

* **First Factor (Knowledge):** The user’s password.
* **Second Factor (Ownership):** A hardware security key (like a USB token) or a smartphone-based authenticator.
* **Third Factor (Characteristic):** A fingerprint scan or facial recognition on a trusted device.

**Why this combination?**

* Even if an attacker somehow obtains both the password and the security token, they still need the user’s unique biometric data. This makes unauthorized access significantly more challenging.

**c. How MFA Aligns with IAM Goals:**

Identity and Access Management (IAM) aims to ensure that only the correct, authorized users gain access to sensitive resources at the appropriate time. MFA supports this by adding hurdles that attackers must overcome if they try to misuse stolen credentials.

* **Ensures the Right User:** By requiring multiple factors—something they know, have, or are—MFA confirms it’s not just someone who guessed or stole a password.
* **Ensures the Right Resource:** MFA can be tailored so that more sensitive resources demand stronger authentication. For example, viewing basic analytics might only need two factors, but accessing financial or HR records might require three.
* **Ensures the Right Time:** Some MFA systems include adaptive or risk-based authentication. If the user logs in from an unusual location or at an odd time, additional verification might be triggered. This ensures that even if factors are compromised, access isn’t granted under suspicious circumstances.

**In summary:**\
MFA strengthens the verification process and helps align with IAM’s primary goal: making sure the correct, legitimate users get the precise level of access they need, whenever they legitimately need it, without allowing unauthorized individuals in.

***

***

**Authorization Framework Selection:**

* **Background:** The company wants to ensure that employees only have the privileges necessary for their job functions and no more.

**Your Questions:** \
\
a. Consider a scenario where the marketing team should only have access to marketing analytics data but not HR files. Which access control model (MAC, DAC, or RBAC) would be most efficient to implement, and why?\
\
b. Explain how separation of duties can be enforced in a company where a single employee previously held both data analysis and data approval permissions, leading to potential abuse.\
\
c. Provide a concrete example of how you would assign roles and permissions under an RBAC model for a marketing specialist, an HR manager, and an IT administrator.

***

**Teaching Explanation:**

**a. Which Access Control Model is Most Efficient?**

* **Mandatory Access Control (MAC):**\
  MAC is often used in highly secure, government-level environments where access is assigned based on labels and classifications (e.g., “Secret,” “Top Secret”). It is rigid, centrally controlled, and not very flexible.
* **Discretionary Access Control (DAC):**\
  DAC leaves control to the owners of the resources. This can become inconsistent over time as individuals grant or revoke permissions without a central strategy. It can lead to “permission sprawl,” where too many people end up with access they don’t need.
* **Role-Based Access Control (RBAC):**\
  RBAC assigns permissions based on job roles rather than individuals. For example, everyone in the marketing team gets the “Marketing” role, which grants access to marketing analytics data only. They do not get the “HR” role, so they have no access to HR data. This model is easier to manage, scales well as the company grows, and ensures consistent application of the least privilege principle.

**Most Efficient Choice:** RBAC is typically the most efficient in this scenario because it allows you to set a single set of rules for the “Marketing” role and apply it to all current and future marketing team members—keeping access neatly aligned with job functions.

***

**b. Enforcing Separation of Duties (SoD):**

Separation of duties means no single individual should have complete control over a critical process. If one employee handled both data analysis and data approval previously, there was a risk that they could manipulate outcomes without oversight.

**How to Enforce SoD:**

1. **Split Responsibilities Between Two or More Roles:**
   * For example, create a “Data Analyst” role responsible for analyzing the data, but not for approving or publishing it.
   * Create a separate “Data Approver” role that reviews the analysis and approves it for use.
2. **Require Dual Authorization for Sensitive Actions:**
   * A data analyst cannot finalize a report without a data approver’s sign-off.
   * This means that even if the analyst tries to misuse or manipulate data, the changes won’t be finalized until an approver with separate permissions agrees.

By structuring the organization so that no single role has end-to-end control, potential abuse is greatly reduced.

***

**c. Concrete RBAC Examples:**

**Roles:**

1. **Marketing Specialist Role:**
   * **Permissions:** View and analyze marketing analytics data, access marketing dashboards.
   * **Rationale:** The marketing specialist needs to see campaign performance metrics but does not need access to HR or IT administrative tools.
2. **HR Manager Role:**
   * **Permissions:** View and edit HR files, manage employee records, handle payroll updates.
   * **Rationale:** The HR manager’s role requires access to sensitive employee data, but there is no need for them to view marketing analytics or IT server configurations.
3. **IT Administrator Role:**
   * **Permissions:** Manage user accounts (provisioning/deprovisioning), access server configurations, network settings, and security logs.
   * **Rationale:** The IT administrator ensures the systems run securely and smoothly. They need technical access but do not require access to HR or marketing data for their day-to-day tasks.

**By assigning employees to roles rather than directly giving them permissions, the company keeps its authorization structure organized, scalable, and strictly aligned with job functions.**

***

***

**Accounting and Audit Logs:**

* **Background:** The security team realizes that investigating after-the-fact requires solid auditing and accounting controls. They want to improve session logging, detect anomalies early, and trace unauthorized activities back to a user or device.

**Your Questions:** a. Which pieces of information would you want your access logs to record to quickly detect suspicious activities?\
b. Describe how session cookies, session IDs, and tokens help maintain security during user sessions. Also, explain the risks if these tokens are hijacked.\
c. How would you use audit logs to detect unusual login patterns (e.g., repeated failed attempts, access from unexpected IP addresses), and what steps would you take once suspicious activity is identified?

***

**Teaching Explanation:**

**a. Which Pieces of Information Should Access Logs Record?**\
When setting up access logs, include data that helps you identify “who did what, when, and from where.” Important details:

1. **User Identification:**
   * Username or unique user ID
   * Associated roles or groups
2. **Timestamp and Date:**
   * Exact time of login, logout, and resource access events
   * Allows you to reconstruct timelines and spot anomalies (like logins during unusual hours)
3. **Source Information (IP Address, Device Info):**
   * IP addresses, device identifiers, and geolocation (if available)
   * Helps detect unusual access patterns, such as logins from unexpected countries
4. **Event Details:**
   * Action performed (login attempt, data read/write, account changes)
   * Resource accessed (specific file names, database records, applications)
   * Success or failure status of the attempted action

By having these details, security teams can quickly identify suspicious activities—like an unfamiliar device accessing sensitive files at odd hours.

***

**b. Session Cookies, Session IDs, and Tokens:**

* **Session Cookies and Session IDs:**\
  Web applications often assign a unique session ID stored in a session cookie on the user’s browser after a successful login. This allows the server to remember the user and maintain their authenticated state as they navigate across pages. Without it, the user would have to re-authenticate on every page load.
* **Tokens (e.g., JWTs or OAuth Tokens):**\
  Tokens serve a similar purpose but are often more flexible and portable. They can be sent with each request to prove the user’s identity. Tokens may carry information about the user’s role, permissions, and session validity, and can be designed to expire after a set period for security.

**Risks if Tokens are Hijacked:**\
If an attacker manages to steal a user’s session cookie, session ID, or token, they can impersonate that user, gaining unauthorized access without needing the actual password. This is why it’s crucial to:

* Use secure and encrypted connections (HTTPS) so tokens aren’t easily intercepted.
* Implement short token lifetimes and refresh mechanisms.
* Require re-authentication for sensitive actions.

***

**c. Using Audit Logs to Detect Unusual Login Patterns and Taking Action:**

1. **Detecting Unusual Patterns:**
   * **Repeated Failed Login Attempts:**\
     Sudden spikes in failed attempts could indicate brute force attacks or password guessing attempts.
   * **Logins from Unexpected IP Addresses or Locations:**\
     If a user who normally logs in from one country suddenly starts logging in from another, it may raise a red flag.
   * **Odd Login Times:**\
     Login attempts occurring at unusual times (e.g., very late at night when the user typically doesn’t work) can signal suspicious behavior.
2. **Steps After Identifying Suspicious Activity:**
   * **Alert and Notification:**\
     Send alerts to the security team or an automated response system to investigate the anomaly.
   * **Session Termination:**\
     If an active suspicious session is detected, invalidate the token or session ID to prevent further unauthorized access.
   * **Account Lockout or Password Reset:**\
     Temporarily lock the user’s account to prevent further attempts and prompt them to reset their credentials.
   * **Review and Strengthen Controls:**\
     Depending on the severity, consider adding IP-based restrictions, enforcing MFA, or conducting user awareness training.
   * **Incident Response Procedure:**\
     Document the event, gather evidence, and follow the company’s incident response plan to contain and mitigate the impact.

**In summary:**\
Well-structured audit logs combined with proactive monitoring enable the detection of anomalies, while prompt responses help minimize damage and improve overall security.

***



***



***



***

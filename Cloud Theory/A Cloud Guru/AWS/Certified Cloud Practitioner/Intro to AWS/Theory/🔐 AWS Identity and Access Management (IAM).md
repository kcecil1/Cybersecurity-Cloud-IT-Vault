
**AWS IAM** (Identity and Access Management) is a tool for managing **who can access what** across all AWS services and resources.

#### 🧑‍💻 IAM Users:
- **Root User**: Created when you first sign up for AWS. This user has **full control** of the account.
- **IAM Users**: Additional users you create, each with specific access permissions.
- Example:
  - You own a company with:
    - 10 developers: access to development resources.
    - 5 salespeople: access to sales reports.
    - 2 testers: access to development and test servers.
    - 1 release engineer: access to all resources.
  - Using **policies**, you control what each user or group can access.
- **Policies**: Define what users can do.
  - Policies can be created using a **visual editor** or **JSON**.
  - Example: 
    - **Effect**: Allow or Deny.
    - **Action**: What the user can do (e.g., `ListBucket`).
    - **Resource**: What the policy applies to.

#### 📄 IAM Roles:
- Similar to users but with more versatility.
- **Roles** allow access delegation to **users or services**.
- Example:
  - If you have a virtual machine hosting a website and a separate AWS database, you can create a **role** that allows the virtual machine to access the database.
- **Roles** can be assumed by:
  - **Users** or **services**.
  - Even users from **different AWS accounts** can use roles, adding an extra security layer.

AWS IAM is fundamental for **managing permissions and securing access** to AWS resources, ensuring that users and services only have the permissions they need.
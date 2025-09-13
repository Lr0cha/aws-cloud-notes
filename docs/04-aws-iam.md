<h1 align="center">
  <img src="../assets/iam.png" alt="AWS IAM" width="35px"/>  
  AWS Identity and Access Management (IAM)
</h1>

AWS **Identity and Access Management (IAM)** is a web service that enables secure control of access to AWS resources. 
With IAM, you can centrally manage **users, groups, roles, and policies** to define **who** can access **what** in your AWS environment. 

> [!IMPORTANT]\
> IAM is a **global service**, not region-specific.
---

## 👥 Core IAM Concepts

- **Users** 
  Individual accounts for a physical user.
  - Example: a developer account with limited permissions. 

- **Groups**
  Collections of users with shared permissions. 
  - Example: a "Developers" group with access to code repositories. 

- **Roles**
  Provide temporary security credentials for trusted entities (such as AWS services or external users). 
  - Example: an **EC2 instance role** that allows the instance to read/write objects from an **S3 bucket** without storing access keys on the server. 

- **Policies** 
  JSON documents that define permissions using **Effect (Allow/Deny)**, **Action**, and **Resource**. 

>[!IMPORTANT]\
> Do not use the **root** account except for AWS account setup.

---

## 📜 Example IAM Policy (JSON)

This policy allows **read-only access** to a specific S3 bucket:

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [
        "s3:GetObject",
        "s3:ListBucket"
      ],
      "Resource": [
        "arn:aws:s3:::my-example-bucket",
        "arn:aws:s3:::my-example-bucket/*"
      ]
    }
  ]
}
````

**Simple Explanation**:

* `Effect`: Allow or Deny Statement
* `Action`: Specific API calls, which policy allows or denies (e.g.,`s3:GetObject`)
* `Resource`: AWS resources the policy applies to (identified by ARN)

> \[!NOTE]
> It’s a best practice to follow the **principle of least privilege**, granting only the permissions necessary for each task.

---

## 🔧 Additional IAM Tools

* **AWS CloudShell** – A browser-based CLI to interact with AWS resources securely.
* **IAM Credentials Report** – Provides a detailed overview of all IAM accounts, credentials, and their status (useful for audits).
* **IAM Trusted Advisor** – Offers security recommendations, such as detecting overly permissive policies or unused credentials.

## 🔗 Interesting resources
- [Aws IAM docs](https://docs.aws.amazon.com/iam/)
- [Use Cases of IAM](https://www.geeksforgeeks.org/devops/identity-and-access-management-iam-in-amazon-web-services-aws/)

<div align="center">
  <a href="./03-shared-responsibilities.md">◀️</a> |
  <a href="./05-aws-s3.md">▶️</a>
</div>

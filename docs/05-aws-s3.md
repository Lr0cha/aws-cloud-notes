<h1 align="center">
  <img src="../assets/s3.png" alt="Amazon S3" width="40px" style="vertical-align: middle;"/>  
  Amazon Simple Storage Service (S3)
</h1>

**Amazon S3** is an object storage service that enables organizations to store, secure, and manage virtually unlimited amounts of data in the cloud. 

> [!NOTE]\
> There are other various storage service types such as File Storage as Service (Amazon EFS), Block Storage as Service (Amazon EBS) and others, covered right [here]().

---

## 📦 Storage Model

- Data is stored as **objects** inside **buckets**, which have its own set of policies and configurations. 
- Each object is identified by a **unique key** (its name within the bucket). 
- Objects consist of the data itself, metadata, and a unique identifier. 

> [!IMPORTANT]\
> Buckets must have a globally **unique** name

> [!NOTE]\
> AWS S3 can hold files of size ranging from 0 bytes to 5 TB.

---

## 🔑 Key Features

- **Versioning** – Retain multiple **versions** of objects, enabling recovery from accidental deletions or overwrites. 
- **Access Control** – Managed through:
  - **IAM Policies**
  - **Bucket Policies**
  - **Access Points**
  - **ACLs (Access Control Lists)** 
- **Durability & Availability** – Designed for **99.999999999% (11 nines)** durability by automatically replicating data across multiple devices and facilities. 
- **Replication** – Copy objects across AWS **Regions** (Cross-Region Replication) or within the same Region (Same-Region Replication) for compliance, backup, and low-latency access.

> [!NOTE]\
> Amazon S3 integrates with many AWS services (such as CloudFront, Athena, and Lambda), making it a **foundational service** for modern cloud architectures. 

---

## 🗂️ What are the types of S3 Storage Classes?

Amazon S3 offers multiple storage classes to balance **cost, availability, and performance**: 

- **S3 Standard** – High durability, availability, and low latency, which is best for frequently accessed data. 
- **S3 Intelligent-Tiering** – Automatically moves data between frequent and infrequent access tiers based on usage patterns. 
- **S3 Standard-IA (Infrequent Access)** – Lower-cost storage for data that is accessed less often but requires rapid retrieval. 
- **S3 One Zone-IA** – Like Standard-IA but stored in a single AZ; cheaper but less resilient. 
- **S3 Glacier / Glacier Deep Archive** – Low-cost storage for archival data with retrieval times ranging from minutes to hours. 

---

## Example Use Cases

- Data backups and disaster recovery 
- Hosting static websites 
- Data lakes for analytics and machine learning 
- Media storage and content delivery 
- Log storage and compliance archiving 

---

## 🔗 Interesting resources
- [What is Amazon S3?](https://docs.aws.amazon.com/AmazonS3/latest/userguide/Welcome.html)
- [Introduction to AWS S3](https://www.geeksforgeeks.org/devops/introduction-to-aws-simple-storage-service-aws-s3/)







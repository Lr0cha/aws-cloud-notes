<div align="center">
  <img src="https://upload.wikimedia.org/wikipedia/commons/9/93/Amazon_Web_Services_Logo.svg" alt="img" width="250"><br>
  <h1>Amazon Web Services (AWS)</h1>
</div><br>

**Amazon Web Services (AWS)** is the world’s most comprehensive and widely adopted cloud platform, offering over **200 fully featured services** for compute, storage, databases, networking, analytics, machine learning, artificial intelligence, Internet of Things (IoT), security, and more.

---

## 🌍 Global Infrastructure

AWS’s infrastructure is built for **high availability, scalability, and fault tolerance**.
It is divided into several key components:

- **Regions**: Geographic areas around the world (e.g., `us-east-1` in North Virginia, `sa-east-1` in São Paulo).
- **Availability Zones (AZs)**: Independent data centers within a region, each with its own power, networking, and cooling.
- **Edge Locations**: Used by services like **Amazon CloudFront** to cache content closer to users for reduced latency.

By distributing applications across **multiple AZs**, users can design **resilient systems** that continue to function even if one data center fails (redundancy).

---

## 🛠️ Some Core AWS Services

Here are some of the most commonly used AWS services:

- **Compute**:
  - <img src="../assets/ec2.png" alt="EC2" width="30"/> [**Amazon EC2**](07-aws-ec2.md) – Virtual servers in the cloud. 
  - <img src="../assets/lambda.png" alt="LAMBDA" width="30"/> [**AWS Lambda**](12-aws-lambda.md) – Serverless computing that runs code without provisioning servers.

- **Storage**: 
  - <img src="../assets/s3.png" alt="S3" width="30"/> [**Amazon S3**](05-aws-s3.md) – Object storage with virtually unlimited scalability. 
  - <img src="../assets/ebs.png" alt="EBS" width="30"/> [**Amazon EBS**](10-aws-storage.md) – Block storage volumes for use with EC2. 

- **Databases**:
  - <img src="../assets/rds.png" alt="RDS" width="30"/> [**Amazon RDS**](11-aws-databases.md) – Managed relational databases (MySQL, PostgreSQL, Oracle, SQL Server).
  - <img src="../assets/dynamo-db.png" alt="DYNAMODB" width="30"/> [**Amazon DynamoDB**](11-aws-databases.md) – NoSQL database with single-digit millisecond latency.

- **Networking**:
  - <img src="../assets/vpc.png" alt="VPC" width="30"/> [**Amazon VPC**](06-aws-vpc.md) – Isolated networks in the cloud.
  - <img src="../assets/route53.png" alt="ROUTE53" width="30"/> **Route 53** – Scalable Domain Name System (DNS) service. 
- **Security & Identity**: 
  - <img src="../assets/iam.png" alt="IAM" width="30"/> [**AWS IAM**](04-aws-iam.md) – Identity and Access Management for fine-grained permissions.

---

## 💡 Why Choose AWS?

- **Scalability**: Scale applications up or down instantly.
- **Flexibility**: Wide variety of services and pricing models.
- **Reliability**: Built-in redundancy across AZs and regions.
- **Security**: Strong compliance standards and encryption capabilities.
- **Innovation**: Continuous release of new services and features.

---

## 🔗 Interesting resources
- [What is aws?](https://aws.amazon.com/pt/what-is-aws/)

<div align="center">
  <a href="./01-cloud-overview.md">◀️</a> |
  <a href="./03-shared-responsibilities.md">▶️</a>
</div>







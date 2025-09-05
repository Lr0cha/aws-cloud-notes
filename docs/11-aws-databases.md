<div align="center">
<h1>AWS Database Services</h1>
</div>

AWS offers fully managed database services for different workloads and application needs. 

> [!NOTE]\
> They can be grouped into **Relational Databases (SQL)**, **Non-Relational Databases (NoSQL)**, and **In-Memory Caching**.

---

## 📊 Relational Databases (SQL)

Relational databases organize data in **tables** with rows and columns, using **SQL** for queries and transactions. 
They are best suited for applications requiring **strong consistency** and **structured data**.

<div>
  <h3>
    <img src="../assets/rds.png" alt="AWS RDS" width="25px"/>
    Amazon RDS (Relational Database Service)</h3>
</div>

- **What it is:** Managed relational database service supporting engines like MySQL, PostgreSQL, MariaDB, Oracle, and SQL Server. 
- **Key features:**
  - Automated backups, patching, and replication. 
  - Supports **Multi-AZ** for high availability (fail over).

> [!NOTE]\
> If the primary instance or its AZ fails RDS **automatically switches** to the standby instance ensuring minimal downtime. 

  - **Read replicas** for scalability. 
  - Integration with VPC, IAM, and KMS for security.

<div>
  <h3>
    <img src="../assets/aurora.png" alt="AWS AURORA" width="25px"/>
    Amazon Aurora</h3>
</div>

- **What it is:** AWS’s **own** cloud-native relational database, compatible with **MySQL** and **PostgreSQL**. 
- **Key features:**
  - Up to **5x faster** than MySQL and **3x faster** than PostgreSQL. 
  - Auto-scaling storage (up to 128 TB per database). 
  - Replicates across **3 Availability Zones** by default. 
  - Offers **[Aurora Serverless](https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/aurora-serverless-v2.html)** → auto-scaling, pay-per-use model. 

---

## 📂 Non-Relational Databases (NoSQL)

Non-relational databases are schema-less and designed for **flexibility, scalability, and high throughput**. 

> [!NOTE]\
> Ideal for **unstructured data**, IoT, gaming, etc.

<div>
  <h3>
    <img src="../assets/dynamo-db.png" alt="AWS DYNAMODB" width="25px"/>
    Amazon DynamoDB</h3>
</div>

- **What it is:** Fully managed, serverless **NoSQL key-value and document database**. 
- **Key features:**
  - Single-digit millisecond latency at any scale. 
  - **On-demand scaling** and **global replication**.
  - Standard & Infrequent Access (IA) Table Class. 
  - Integrated with AWS Lambda (event-driven). 
  - Supports TTL (time-to-live) for automatic record expiration. 
---

## In-Memory Caching

Caching services are used to **reduce database load** and improve application performance by **storing frequently** accessed data in memory. 

<div>
  <h3>
    <img src="../assets/elastic-cache.png" alt="AWS ELASTIC CACHE" width="25px"/>
    Amazon ElastiCache</h3>
</div>

- **What it is:** Fully managed in-memory cache service supporting **Redis** and **Memcached**. 
- **Use cases:** Session storage, leaderboards, caching API responses, speeding up database queries. 
- **Key features:**
  - Sub-millisecond latency. 
  - Highly scalable and secure. 
  - Automatic failover and clustering. 

> [!IMPORTANT]\
> There is a DynamoDb' cache service ([Amazon DynamoDB Accelerator (DAX)](https://www.geeksforgeeks.org/dynamo-db/aws-dynamodb-introduction-to-dynamodb-accelerator-dax/))
---

## Review
- **RDS** → Traditional relational workloads (OLTP, business apps). 
- **Aurora** → Cloud-optimized relational DB with high performance and availability. 
- **DynamoDB** → NoSQL workloads needing high throughput and low latency. 
- **ElastiCache** → Speed up applications with in-memory caching. 

---


## 🔗 Interesting resources
- [Amazon RDS and Aurora Documentation](https://docs.aws.amazon.com/rds/)
- [Amazon RDS - Introduction to Amazon Relational Database System](https://www.geeksforgeeks.org/devops/amazon-rds-introduction-to-amazon-relational-database-system/)
- [Amazon DynamoDB Documentation](https://docs.aws.amazon.com/dynamodb/)
- [Common ElastiCache Use Cases and How ElastiCache Can Help](https://docs.aws.amazon.com/AmazonElastiCache/latest/dg/elasticache-use-cases.html)
- [Using AWS Lambda with Amazon DynamoDB](https://docs.aws.amazon.com/lambda/latest/dg/with-ddb.html)

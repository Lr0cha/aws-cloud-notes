<h1 align="center">
  <img src="../assets/ec2.png" alt="Amazon EC2" width="40px" style="vertical-align: middle;"/>  
  Amazon Elastic Compute Cloud (EC2)
</h1>

**Amazon EC2** is an **Infrastructure as a Service (IaaS)** offering that provides **resizable virtual servers (instances)** in the AWS Cloud. 
It allows, for example, organizations to run applications without the cost and complexity of managing physical hardware, while offering **flexibility**, **scalability**, and **control**. 

---

## 🔑 Key concepts and features
- **Elastic Capacity** – **Scale** compute resources **up** or **down** within minutes, matching real time demand. 
- **Flexible Pricing Models**: 
  - **On-Demand Instances** – Pay per second/hour with **no** long-term commitment. 
  - **Reserved Instances** – 1–3 year commitment for up to 75% cost savings. 
  - **Spot Instances** – Take advantage of **spare** AWS capacity at deep discounts. 
  - **Savings Plans** – Flexible cost model for long-term workloads.
 
    
- **Compute Options** – Wide selection of instance families optimized for different use cases: 
  - **General Purpose** – Balanced compute, memory, and networking (e.g, web servers and code repositories). 
  - **Compute Optimized** – High-performance compute for intensive tasks. 
  - **Memory Optimized** – Large memory footprint to deliver fast performance for workloads that process **large data** sets in memory. 
  - **Storage Optimized** – High I/O and throughput for big data and more. 
  - **Accelerated Computing** – GPUs/FPGA for ML, AI, graphics, and HPC.

 > 📌 Learn more about compute options [**here**](https://aws.amazon.com/ec2/instance-types/)
    
- **Networking** – Integration with [**VPC**](./06-aws-vpc.md), subnets, Elastic IPs, Security Groups, and NACLs for network isolation and control. 
- **High Availability** – Deploy instances across multiple **Availability Zones**, integrate with **Auto Scaling** and **Elastic Load Balancing**.
- **Amazon Machine Images (AMIs)** – Preconfigured templates with OS, applications, and **settings** for consistent deployments. 
- **Automation** – Configure startup tasks with **User Data scripts** (install software, run updates, launch services). 
- **Amazon CloudWatch Monitoring** – Track CPU, memory, disk, and network metrics; set alarms and automate scaling actions.
---

## 💾 Storage Options

- **Amazon Elastic Block Store (EBS)** – Persistent block storage volumes that survive stop/terminate.
- **Instance Store** – Disks that are physically attached to the host.

> [!NOTE]\
> Data is lost when the instance stops.

- **Amazon Elastic File System (EFS)** – Fully managed, scalable shared file system accessible by multiple instances. 
- [**Amazon S3 Integration**](./05-aws-s3.md) – Store backups, logs, and application data for durability and cost efficiency. 

- [**Database Services**]()

---

## 🔐 Security & Access

- **Key Pairs** – Secure SSH (Linux) or RDP (Windows) login. 
- **Security Groups** – Instance-level virtual firewalls controlling inbound/outbound traffic. 
- **IAM Roles for EC2** – **Assign permissions** to instances securely without embedding credentials. 

---

## 🔗 Interesting resources
- [What is Amazon EC2?](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/concepts.html)
- [Introduction to AWS EC2](https://www.geeksforgeeks.org/cloud-computing/what-is-elastic-compute-cloud-ec2/)







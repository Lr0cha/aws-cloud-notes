<div align="center">
  <h1>💾 AWS Storage Services</h1>
</div>

AWS provides different types of storage solutions, each **optimized** for **specific** use cases. 
> [!NOTE]\
> Storage in AWS generally falls into **three categories**: **Block**, **File**, and **Object** storage. 

---

## 📦 Block Storage
Block storage behaves like traditional hard drives, where data is divided into **blocks** and accessed at the operating system level.

> [!NOTE]\
> Optimized to applications requiring low-latency and durable storage **attached** to single Amazon EC2 instances or containers.

<div>
  <h3>
    <img src="../assets/ebs.png" alt="AWS EBS" width="25px"/>
    Amazon Elastic Block Store (EBS)</h3>
</div>

- **What it is:** Persistent block storage volumes for use with EC2 instances. 
- **Use cases:** OS boot volumes, transactional workloads, etc. 
- **Key features:**
  - Designed for **low-latency, high-performance workloads**. 
  - Volumes **persist** even if the instance is stopped or terminated (unless deleted). 
  - Supports encryption, **snapshots**, and resizing.
  - Volume types: General Purpose SSD (gp3/gp2), Provisioned IOPS SSD (io1/io2), Throughput Optimized HDD (st1), Cold HDD (sc1).
> [!NOTE]\
> EBS snapshots are point-in-time backups of Amazon EBS volumes that persist independently from the volume itself.

<div>
  <h3>
    <img src="../assets/ec2.png" alt="AWS EC2 Instance Store" width="25px"/>
    EC2 Instance Store</h3>
</div>

- **What it is:** Temporary block storage physically attached to the host server. 
- **Use cases:** Caches, buffers, **temporary** data that can be regenerated. 
- **Key features:**
  - Very high performance (directly attached to host). 
  - **Ephemeral** → data is lost when the instance stops, hibernates, or terminates. 

---

## 📁 File Storage
File storage provides a **shared** file system that can be accessed from multiple instances and on-premise environments.

<div>
  <h3>
    <img src="../assets/efs.png" alt="AWS EFS" width="25px"/>
    Amazon Elastic File System (EFS)</h3>
</div>

- **What it is:** Fully managed, elastic, and scalable **NFS** file system. 
- **Use cases:** Web serving, content management, container storage, big data analytics. 
- **Key features:**
  - Can be mounted on thousands of EC2 instances simultaneously. 
  - Scales automatically as files are added/removed. 
  - Storage classes: Standard & Infrequent Access (IA). 
  - Integrates with VPC for secure access.
  - Used for **Linux** host due NFS.

> [!NOTE]\
> Amazon EFS is accessible across most types of Amazon Web Services compute instances,(e.g., Amazon EC2, ECS,Lambda, etc). 

<div>
  <h3>
    <img src="../assets/fsx.png" alt="AWS FSX" width="25px"/>
    Amazon FSX</h3>
</div>

Managed file systems built on popular file server technologies. 
- **FSx for Windows File Server** → Native Windows file system with SMB support. 
- **FSx for Lustre** → High-performance file system for HPC and ML workloads. 

---

## 🗄️ Object Storage
Object storage stores data as objects (files + metadata + unique identifier) inside **buckets**. 

👉 **See full notes:** [Amazon S3 (Simple Storage Service)](./05-aws-s3.md) 

---

## Review
- **EBS** → Transactional workloads, databases, and OS volumes. 
- **Instance Store** → Temporary, high-performance cache/storage. 
- **EFS** → Shared file system across many EC2 instances. 
- **FSx** → Specialized file systems (Windows apps or HPC workloads). 
- **S3** → Data lakes, backups, archival, static hosting, big data analytics. 

---



## 🔗 Interesting resources
- [Choosing an AWS storage service](https://docs.aws.amazon.com/decision-guides/latest/storage-on-aws-how-to-choose/choosing-aws-storage-service.html)
- [AWS Storage: EBS vs. S3 vs. EFS](https://youtu.be/_CN7KqC3y3s?si=ncQCYxMkkfcGnlCO)



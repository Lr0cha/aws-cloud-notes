<h1 align="center">
  🐳 AWS Containers: ECR, ECS & Fargate
</h1>

AWS offers fully managed services to build, store, and run containers at scale without worrying about the underlying infrastructure. 

<div>
  <h3>
    <img src="../assets/ecr.png" alt="AWS ECR" width="25px"/>
    Amazon ECR (Elastic Container Registry)</h3>
</div>

Amazon Elastic Container Registry (ECR) is a **fully managed container registry** service that makes it easy to store, manage, and deploy Docker container images, and OCI-compliant artifacts. 

> [!NOTE]\
> Think of ECR as **"Docker Hub, but managed inside AWS"**.

### 🔑 Key Features and Concepts

* **Secure Storage**: ECR is integrated with [AWS IAM](./04-aws-iam.md), controlling who can access your container repositories. It also supports encryption at rest using AWS Key Management Service (KMS).

* **Image Scanning**: Amazon ECR performs **automated vulnerability scanning** of container images when they are **pushed** to the registry.

* **Highly Available & Scalable**

* **Seamless Integration**: Amazon ECR integrates seamlessly with services like Amazon Elastic Container Service (ECS), Elastic Kubernetes Service (EKS), and AWS Fargate.

* **Repositories**
  Amazon ECR repositories are containers for your images, and they support both **public** and **private** repositories. 

> [!IMPORTANT]\
> Amazon ECR uses AWS Identity and Access Management (IAM) to enable resource-based permissions for private Docker repositories to push, pull, and manage images through CLI.

* **Lifecycle Policies**
  ECR supports **lifecycle policies**, allowing you to automate the **cleanup** of unused or old images, helping to manage storage costs and maintain the health of your registry.

* **Version Control**

> \[!IMPORTANT]
> When using the **AWS CLI** with Amazon ECR, ensure you're using the latest version of the CLI to access all the latest features, including new image scanning capabilities and repository management functions.

---

<div>
  <h3>
    <img src="../assets/ecs.png" alt="AWS ECS" width="25px"/>
    Amazon ECS (Elastic Container Service)</h3>
</div>

Amazon ECS is a **fully managed, highly scalable container orchestration service** that allows you to run and manage Docker containers on AWS. 


### 🔑 Key Features and Concepts

- **Clusters** – Logical groups where tasks and services run. 
  - Backed either by **EC2 instances** (that you manage) or **AWS Fargate** (serverless).

- **Task Definitions** – JSON blueprints that define:
  - Which container images to run (from ECR, Docker Hub, etc.)
  - CPU and memory requirements
  - Networking mode
  - Environment variables and IAM roles
  - Data volumes

- **Tasks** – Running instances of a task definition (i.e., containers in action).

- **Services** – Ensure that a **specified number of tasks** are always running. 
  - Can integrate with **Load Balancers (ALB/NLB)** for traffic distribution. 
  - Supports **auto scaling** based on demand.

### 🚀 Launch Types

ECS supports two primary launch types:

1. **ECS on EC2**
   - You provision and manage EC2 instances to serve as container hosts. 
   - Provides full control over instance types, AMIs, networking, and scaling. 
   - Best when you need **fine-grained control** over infrastructure or want to use **Reserved Instances/Spot** for cost optimization.

2. **ECS on Fargate**
   - Serverless compute: AWS manages the underlying infrastructure. 
   - No need to manage EC2 instances, scaling, or patching. 
   - You only define the **task definition** (what to run) and ECS + Fargate take care of **where to run it**. 
   - Best for teams that want **simplicity**.

---

<div>
  <h3>
    <img src="../assets/fargate.png" alt="AWS FARGATE" width="25px"/>
    AWS Fargate</h3>
</div>

Fargate is a **serverless compute engine for containers**.

- **No infrastructure management** – You don’t need to provision or scale EC2 instances.
- **Pay-per-use** – Billed per vCPU and memory usage per second.
- **Security isolation** – Each task runs in its own kernel-level isolation.
- **Integration** – Works with ECS and EKS.

> [!NOTE]\
> With Fargate, you only define **"what to run"**, not **"where to run"**.

---

##  Common Example

1. Build a Docker image and **push to ECR**. 
2. Define an ECS **Task Definition** pointing to the image. 
3. Run it in ECS using either **EC2** or **Fargate**. 
4. Optionally expose via an **Application Load Balancer (ALB)**. 

---

## 🔗 Interesting resources

- [Containers on AWS Overview: ECS | EKS | Fargate | ECR](https://www.youtube.com/watch?v=AYAh6YDXuho)
- [Amazon Elastic Container Registry Documentation](https://docs.aws.amazon.com/ecr/)
- [Introduction to Amazon Elastic Container Registry](https://www.geeksforgeeks.org/devops/introduction-to-amazon-elastic-container-registry/)
- [Amazon Elastic Container Service Documentation](https://docs.aws.amazon.com/ecs/)
- [Amazon Elastic Container Service (ECS)](https://www.geeksforgeeks.org/devops/introduction-to-amazon-elastic-container-service-ecs/)
- [AWS Fargate for Amazon ECS](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/AWS_Fargate.html)

<div align="center">
  <a href="./13-aws-messages-events.md">◀️</a> |
</div>


<h1 align="center">
  <img src="../assets/cloud-formation.png" alt="Amazon CloudFormation" width="40px"/> 
  AWS CloudFormation
</h1>

**AWS CloudFormation** is a service that allows you to **provision and manage AWS resources using code**, following the concept of `Infrastructure as Code (IaC)`.This approach **automates** deployment, configuration, and updates of your infrastructure, ensuring consistency, repeatability, and easier management across environments (e.g., dev, test, production). 

> [!NOTE]\
> Instead of manually creating resources like [VPCs](./06-aws-vpc.md), [EC2](./07-aws-ec2.md) instances, or [S3](./05-aws-s3.md) buckets etc through the AWS Management Console, you can define them using **templates** written in **YAML** or **JSON**.

## 🔑 Key Concepts

- **Template** – A file (YAML or JSON) that defines all the AWS resources to create. 
- **Stack** – A collection of AWS resources that are created and managed as a single unit. 
- **Change Set** – A preview of changes CloudFormation will apply before execution. 
- **Parameters** – These offer an interaction during the deployment of the stack, making it easier to create and customize templates. 

### YAML Template Example

```yaml
AWSTemplateFormatVersion: 2010-09-09
Description: A sample template
Resources:
  MyEC2Instance:
    Type: 'AWS::EC2::Instance'
    Properties:
      ImageId: ami-0ff8a91507f77f867
      InstanceType: t2.micro
      KeyName: testkey
      BlockDeviceMappings:
        - DeviceName: /dev/sdm
          Ebs:
            VolumeType: io1
            Iops: 200
            DeleteOnTermination: false
            VolumeSize: 20
```

> [!NOTE]
> It defines a single resource (`AWS::EC2::Instance`) with specific properties such as instance type, AMI Image, key pair, and an Amazon EBS volume.
>
> More: [How CloudFormation works](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/cloudformation-overview.html)

---

## 🔄 Deployment Methods

You can deploy CloudFormation stacks using:

* **AWS Management Console** – Visual interface to upload templates.
* **AWS CLI / SDKs** – Automate stack creation via scripts.
* **CI/CD Pipelines** – Integrate with AWS CodePipeline or GitHub Actions for automated deployments.

Example CLI command:

```bash
aws cloudformation create-stack \
  --stack-name my-stack \
  --template-body file://template.yaml \
  --capabilities CAPABILITY_IAM
```
> [!NOTE]\
> CloudFormation uses **IAM Roles** to perform actions on your behalf.

---

<h2>
  <img src="https://skillicons.dev/icons?i=terraform" alt="Terraform"/></img>
  Terraform (Infrastructure as Code Alternative)
</h2>

**Terraform**, developed by **HashiCorp**, is an open-source **Infrastructure as Code (IaC)** tool that enables users to **define, provision, and manage cloud infrastructure across multiple providers** — including **AWS**, **Azure**, and **Google Cloud**.
> [!NOTE]\
> It uses its own declarative language called **HCL (HashiCorp Configuration Language)** to describe desired infrastructure in a human-readable way.

## 🔑 Key Concepts

- **Provider** – Defines which platform you are managing (AWS, Azure, etc.). 
- **Resource** – Specifies an infrastructure component (e.g., EC2, S3, VPC). 
- **State File** – Keeps track of existing resources to detect changes and avoid recreations. 
- **Plan & Apply** – `terraform plan` shows what will change and `terraform apply` executes it. 

---

### HCL Example Terraform

Below is a simple Terraform configuration that creates an EC2 instance on AWS:

```hcl
provider "aws" {
  region = "us-east-1"
}

resource "aws_instance" "example" {
  ami           = "ami-0abcdef1234567890"
  instance_type = "t2.micro"
}
```

> [!NOTE]
> Terraform is **multi-cloud** and **platform-agnostic**, while **CloudFormation** is **AWS-specific** and natively integrated into the AWS ecosystem.
>
> 📘 Learn more about Terraform: [Create Infrastructure](https://developer.hashicorp.com/terraform/tutorials/aws-get-started/aws-create)

---

<div align="center">

## CloudFormation vs Terraform

| **Feature**          | **AWS CloudFormation**                | **Terraform**                          |
| -------------------- | ------------------------------------- | -------------------------------------- |
| **Scope**            | AWS-specific                          | Multi-cloud (AWS, Azure, GCP, etc.)    |
| **Language**         | YAML / JSON                           | HCL (HashiCorp Configuration Language) |
| **State Management** | Managed internally by AWS             | Managed locally or via remote backends |
| **Pricing**          | Free (pay only for resources created) | Free (open-source)                     |
| **Integration**      | Deeply integrated with AWS            | Works across many providers            |

</div>

> [!NOTE]\
> CloudFormation is ideal if you are fully in the AWS ecosystem, while **Terraform** is often chosen for **multi-cloud** or hybrid environments.

---

## 🔗 Interesting resources
- [AWS CloudFormation Documentation](https://docs.aws.amazon.com/cloudformation/)
- [What is AWS Cloudformation?](https://www.geeksforgeeks.org/cloud-computing/aws-cloudformation/)
- [Introduction to Terraform](https://www.geeksforgeeks.org/devops/what-is-terraform/)

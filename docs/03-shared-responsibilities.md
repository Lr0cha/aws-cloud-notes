<div align="center">
  <h1>AWS Shared Responsibility Model</h1>
</div><br>

  This model helps reduce the operational burden on customers, since AWS manages the infrastructure up to the virtualization layer, while customers remain responsible for their applications, data, and configurations. 

- **AWS responsibility – “Security *of* the Cloud”** 
  AWS is responsible for protecting the infrastructure that runs all the services offered in the AWS Cloud. 
  This includes hardware, software, networking, and facilities that host AWS services. 

- **Customer responsibility – “Security *in* the Cloud”** 
  Customers are responsible for managing and securing what they deploy in AWS. 
  This includes the guest operating system (updates and patches), application software, configurations, identity management, and data protection. 

>[!IMPORTANT]\
>The level of responsibility also depends on the type of service (IaaS, PaaS, or SaaS). 
>For example, when using **Amazon EC2**, customers manage the OS and applications; whereas with **AWS Lambda**, AWS manages much more of the stack. 


---

![AWS Shared Responsibility Model](https://d1.awsstatic.com/onedam/marketing-channels/website/aws/en_US/product-categories/security-identity-compliance/compliance/approved/images/7a404923-5572-409c-b30e-6d44706bcd89.4ae6daa1c586799e6826be45e73950fc180a0e8c.jpeg)
> Image source: [AWS Shared Responsibility Model](https://aws.amazon.com/compliance/shared-responsibility-model/) 

<div align="center">
  <a href="./02-what-is-aws.md">◀️</a> |
  <a href="./04-aws-iam.md">▶️</a>
</div>







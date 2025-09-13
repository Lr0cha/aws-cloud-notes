<h1 align="center">
  <img src="../assets/ec2-auto-scaling.png" alt="AWS Auto Scaling" width="40px"/>  
  Amazon EC2 Auto Scaling
</h1>

**Amazon EC2 Auto Scaling** ensures your applications maintain **optimal** performance and availability by automatically **adding or removing EC2 instances** based on demand. 

> [!NOTE]\
> It **eliminates** manual scaling, reduces costs, and increases fault tolerance. 

---

## 🔑 Key concepts and features

- **Dynamic Scaling** – Automatically increase/decrease capacity based on policies, metrics, or schedules.
- **Auto Scaling Group (ASG)** – Logical group of EC2 instances **managed** together. 
- **Launch Template** – **Defines** instance type, AMI, networking, and storage. 
- **Scaling Policies** – Define **when** and **how** scaling occurs. 
- **Predictive Scaling** – Uses ML to forecast traffic patterns and scale in advance. 
- **Health Checks** – Automatically replace unhealthy instances. 
- **Fleet Management** – Maintains desired number of instances (self-healing capability). 
- **Integration** – Works with **[Load Balancer](./08-aws-elb.md), CloudWatch, ECS, RDS Aurora replicas, etc**. 

---

## Scaling Example Options

- **Target Tracking** – Keep a metric (e.g., CPU usage at 60%) at a desired level. 
- **Step Scaling** – Adjust capacity in steps based on alarm thresholds (e.g., add 2 instances if CPU > 80%). 
- **Scheduled Scaling** – Predefined scaling actions (e.g., scale out at 9AM, scale in at night). 

---

## 📊 Monitoring & Cost Optimization

- **CloudWatch Alarms** – Trigger scaling events based on metrics (CPU, requests, latency). 
- [**Elastic Load Balancing**](./08-aws-elb.md) – Distributes traffic across scaled instances for seamless availability. 
- **Rightsizing & Savings** – Reduce over-provisioning by scaling dynamically instead of fixed fleets. 

---



## 🔗 Interesting resources
- [What is Amazon EC2 Auto Scaling?](https://docs.aws.amazon.com/autoscaling/ec2/userguide/what-is-amazon-ec2-auto-scaling.html)
- [Amazon EC2 Auto Scaling](https://www.geeksforgeeks.org/devops/amazon-web-services-scaling-amazon-ec2/)
- [Tutorial: Set up a scaled and load-balanced application](https://docs.aws.amazon.com/autoscaling/ec2/userguide/tutorial-ec2-auto-scaling-load-balancer.html)

<div align="center">
  <a href="./08-aws-elb.md">◀️</a> |
  <a href="./10-aws-storage.md">▶️</a>
</div>





<h1 align="center">
  <img src="../assets/load-balancer.png" alt="AWS ELB" width="40px""/>  
  Elastic Load Balancing (ELB)
</h1>

**Elastic Load Balancing (ELB)** is a fully managed service that automatically distributes **incoming application traffic** across multiple **EC2 instances, containers**, etc within one or more **Availability Zones**. 
It improves **availability, fault tolerance, and scalability** of applications while offloading traffic management from the user. 

---

## 🔑 Key concepts and features

- **Automatic Traffic Distribution** – Dynamically balances traffic between **healthy** targets. 
- **High Availability** – Operates across multiple **Availability Zones** for fault tolerance.
- **Target groups** - Route requests to individual registered targets, such as EC2 instances, using the protocol and port number set up. 
- **Protocol Support** – Handles HTTP, HTTPS, TCP, and UDP depending on load balancer type. 
- **SSL/TLS Termination** – Offloads encryption/decryption from applications for better performance. 
- **Integration** – Works seamlessly with [**Auto Scaling Groups**]("./09-aws-asg.md"), **Route 53 (DNS)**, and **CloudWatch**. 

---

## Types of Load Balancers

- **Application Load Balancer (ALB)** – Layer 7 (HTTP/HTTPS). Supports path-based and host-based routing, can route requests to ports on one or more registered targets. 
- **Network Load Balancer (NLB)** – Layer 4 (TCP/UDP). Handles millions of requests with **ultra-low latency**. 
- **Gateway Load Balancer (GWLB)** – Deploy, scale, and manage 3rd-party virtual appliances (firewalls, IDS/IPS). 
- **Classic Load Balancer (CLB)** – **Legacy** option (Layer 4 & 7). 
> [!NOTE]\
> Mostly **replaced** by ALB/NLB. 
---

## 📊 Monitoring & Management

- **CloudWatch Metrics** – Latency, request count, healthy/unhealthy hosts. 
- **Access Logs** – Detailed request-level logs for auditing and analytics. 
- **AWS WAF** – Protect ALB apps from common exploits (SQL injection, XSS). 

---

## 🔗 Interesting resources
- [Use Elastic Load Balancing...](https://docs.aws.amazon.com/autoscaling/ec2/userguide/autoscaling-load-balancer.html)
- [Target groups for your Application Load Balancers](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/load-balancer-target-groups.html)
- [Tutorial: Set up a scaled and load-balanced application](https://docs.aws.amazon.com/autoscaling/ec2/userguide/tutorial-ec2-auto-scaling-load-balancer.html)







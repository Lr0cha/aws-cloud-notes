<div align="center">
  <h1>AWS Messaging & Event Services</h1>
</div><br>

AWS provides several messaging and event-driven services to **decouple applications**, improve scalability, and enable **event-driven architectures**. 

<div>
  <h3>
    <img src="../assets/sqs.png" alt="AWS SQS" width="25px"/>
    Amazon SQS (Simple Queue Service)</h3>
</div>

Amazon SQS is a **fully managed message queuing service** that enables decoupling of microservices and distributed systems.

> [!NOTE]\
> It processes messages through a single subscriber typically, for wider distribution integrate with Amazon SNS.

* **Types of Queues**:

  * **Standard Queue** – Designed for maximum throughput and best-effort ordering. Guarantees **at-least-once** message delivery.

> [!NOTE]\
> Does not guarantee the order of message delivery.

  * **FIFO Queue (First in First out)** – Guarantees **exact order** of messages and **exactly-once** delivery.

### Message lifecycle

![AWS SQS](https://docs.aws.amazon.com/images/AWSSimpleQueueService/latest/SQSDeveloperGuide/images/sqs-message-lifecycle-diagram.png)
> Image source: [What is Amazon Simple Queue Service?](https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/welcome.html) 

* **Some Features**:

  * **Message Retention**
  * **Asynchronous Processing** – Consumers pull messages from the queue to process them at their own pace, allowing the **producer** and **consumer** to operate independently.
  * **Visibility Timeout** – Allows you to hide messages from other consumers once they are being processed, **avoiding duplicate work**.
  * **Dead Letter Queues (DLQs)** – Store undelivered or unprocessed messages for later inspection or reprocessing.

* **Use Cases**:

  * **Microservices Decoupling** – Ensures reliable communication between decoupled components of a system.
  * **Load Buffering** – Smoothens the processing of requests during traffic spikes by storing messages temporarily in the queue.
  * **Handling Burst Traffic** – SQS allows the queue to grow and handle high volumes of messages without overwhelming the consumers.

### Example:
  Consider a large e-commerce platform where user orders trigger several backend processes. Order data is pushed into an SQS queue. A backend worker processes the orders asynchronously.

---

<div>
  <h3>
    <img src="../assets/sns.png" alt="AWS SNS" width="25px"/>
    Amazon SNS (Simple Notification Service)</h3>
</div>

SNS is a **fully managed pub/sub messaging service** that allows applications to **send** notifications to **multiple** subscribers over various communication **protocols**.

* **Publish/Subscribe Model**:

  * A **publisher** sends a message to an SNS **topic**, which acts as a logical channel for distributing the message.
  * All **subscribers** (e.g., Lambda functions, SQS queues, HTTP/S endpoints, email/SMS recipients) attached to the topic will receive the message.
  * SNS abstracts away the complexities of message delivery, ensuring seamless communication without worrying about **where** or **how** the message is delivered.

> [!NOTE]\
> Publishers need only to have the necessary permissions to publish to a topic. SNS handles the distribution and delivery mechanics across subscribed endpoints.

* **Subscribers** – Once an endpoint subscribes to a topic, it can receive notifications across the following supported protocols:

  * **Amazon SQS** queues
  * **AWS Lambda** functions
  * **HTTP/S** endpoints (custom web servers)
  * **Email** and **SMS** messages
  * **Mobile Push** notifications (e.g., to iOS, Android, Fire OS)


![AWS SNS](https://media.geeksforgeeks.org/wp-content/uploads/20240930171750/sns-delivery-protocol.webp)
> Image source: [What is Amazon SNS?](https://docs.aws.amazon.com/sns/latest/dg/welcome.html) 

* **Use Cases**:

  * **Fan-out Messaging** – Delivering one message to multiple consumers.
  * **Application Alerts** – Sending notifications about system events like server health, monitoring alerts, or application performance.
  * **Decoupling Microservices** – Trigger workflows across multiple distributed systems without directly coupling components.
  * **Serverless Applications** – Use SNS in a fully serverless environment, allowing seamless integration with AWS Lambda to trigger compute functions or with SQS to handle message queues.

### Example:
  Imagine you have an EC2 instance running critical applications. If its **CPU utilization** spikes above 90%, an **Amazon CloudWatch alarm** is triggered. The alarm sends a notification to an SNS topic, which then sends alerts to subscribers like Lambda (for further processing), SQS (for queuing tasks), or directly to system administrators via email/SMS.

---

<div>
  <h3>
    <img src="../assets/event-bridge.png" alt="AWS EVENTBRIDGE" width="25px"/>
    Amazon EventBridge</h3>
</div>

EventBridge is a **serverless event bus** that allows you to build event-driven applications by connecting different AWS services, SaaS applications, and custom applications.

> [!IMPORTANT]\
> Events can represent changes like data updates, resource state changes, or custom triggers.

EventBridge includes two ways to process and deliver events:

1. **EventBridge Bus**: A router that receives events and delivers them to zero or more targets.

> [!NOTE]\
> Well-suited for routing events from **many** sources to many targets.

2. **EventBridge Pipes** is intended for **point-to-point** integrations, so it receives events from a **single source** for **processing** and delivery to a **single target**. 

> [!NOTE]\
> Pipes and event buses are often used together.

![AWS EVENTBRIDGE](https://docs.aws.amazon.com/images/eventbridge/latest/userguide/images/service_eventbridge_conceptual.svg)
> Image source: [What Is Amazon EventBridge?](https://docs.aws.amazon.com/eventbridge/latest/userguide/eb-what-is.html)
 
* **Event Sources**:

  * **AWS Services** – Events can be triggered from a wide range of AWS services (e.g., EC2 instance state change, S3 file uploads, or AWS CodePipeline).
  * **SaaS Applications** – Third-party integrations (e.g., Zendesk, Datadog, PagerDuty) can generate events based on their activity.
  * **Custom Applications** – Developers can publish custom events from their own applications via the EventBridge API.

* **Event Routing**:

  * **Rules** – Define how incoming events are processed, filtered, and routed to one or more **targets** such as Lambda functions, Step Functions, SQS queues, SNS topics, etc.
  * **Schema Registry** – Automatically discover, catalog, and validate event schema to ensure compatibility across applications.

* **Use Cases**:

  * **Application Integration** – Integrate and automate actions across AWS services and third-party applications.
  * **Real-Time Data Processing** – Automatically respond to changes, such as updating dashboards or triggering business logic in response to new data.
  * **Serverless Orchestration** – Coordinate multiple serverless applications by triggering workflows like AWS Lambda, SQS, etc.

### Example:
  Imagine an e-commerce site that needs to track inventory changes in real-time. EventBridge can listen for **inventory updates** from an internal application and automatically trigger actions such as updating the website, adjusting stock levels, or notifying the warehouse team, all without the need for complex polling systems.

---

## Review

| Service       | Model              | Best For |
|---------------|-------------------|----------|
| **SNS**       | Pub/Sub (fan-out) | Broadcasting messages to multiple subscribers. |
| **SQS**       | Queue (point-to-point) | Decoupling producers/consumers, buffering workloads. |
| **EventBridge** | Event Bus (event routing) | Event-driven architectures, automation, integrations. |

---

## 🔗 Interesting resources
- [Amazon Simple Queue Service Documentation](https://docs.aws.amazon.com/sqs/)
- [Amazon Web Services - Simple Queue Service(SQS)...](https://www.geeksforgeeks.org/devops/aws-sqs/)
- [Amazon Simple Notification Service Documentation](https://docs.aws.amazon.com/sns/)
- [Amazon Web Services - Simple Notification Service(SNS)](https://www.geeksforgeeks.org/devops/simple-notification-service-sns-in-aws/)
- [Amazon EventBridge Documentation](https://docs.aws.amazon.com/eventbridge/)
- [AWS - Amazon EventBridge](https://www.geeksforgeeks.org/devops/aws-eventbridge/)










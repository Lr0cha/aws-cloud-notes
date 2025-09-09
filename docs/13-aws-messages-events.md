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

* **Simple Example**:
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

* **Example**:
  Imagine you have an EC2 instance running critical applications. If its **CPU utilization** spikes above 90%, an **Amazon CloudWatch alarm** is triggered. The alarm sends a notification to an SNS topic, which then sends alerts to subscribers like Lambda (for further processing), SQS (for queuing tasks), or directly to system administrators via email/SMS.

---

## 🔗 Interesting resources
- [Amazon Simple Queue Service Documentation](https://docs.aws.amazon.com/sqs/)
- [Amazon Web Services - Simple Queue Service(SQS)...](https://www.geeksforgeeks.org/devops/aws-sqs/)
- [Amazon Simple Notification Service Documentation](https://docs.aws.amazon.com/sns/)
- [Amazon Web Services - Simple Notification Service(SNS)](https://www.geeksforgeeks.org/devops/simple-notification-service-sns-in-aws/)










<h1 align="center">
  <img src="../assets/lambda.png" alt="Amazon EC2" width="40px"/>  
  Amazon Lambda
</h1>


AWS Lambda is a **serverless compute service** that lets you run code without provisioning or managing servers. 
You upload your function code, and Lambda automatically runs it **only when triggered**, scaling seamlessly from a few requests per day to thousands per second.

> [!NOTE]\
> Code runs in a server that you do not have to manage or buy.

---

## 🔑 Key concepts and features
- **Event-driven execution** – Automatically triggered by AWS services or custom events. 
- **Automatic scaling** – Each request is handled in a separate execution environment. 
- **Granular billing**
- **Integrated monitoring** – Logs and metrics available in **Amazon CloudWatch**. 
- **Built-in fault tolerance** – High availability by default across multiple AZs. 
- **Flexible resource allocation**

---

## How It Works
1. You write your code in supported languages (Node.js, Python, Java, Go, C#, Ruby, etc.). 
2. Define a **trigger** (e.g., S3 upload, API Gateway request, DynamoDB event). 
3. Lambda executes the function in a **managed environment**. 
4. You **pay only for execution time** (measured in milliseconds) and number of requests. 

> [!NOTE]\
> upload your code (as a .zip file or container image). 

---

## Common Use Cases
- **Data Processing** → Run code when files are uploaded to **Amazon S3**. 
- **APIs & Backend Services** → Integrate with **Amazon API Gateway** to build serverless REST/GraphQL APIs. 
- **Automation & Orchestration** → React to AWS events (e.g., CloudWatch alarms, DynamoDB streams). 
- **Real-time Processing** → Process data streams from **Kinesis** or **MSK**. 
- **IoT Applications** → Handle device messages and events in real-time. 

---

## 📝 Sample Example: AWS Lambda Triggered by S3 (Python)

This function runs **every time a new file is uploaded** to a specific S3 bucket. 
It logs the bucket name and object key, then uses **boto3** to fetch metadata.

```python
import json
import boto3

# Initialize S3 client
s3 = boto3.client('s3')

def lambda_handler(event, context):
    # Get bucket name and file key from event
    bucket_name = event['Records'][0]['s3']['bucket']['name']
    object_key = event['Records'][0]['s3']['object']['key']

    print(f"New file uploaded: {object_key} in bucket: {bucket_name}")

    # Fetch object metadata
    response = s3.head_object(Bucket=bucket_name, Key=object_key)
    content_type = response['ContentType']

    print(f"File content type: {content_type}")

    return {
        'statusCode': 200,
        'body': json.dumps(
            f"Processed {object_key} from {bucket_name} with content type {content_type}"
        )
    }
```
### function sample explanation:

1. The Lambda function is triggered when a new file is uploaded to an S3 bucket.
2. It extracts the bucket name and file key from the event.
3. It fetches the metadata of the file, specifically the content type.
4. It logs details about the uploaded file and its content type.
5. Finally, it returns a success message with relevant details.

> \[!IMPORTANT]
> * This function uses **boto3 (AWS SDK for Python)**.
> * The Lambda function needs an **IAM Role** with permission to access the S3 bucket, for example:

---

## 🔗 Interesting resources
- [AWS Lambda Documentation](https://docs.aws.amazon.com/lambda/)
- [Introduction to AWS Lambda](https://www.geeksforgeeks.org/devops/introduction-to-aws-lambda/)
- [Lambda sample applications](https://docs.aws.amazon.com/lambda/latest/dg/lambda-samples.html)
- [Creating event-driven architectures with Lambda](https://docs.aws.amazon.com/lambda/latest/dg/concepts-event-driven-architectures.html)


# AWS Lambda  

## What is AWS Lambda?
● AWS Lambda is a serverless compute service through which you can run your code without provisioning any Servers.  
● It only runs your code when needed and also scales automatically when the request count increases.  
● AWS Lambda follows the Pay per use principle – it means there is no charge when your code is not running.  
● Lambda allows you to run your code for any application or backend service with zero administration.  
● Lambda can run code in response to the events.  
  **Example** – update in DynamoDB Table or change in S3 bucket.  
● You can even run your code in response to HTTP requests using Amazon API Gateway.

---

## 🎯 Simple Example:
✅ **Imagine** you built a **photo app** where people upload images. You want to **automatically resize** those images into small size after upload ➔ **Lambda can do it for you without you setting up a full server!**  

✅ **Imagine** your school project wants to send a **thank you email** automatically when someone submits a contact form ➔ **Lambda can handle it easily!**

---

## What is Serverless Computing?
● Serverless computing is a method of providing backend services on a pay per use basis.  
● Serverless/Cloud vendor allows you to write and deploy code without worrying about the underlying infrastructure.  
● Servers are still there, but you are not managing them, and the vendor will charge you based on usage.

---

## 🎯 Simple Example:
✅ **Imagine** you want to play video games — you don't buy the PlayStation, you just play games in a gaming center and **pay only for the time you play**. ➔ That's what serverless is like!

---

## When do you use Lambda?
● When using AWS Lambda, you are only responsible for your code.  
● AWS Lambda manages the memory, CPU, Network, and other resources.  
● It means you cannot log in to the compute instances or customize the operating system.  
● If you want to manage your own compute resources, you can use other compute services such as EC2, Elastic Beanstalk.  
● There will be a level of abstraction which means you cannot log in to the server or customize the runtime.

---

## 🎯 Simple Example:
✅ **Think** of a **vending machine**. You put money, press a button, and it gives you a snack. You don't have to know how the machine works inside!  
Similarly, in Lambda, you just give your code, and it runs — you don’t manage the inside.

---

## How does Lambda work?
### Lambda Functions
● A function is a block of code in Lambda.  
● You upload your application/code in the form of single or multiple functions.  
● You can upload a zip file, or you can upload a file from the S3 bucket as well.  
● After deploying the Lambda function, Lambda automatically monitors functions on your behalf, reporting metrics through Amazon CloudWatch.

---

### 🎯 Simple Example:
✅ **Writing a magic spell** in a book. Later when someone says the magic word (event), the spell happens automatically (Lambda function runs).

---

### Lambda Layers
● A Lambda layer is a container/archive which contains additional code such as libraries, dependencies, or custom runtimes.  
● AWS Lambda allows five layers in a function.  
● Layers are immutable.  
● A new version will be added if you publish a new layer.  
● Layers are by default private but can be shared and made public explicitly.

---

### 🎯 Simple Example:
✅ **Think** of **ingredients** needed for a cake. If you use a Layer, you can reuse the same ingredients for many cakes without preparing them every time!

---

### Lambda Event
● Lambda Event is an entity that invokes the lambda function.  
● Lambda supports synchronous invocation of Lambda Functions.  
● Lambda supports the following sources as an event:
- AWS DynamoDB
- AWS SQS
- AWS SNS
- CloudWatch Event
- API Gateway
- AWS IoT
- Kinesis
- CloudWatch Logs

---

### 🎯 Simple Example:
✅ **Imagine** a school bell (event) rings — all students (Lambda functions) immediately start moving for the next class.  
**Event happens ➔ Lambda Function runs!**

---

## Language Supported in AWS Lambda
- NodeJS
- Go
- Java
- Python
- Ruby

---

## Lambda@Edge
● It is the feature of Amazon CloudFront which allows you to run your code closer to the location of Users of your application.  
● It improves performance and reduces latency.  
● Just like lambda, you don’t have to manage and provision the infrastructure around the world.  
● Lambda@Edge runs your code in response to the event created by the CDN.

---

## 🎯 Simple Example:
✅ **Imagine** if your friend has your video game in every city. So whenever you travel, you can instantly play without waiting for shipping.  
That's what **Lambda@Edge** does — makes code run near the user!

---

## Pricing:
- Charges will be calculated based on the number of requests for the function executed in a particular duration.  
- Duration will be counted on a per 100-millisecond basis.  
- Lambda Free tier usage includes 1 million free requests per month.  
- It also comes with 400,000 GB-Seconds of compute time per month.

---


# Difference Between EBS, EC2, and Lambda

| Feature | EC2 | Elastic Beanstalk (EBS) | Lambda |
|:--------|:---|:-------------------------|:-------|
| **What it is** | Virtual Server in the Cloud (You manage everything) | Service to easily deploy and manage your apps (It manages EC2 and other resources for you) | Serverless compute to run code without managing servers |
| **Who manages servers** | You | AWS manages (but you can still control a little) | AWS (fully) |
| **When used** | When you want full control of server (like OS, patching, etc.) | When you want easy application deployment without worrying much about servers | When you want to run code quickly without ANY servers or worry |
| **Scaling** | You manually set up scaling (or configure Auto Scaling) | Auto scaling managed by Beanstalk | Auto scaling automatic and instant |
| **Billing** | Pay for server uptime (running time) | Pay for underlying resources like EC2, ELB, etc. | Pay only when your code runs |
| **Good for** | Hosting websites, databases, applications needing full control | Web apps, APIs, background workers | Running short tasks, APIs, background processes, event-driven actions |
| **Example** | Hosting a game server you tweak yourself | Hosting a website like a school website, where AWS handles most stuff | Auto-resizing photos when students upload their profile picture |
| **Setup Complexity** | Complex (you install, update, secure everything) | Medium (upload code, choose platform, done!) | Very Simple (upload code, set trigger, done!) |

---

# 🎯 Easy-to-Remember Story:
✅ **EC2** ➔ Like owning a **full house**. You clean, maintain, and repair it yourself.  
✅ **Elastic Beanstalk** ➔ Like renting a **furnished apartment**. The owner fixes most things, you just live and decorate your room.  
✅ **Lambda** ➔ Like **ordering pizza**. You don't own the kitchen or the restaurant — you just get what you need when you need it!

---

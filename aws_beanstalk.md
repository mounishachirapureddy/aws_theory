
# AWS Beanstalk  

## What is Amazon Elastic Beanstalk?
● Beanstalk is a compute service for deploying and scaling applications developed in many popular languages.  
● Developers can focus on writing code and don’t need to worry about the underlying infrastructure required to run the application.  
● AWS Elastic Beanstalk is the best way to deploy your application in the fastest and simplest way.  
● It provides the user interface/dashboard to monitor your application.  
● It gives you the flexibility to choose AWS resources such as Amazon EC2 Instance along with the pricing options which suit your application needs.

---

## AWS Elastic Beanstalk supports two types of Environment:

### 1. Web Tier Environment
- This application hosted on the Web Server Environment handles the HTTP and HTTPS requests from the users.
- Beanstalk Environment: When an environment is launched, Beanstalk automatically assigns various resources to run the application successfully.
- Elastic Load Balancer: Request is received from the user via Route53 which forwards the request to ELB. Then ELB distributes the request among various EC2 Instances of the Auto Scaling group.
- Auto Scaling Group: Auto Scaling will automatically add or remove EC2 Instances based on the load in the application.
- Host Manager: Software components inside every EC2 Instance which is responsible for the following:  
  ▪ Log files generation  
  ▪ Monitoring  
  ▪ Events in Instance

---

#### **Real-World Examples of Web Server Environment**  
✅ **Example 1**: Building a **shopping website** like **Amazon**. People open your site and browse products. ➔ Use **Web Server**.  

✅ **Example 2**: Creating a **mobile app backend** like **Instagram API**. Mobile app talks to server to load posts. ➔ Use **Web Server**.  

✅ **Example 3**: Making a **school portal** where students log in to view homework. ➔ Use **Web Server**.

---

### 2. Worker Environment
- A worker is a background process that helps applications for handling heavy resource and time-intensive operations.
- It is responsible for database clean up, report generation that helps to remain up and running.
- In the Worker Environment, Beanstalk installs a Daemon on each EC2 Instance in the Auto Scaling Group.
- Daemon pulls requests from the SQS queue and executes the task based on the message received.
- After execution, SQS will delete the message, and in case of failure, it will retry to send the message.

---

#### **Real-World Examples of Worker Environment**  
✅ **Example 1**: In an **e-commerce website**, after people place an order, **generate an invoice PDF** and send it later by email. ➔ Use **Worker**.  

✅ **Example 2**: In a **photo-sharing app**, after uploading a photo, **resize it into small, medium, and large images** quietly. ➔ Use **Worker**.  

✅ **Example 3**: In a **news site**, **collect and email daily news updates** to all users every night. ➔ Use **Worker**.

---

## Platform Supported
- .Net (on Linux or Windows)
- Docker
- GlassFish
- Go
- Java
- Node.js
- Python
- Ruby
- Tomcat

---

## Deployment Models:

| Deployment Model | Explanation |
|:---------------|:-------------|
| **All at Once** | Deployment will start taking place in all the instances at the same time. All your EC2 Instances will be out of service for a short time. Your application will be completely down for that duration. |
| **Rolling** | Deploy the new version in batches; one group of instances will run the old version while others get updated. No complete downtime. |
| **Rolling with Additional Batch** | Deploy the new version in batches, but first create an additional group of instances temporarily to compensate for the updating ones. |
| **Immutable** | Deploy the new version to a completely new group of instances. No risk to existing running environment. |
| **Traffic Splitting** | Deploy the new version to a separate group of instances and **split the incoming traffic** between the older and the new ones, to test new version safely. |

---

## Pricing:
- Amazon will **not charge** you for AWS Elastic Beanstalk itself.
- Instead, you will be paying for the **resources** such as EC2 Instances, Elastic Load Balancer (ELB), and Auto Scaling Group where your application is hosted.

---

## 🎯 How Environment is Selected?  

**Simple Rule**:
- If you are building a **website** or **API** ➔ **Choose Web Server Environment**.
- If you are building a **background task runner** ➔ **Choose Worker Environment**.

---

## 🛑 Quick Remember Tip:
| Situation | Choose Environment |
|:---------|:-------------------|
| **People are waiting for a response** (website, app, API) | **Web Server** |
| **No one is waiting** (background work like emails, resizing, reports) | **Worker** |

---

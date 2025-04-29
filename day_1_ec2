## 1. **What is AWS EC2?**
- **EC2 (Elastic Compute Cloud)** is a core AWS service that lets you **launch and manage virtual servers** (called instances) in the cloud.
- These instances behave just like your physical computers but are **running inside AWS data centers**.
- **Elastic** means you can **easily scale up** (add more instances) or **scale down** (remove instances) **based on demand**.
- You do **NOT** need to buy and maintain expensive physical servers anymore — AWS takes care of the infrastructure.
- You have **complete control** over the instances:
  - Choose operating system (Linux, Windows, etc.)
  - Configure CPU, RAM, storage
  - Manage security settings
  - Set up networking rules.

---

## 2. **Instance Type**
- **Instance Types** are like **templates** for how powerful your server will be.
- Different workloads need different combinations of:
  - **vCPUs** (virtual CPUs)
  - **Memory (RAM)**
  - **Storage performance**
  - **Networking speed**
- AWS offers **many families** of instances for different needs:
  - **General Purpose** (balanced compute, memory) — Example: t3, m5
  - **Compute Optimized** (high CPU) — Example: c5, c6g
  - **Memory Optimized** (high RAM) — Example: r5, x1
  - **Storage Optimized** (high disk speed) — Example: i3, d2
  - **Accelerated Computing** (GPU-based) — Example: p4, inf1 (for ML, AI)

**Example:**
> If you are running a web server → use General Purpose.  
> If you are running heavy database → use Memory Optimized.

---

## 3. **EBS Volume (Elastic Block Store)**
- **EBS** is like a **hard drive** for your EC2 instance.
- It is a **block-level storage device** that attaches to your EC2.
- Even if your EC2 instance stops or crashes, the **data stored in EBS persists**.
- You can:
  - Attach multiple EBS volumes to an instance
  - Take snapshots (backups)
  - Restore volumes easily.

---

### 📦 **Types of EBS Volumes:**
| Type | Purpose | Example Use Case |
|:----|:--------|:-----------------|
| **General Purpose SSD (gp2/gp3)** | Balanced performance | Web servers, dev/test |
| **Provisioned IOPS SSD (io1/io2)** | High-performance I/O | Databases, critical apps |
| **Throughput Optimized HDD (st1)** | Large streaming workloads | Big data, log processing |
| **Cold HDD (sc1)** | Lowest cost, infrequent access | Backups |
| **Magnetic (standard)** | Older generation (rarely used) | Archival |

---

## 4. **Instance Store**
- **Instance Store** = **Temporary storage** that exists **only as long as the instance is running**.
- Data **disappears** when the instance stops, crashes, or is terminated.
- **Faster** than EBS because it's **physically attached** to the host server.
- Good for:
  - Temporary files
  - Buffer/cache
  - Scratch data

**Important:** Never store important data on instance store unless you are OK losing it.

---

## 5. **AMI (Amazon Machine Image)**
- **AMI** is like a **blueprint/template** for launching EC2 instances.
- It contains:
  - Operating system (e.g., Ubuntu, Windows Server)
  - Installed applications (like Apache, MySQL)
  - Any required libraries, files, configurations.
- You can create a **custom AMI** once you set up an instance perfectly, and then launch **many instances with identical settings** later.

**Example:**
> You configure a web server with your website files.  
> You create an AMI from that instance.  
> Later, you launch 5 new instances instantly from the AMI without reconfiguring.

---

## 6. **Security Group**
- **Security Group** = **Virtual firewall** that controls traffic **into** and **out of** EC2 instances.
- It controls:
  - **Inbound Rules** (who can send traffic to the instance)
  - **Outbound Rules** (who the instance can send traffic to)
- **Key Features:**
  - **Stateful**: If a connection is allowed in, return traffic is automatically allowed.
  - **Only allows** rules (no explicit deny).
- **Common Rules:**
  - Allow SSH (port 22) to connect to Linux servers
  - Allow HTTP (port 80) for websites
  - Allow HTTPS (port 443) for secure websites

**Tip:** Always restrict access by IP address wherever possible (for security).

---

## 7. **Key Pair**
- AWS uses **Key Pairs** for **securely logging** into EC2 instances.
- A Key Pair consists of:
  - **Public Key** (stored in the EC2 instance)
  - **Private Key** (downloaded and kept safe by you)
- When you SSH into your instance, AWS verifies that your private key matches the public key stored inside the instance.
- If you **lose the private key**, you **cannot** access the instance unless you rebuild it!

**Tip:** Always download the `.pem` file (private key) when creating an instance and store it safely.

---

## 8. **Tags**
- **Tags** = **Labels** (Key-Value Pairs) that you can assign to AWS resources.
- Examples of tags:
  - `Environment: Production`
  - `Project: WebApp`
  - `Owner: JohnDoe`
- **Benefits of using Tags:**
  - Easy resource management
  - Better billing breakdown (cost allocation)
  - Automation (scripts can search by tags)

**Example:** You can find and shut down all instances tagged with `Environment: Test` when not needed.

---

## 9. **Pricing**
AWS EC2 gives you **flexible pricing options** depending on how you plan to use it:

| Pricing Model | Details | Best For |
|:--------------|:--------|:---------|
| **On-Demand** | Pay per second/hour, no commitment. | Short-term, unpredictable workloads. |
| **Savings Plan** | Commit to a 1 or 3-year usage. Big discount (~30-70%). | Steady workloads. |
| **Reserved Instances** | Pay upfront for 1 or 3 years. | Applications that run all the time (like servers). |
| **Spot Instances** | Use spare AWS capacity at 90% discount. Can be terminated anytime. | Batch processing, fault-tolerant apps. |


---
# ✅ Summary

- EC2 = AWS Virtual Machine Service  
- EBS = Persistent storage  
- Instance Store = Temporary fast storage  
- AMI = Machine blueprint  
- Security Group = Instance firewall  
- Key Pair = Secure SSH login  
- Tags = Resource labeling  
- Pricing = Flexible based on needs


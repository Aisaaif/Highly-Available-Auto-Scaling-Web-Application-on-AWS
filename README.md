
# 🚀 Highly Available Auto Scaling Web Application on AWS

> A production-style AWS architecture that automatically scales, balances traffic, and sends real-time alerts under load.

![AWS](https://img.shields.io/badge/AWS-Cloud-orange)
![DevOps](https://img.shields.io/badge/Role-DevOps-blue)
![Linux](https://img.shields.io/badge/Linux-System%20Admin-green)

---

<img width="1536" height="1024" alt="ChatGPT Image Apr 11, 2026, 02_01_46 PM" src="https://github.com/user-attachments/assets/8c0195f7-c7d3-4ac5-8a88-cc13247406a7" />
This architecture ensures high availability, fault tolerance, and automatic scaling based on real-time demand.

## 📌 Overview

Designed and implemented a highly available and auto-scaling web application architecture on AWS that dynamically adjusts infrastructure based on demand while ensuring reliability, monitoring, and real-time alerting.
---

## 🚀 Key Features

- High Availability using Load Balancer  
- Dynamic scaling with Auto Scaling Group  
- Real-time monitoring using CloudWatch  
- Alert notifications using SNS  
- Automated deployment using bootstrapping  

---

## 🎯 Real-World Scenario

Simulated a production-like environment where a web application must handle varying traffic loads while maintaining uptime and sending alerts for system events.

---

## 🧱 Architecture

User → Application Load Balancer → Auto Scaling Group → EC2 Instances
CloudWatch monitors CPU → triggers scaling → SNS sends alerts

---

## 🔧 Services Used

* EC2 (Elastic Compute Cloud)
* Auto Scaling Group (ASG)
* Launch Template
* Application Load Balancer (ALB)
* CloudWatch (Monitoring & Alarms)
* SNS (Notifications)

---

## ⚙️ Implementation

### 1. Launch Template

* Configured EC2 instance with Amazon Linux
* Added User Data for bootstrapping web server

### 2. Bootstrapping (User Data)

```bash
#!/bin/bash
yum update -y
yum install httpd -y
systemctl start httpd
systemctl enable httpd

echo "<h1>Welcome from Auto Scaling Instance</h1>" > /var/www/html/index.html
```

### 3. Load Balancer

* Created Application Load Balancer
* Attached Target Group

### 4. Auto Scaling Group

* Min: 1 | Desired: 1 | Max: 3
* Attached to Load Balancer

### 5. CloudWatch Alarms

* CPU > 70% → Scale Out
* CPU < 30% → Scale In

### 6. SNS Integration

* Configured email notifications
* Alerts for:

  * High CPU
  * Instance launch
  * Instance termination

---

🧠 Approach  

- Designed a scalable architecture using AWS services  
- Automated EC2 setup using user data (bootstrapping)  
- Configured monitoring and alerting for system visibility  
- Simulated load to validate auto scaling behavior  

---

## 🧪 Testing

Simulated high CPU load using:

```bash
stress --cpu $(nproc)
```

Observed:

* CloudWatch alarm triggered
* New EC2 instance launched
* SNS notification received

---

## 📸 Screenshots

🔹 Load Balancer Serving Traffic  
<img width="1920" height="1080" alt="Load Balancer Serving Traffic.png" src="https://github.com/user-attachments/assets/5b33f07d-b24d-4876-a64b-e4dede6f206c" />
🔹 CloudWatch Alarm Triggered
<img width="1920" height="1080" alt="CloudWatch Alarm Triggered.png" src="https://github.com/user-attachments/assets/63845d1e-829f-42b9-8562-de3db51481ed" />
🔹 Auto Scaling Activity
<img width="1920" height="1080" alt="Auto Scaling Activity.png" src="https://github.com/user-attachments/assets/218501b4-36c7-41c8-83f3-5d74feb32f21" /> 
🔹 Multiple EC2 Instances Running
<img width="1920" height="1080" alt="Multiple EC2 Instances Running.png" src="https://github.com/user-attachments/assets/5a583fc8-15ab-4d28-94fd-9808e190e429" />
🔹 Health Check On Target Groups
<img width="1920" height="1080" alt="Health Check On Target Groups.png" src="https://github.com/user-attachments/assets/1f75447d-47ba-47da-a78f-701d2509de51" />
🔹 SNS Notification Received
<img width="1920" height="1080" alt="SNS Notification Received.png" src="https://github.com/user-attachments/assets/fc22cc02-25be-4155-a90d-22eb455ec078" />

---

## 📈 Outcome

Successfully implemented a scalable and highly available web application infrastructure that automatically responds to traffic changes using monitoring, scaling, and alerting mechanisms.

---

## 💡 Key Learnings

- Designing scalable and fault-tolerant architectures on AWS  
- Implementing dynamic infrastructure using Auto Scaling  
- Monitoring system performance using CloudWatch  
- Integrating alerting systems using SNS  
- Automating deployments using bootstrapping techniques  

---

## 🌍 Real-World Relevance

This project demonstrates how modern cloud applications handle traffic spikes, maintain high availability, and automatically scale infrastructure based on demand without manual intervention.

---
## 🔗 Connect www.linkedin.com/in/mohammedsaifali18

If you found this useful, feel free to connect with me on LinkedIn.

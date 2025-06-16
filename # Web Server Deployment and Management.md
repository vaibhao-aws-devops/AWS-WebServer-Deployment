# Web Server Deployment and Management using AWS Services

This project demonstrates the deployment of a scalable and fault-tolerant web server infrastructure using AWS.

---

## 🔧 AWS Services Used

- Amazon EC2
- Amazon Machine Image (AMI)
- Elastic Load Balancer (ELB)
- Auto Scaling Group
- Amazon CloudWatch
- SNS (Simple Notification Service)
- IAM
- Amazon S3 (optional)

---

## 🧩 Architecture Diagram

![Architecture Diagram](screenshots/architecture-diagram.png)

---

## 📘 Step-by-Step Implementation

1. Launch EC2 and install Apache web server.
2. Create AMI of EC2.
3. Set up ELB and Target Group.
4. Create SNS topic and subscription.
5. Create Launch Template using AMI.
6. Configure Auto Scaling (Min=1, Max=5, CPU > 30%).
7. Attach CloudWatch Alarm to Auto Scaling policy.
8. Test using stress tool and monitor using top/CloudWatch.

---

## ✅ Project Outcomes

| Test | Result |
|------|--------|
| Load test (stress tool) | ✅ Auto Scaling triggered |
| ELB traffic | ✅ Load Balanced |
| CPU alert | ✅ Email via SNS |
| EC2 termination | ✅ Instance replaced |

---

## 📄 Report

📎 [`Final__AWS_Project_Report_Vaibhao.pdf`](Final__AWS_Project_Report_Vaibhao.pdf)

---

## 👨‍💻 Author

**Vaibhao Yenchalwar**

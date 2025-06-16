# 🛠️ AWS Web Server Setup - Step-by-Step

## Step 1: Launch EC2 Instance
- Type: t2.medium
- Storage: 10 GB
- OS: Amazon Linux
- Install Apache: `sudo yum install httpd -y`

## Step 2: Create AMI of EC2
- Create Image → Name it → Use for Launch Template

## Step 3: Create Target Group
- Type: Instance
- Protocol: HTTP
- Health check path: `/`

## Step 4: Create Application Load Balancer
- Internet-facing, IPv4
- HTTP listener on port 80
- Attach to Target Group
- Allow HTTP traffic in Security Group

## Step 5: Create SNS Topic & Email Subscription
- Topic: EC2Alerts
- Add your email
- Confirm subscription from email

## Step 6: Create Launch Template
- Use AMI created in Step 2
- Instance type: t2.medium
- Configure security group

## Step 7: Create Auto Scaling Group
- Use Launch Template
- Connect to Target Group
- Desired = 1 | Min = 1 | Max = 5
- Add CPU scaling policy (CPU > 30%)

## Step 8: Create CloudWatch Alarm
- Condition: CPUUtilization > 30% for 1 minute
- Action: Trigger Auto Scaling + SNS Email

## Step 9: Connect to EC2 via Git Bash
- SSH with `.pem` key
- Install stress tool:
  ```
  sudo yum install stress -y
  stress --cpu 2 --timeout 300
  ```

## Step 10: Monitor Auto Scaling
- Launch new instance if load increases
- Terminate instances if load reduces
- Get email alert from SNS
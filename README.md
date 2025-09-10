# Setting Up a Cloud Server

**Name:** Thien Nguyen  
**Date:** 4/30/2025  

---

## 📖 Introduction
In this lab, I created a virtual machine (VM) in the cloud and connected to it using SSH.  
This process helps us understand how cloud services work and prepares us to set up a honeypot in the next lab.  

---

## 🛠 Breakpoints

### 🔹 Breakpoint 1 – Creating an AWS Account
- I registered for a **free Amazon Web Services (AWS) account** using my personal email.  
- I selected the **AWS Free Tier**, which provides limited resources like EC2 instances, S3 storage, and IAM access at no cost for one year.  
- This step ensured I had the necessary access to cloud services for the lab without financial risk.  

### 🔹 Breakpoint 2 – Securing the Root Account
- I protected the AWS **root account** by setting up **Multi-Factor Authentication (MFA)** using the Duo Mobile app.  
- After linking the QR code with my account, every login required approval on my phone, adding strong protection against unauthorized access.  
- I also configured **Free Tier usage alerts** in the AWS Billing Console. This ensured that if I approached free tier limits, I would get an email warning before charges occurred.  

### 🔹 Breakpoint 3 – Configuring IAM Users and Permissions
- Instead of using the root account for daily operations, I created a **user group** and a dedicated **IAM Identity Center user**.  
- I enabled **MFA** for this user to maintain strong security.  
- Next, I created a **custom permission set** with the `AmazonEC2FullAccess` policy, giving the user full access to EC2 resources.  
- I configured the session timeout to **4 hours**, limiting the time a user stays logged in to reduce potential risks.  
- Finally, I assigned this permission set to my user group, ensuring all members could safely launch and manage EC2 instances without needing root privileges.  

### 🔹 Breakpoint 4 – Launching a Virtual Machine (EC2 Instance)
- I launched an **EC2 instance** using the **Ubuntu Server 22.04 LTS** image, which is widely used for cloud deployments.  
- For cost efficiency, I chose the **t2.micro** instance type, included in the AWS Free Tier.  
- I created a new **RSA key pair** (in `.pem` format), which is essential for secure SSH connections.  
- I downloaded the key to a safe location on my computer, since AWS only provides it once and it is required for authentication.  

### 🔹 Breakpoint 5 – Connecting to the Instance via SSH
- Using the `.pem` key file, I opened a terminal on my local machine to establish a secure SSH session.  
- I carefully followed AWS’s official instructions to adjust file permissions for the key and run the SSH command:  

```bash
ssh -i "my-key.pem" ubuntu@<public-ip-address>

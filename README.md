# Lab 07 – Setting Up a Cloud Server

**Name:** Thien Nguyen  
**Course/Section:** IS-3033  
**Date:** 4/30/2025  

---

## 📖 Introduction
In this lab, we created a virtual machine (VM) in the cloud and connected to it using SSH.  
This process helps us understand how cloud services work and prepares us to set up a honeypot in the next lab.  

---

## 🛠 Breakpoints

### 🔹 Breakpoint 1
- Signed up for a free account with **Amazon Web Services (AWS)** using the AWS Free Tier.  

### 🔹 Breakpoint 2
- Secured the AWS root account by enabling **Multi-Factor Authentication (MFA)** with the Duo Mobile app.  
- Set up **Free Tier usage alerts** in the Billing and Cost Management Console to prevent accidental charges.  

### 🔹 Breakpoint 3
- Created a **user group and user** in the AWS IAM Identity Center instead of using the root account.  
- Enabled **MFA** for the new user.  
- Created a custom permission set using the `AmazonEC2FullAccess` policy.  
- Set the session timeout to **4 hours**.  
- Assigned the permission set to the user group, allowing safe EC2 management without the root account.  

### 🔹 Breakpoint 4
- Launched an **EC2 instance** on AWS using the **Ubuntu Server 22.04 LTS** image.  
- Selected the **t2.micro** instance type (covered by Free Tier).  
- Created and downloaded a new **RSA key pair (.pem)** for SSH authentication.  

### 🔹 Breakpoint 5
- Tested **SSH access** to the EC2 instance from a local machine using the `.pem` key.  
- Successfully connected via terminal following AWS instructions.  

---

## ✅ Conclusion
In this lab, I learned how to deploy and manage a cloud-based virtual machine using AWS, which improved my understanding of **cloud infrastructure and security practices**.  

Challenges I faced included:
- Navigating **IAM Identity Center** and setting permissions for non-root users.  
- Setting up **secure SSH access** to the EC2 instance.  

By carefully following the lab guide and AWS documentation, I resolved these challenges. These skills will be valuable for:  
- Managing cloud servers  
- Deploying secure applications  
- Preparing for more advanced labs such as honeypot deployment  

---

## 👥 Collaboration
I worked **entirely alone**.  

---

## 📜 License
This project is for educational purposes only.  

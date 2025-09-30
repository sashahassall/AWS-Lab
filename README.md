# AWS Architecture Lab


## Overview
This project includes a secure 2-tier AWS lab with web and database tiers, VPC isolation, IAM-based S3 access controls, and monitoring/logging.  
It simulates a production-style setup with a **web tier** (public subnet) and a **database tier** (private subnet).  

---



## Architecture Diagram
<img width="1029" height="1150" alt="Screenshot 2025-09-29 134453" src="https://github.com/user-attachments/assets/0883de80-15db-49e5-9507-e90f7f70eead" />


The diagram shows a VPC with public/private subnets.  
- **Public Subnet:** Bastion host + Nginx web server  
- **Private Subnet:** MySQL database (accessible only from the web server)  
- **Security Groups:** Enforce least privilege (e.g., port 3306 only from Web SG)  
- **Monitoring/Logging:** CloudWatch alarms and CloudTrail audit logs  

---

## Tech Stack
- **AWS Services:** VPC, EC2, Security Groups, S3, IAM, CloudWatch, CloudTrail  
- **Application Stack:** Nginx web server (public subnet) + MySQL database (private subnet)  
- **Operating Systems:** Amazon Linux, Ubuntu  

---

## Key Features
- Isolated web and database tiers using VPC subnets  
- Bastion host for secure SSH access into private resources  
- Security groups designed with principle of least privilege  
- CloudWatch alarms and CloudTrail logs for monitoring and auditing  

---

## Key Takeaways

  - Gained experience with cloud infrastructure design and security best practices
  - Learned how to implement least privilege using security groups and IAM roles
  - Recognized the importance of monitoring and logging within cloud environments
  - Practiced configuring and troubleshooting connectivity between public and private subnets  

---

## Screenshots & Config Files

For the full step-by-step process with screenshots, see the [Walkthrough & Screenshots guide](./Walkthrough%20&%20Screenshots/ReadME.md).

For examples of configuration files from my lab, visit the [Configs] folder. 

---

## Possible Future Improvements 
- Adding a WAF for web protection  
- Automating setup with Terraform
- Become AWS Certified
  
**I know that this is only a first step in learning how to build and secure cloud environments, however, this project gave me inspiration to continue exploring cloud security and developing my knowledge and skills.**


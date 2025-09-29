## Screenshots / Walkthrough

### 1. VPC & Subnets
- Created a VPC with isolated public and private subnets.
- Attached an Internet Gateway & defined route tables to direct traffic 
 

 <img width="2996" height="559" alt="Screenshot 2025-09-27 210448" src="https://github.com/user-attachments/assets/8330fc4b-9417-4719-8d2c-e48d0821b71a" />

<img width="3010" height="494" alt="Screenshot 2025-09-27 210105" src="https://github.com/user-attachments/assets/063a1601-7ade-45a8-94cc-b8875e3d1bcf" />


### 2. Deploy EC2 Instances  
- Launched a **public EC2 instance (Ubuntu)** to serve as the web server and a **private EC2 instance** for the database tier  

<img width="2996" height="559" alt="Screenshot 2025-09-27 210448" src="https://github.com/user-attachments/assets/29b98e9d-09da-4201-b958-3d01fae16b4f" />




### 3. Configure Security Groups  
- **Web Server SG:** Allowed inbound HTTP/HTTPS from the internet, SSH restricted to my IP  
- **Database Server SG:** Allowed inbound MySQL (Port 3306) traffic only from the Web Server SG
<img width="2839" height="705" alt="Screenshot 2025-09-27 210540" src="https://github.com/user-attachments/assets/de7907ce-2cfe-4074-b736-83d922df986c" />


 

### 4. Configure Bastion Host  
- Set up a bastion host in the public subnet as a secure entry point for SSH 
The bastion host provides controlled access, without exposing private EC2 instances directly to the internet, which reduces the attack surface.  



### 5. Web Server Setup (Public Subnet)  
- Updated key file permissions locally for secure SSH  
- Connected to the web server EC2 instance  
- Installed **Nginx** and verified it was running
<img width="2576" height="874" alt="Screenshot 2025-09-27 210800" src="https://github.com/user-attachments/assets/b8127924-20fe-4421-bfe0-ec071ffa9844" />




### 6. Database Server Setup (Private Subnet)  
- Installed **MySQL** on the private EC2 instance
-  Created a MySQL database and user for testing  
- Verified connectivity between the **web server** and **database server**
Hosting the database in a private subnet makes it so that it is not publicly accessible, which reduces exposure and allows controlled access from the web server. 

<img width="2222" height="799" alt="Screenshot 2025-09-27 211258" src="https://github.com/user-attachments/assets/0a0f47cc-6c7e-4527-b3fb-451d0c6eb8b7" />


### 7. Configure S3 Bucket  
- Created an S3 bucket for secure storage  
- Applied bucket policies to restrict public access and enabled SSE-S3 encryption to protect data at rest

<img width="2396" height="661" alt="Screenshot 2025-09-28 190533" src="https://github.com/user-attachments/assets/20d0ff92-fcc3-4226-a53d-3a64341d0961" />
<img width="3577" height="657" alt="Screenshot 2025-09-28 193207" src="https://github.com/user-attachments/assets/351c2f14-ef94-43eb-bc2a-d613b31f64d4" />


### 8. Configure IAM  
- Created IAM roles for EC2 instances  
- Attached least-privilege policies for accessing S3 and CloudWatch  
- **Why:** Using IAM roles improves security by managing permissions centrally and avoiding hardcoded credentials  
<img width="2777" height="266" alt="Screenshot 2025-09-28 190917" src="https://github.com/user-attachments/assets/16696588-3e52-4cbb-93b2-9a0286020774" />
<img width="978" height="403" alt="Screenshot 2025-09-28 191146" src="https://github.com/user-attachments/assets/20b7166d-c020-4a87-a0d0-92ac0c77a216" />


---

### 9. Monitoring & Logging  
- Enabled **CloudWatch alerts** for EC2 CPU utilization  
- Configured **CloudTrail** to log API activity for auditing  
Together, CloudWatch and CloudTrail provide performance monitoring and logging which is important because it allows us to check on the system's health and security.
<img width="2915" height="1358" alt="Screenshot 2025-09-28 193845" src="https://github.com/user-attachments/assets/ae5e2d91-8150-4830-b849-17eb4b302280" />
<img width="3687" height="969" alt="Screenshot 2025-09-28 194244" src="https://github.com/user-attachments/assets/683e954f-0f41-4ec0-842a-c83385713166" />
<img width="2948" height="1095" alt="Screenshot 2025-09-28 185939" src="https://github.com/user-attachments/assets/5f07359c-a21b-4973-9d37-c57351f2e13e" />




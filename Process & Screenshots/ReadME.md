## Screenshots / Walkthrough

### 1. VPC & Subnets
- Created a VPC with isolated public and private subnets.
- 


 

<img width="3046" height="396" alt="Screenshot 2025-09-27 205850" src="https://github.com/user-attachments/assets/e459be8d-8b9d-4ca9-8dd6-492092d4d7f4" />
<img width="3010" height="494" alt="Screenshot 2025-09-27 210105" src="https://github.com/user-attachments/assets/063a1601-7ade-45a8-94cc-b8875e3d1bcf" />


### 2. Security Groups
Configured least privilege — MySQL traffic only allowed from the Web SG.  
![Security Groups](./screenshots/security-groups.png)


### 3. Bastion Host Access
SSH into the bastion, then into the private database instance.  
![Bastion SSH](./screenshots/bastion-ssh.png)

### 4. Monitoring & Logging
Configured CloudWatch alarms and enabled CloudTrail for auditing.  
![CloudWatch Alarm](./screenshots/cloudwatch-alarm.png)
![CloudTrail Event](./screenshots/cloudtrail-event.png)

# AWS Configurations  

This folder has a few examples of AWS config files that I exported and sanitized from this project. Here's a quick breakdown: 


- **webserver-sg.json**  
Security Group for the web server that shows rules for HTTP/HTTPS and restricted SSH. 

- **database-sg.json**  
  Security Group for the database. Only allows MySQL traffic from the WebServer SG.  

- **webserver-iam-role.json**  
  IAM role attached to the Web Server EC2 Instance. 

- **cloudwatch-alarm.json**  
  CloudWatch alarm monitoring CPU Utilization on the web server instance, set to trigger above 70%.  

These configuration snippets demonstrate some of the hands-on learning I was able to do through this project. I gained experience with:   
- Network security (least privilege using Security Groups)  
- Identity and access management (IAM roles & policies)  
- Monitoring and logging (CloudWatch alarms)  

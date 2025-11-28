# Pramod Kalangi – AWS Day 7: High Availability Web App with ALB + Auto Scaling (Manual Setup)
#Pramod Kalangi - AWS Day 7: High Availability Web App with ALB + Auto Scaling (Manual Setup)/README.md

**Status: COMPLETED & LIVE 🔥**

## Live URL
**http://pramodkalangi-alb-729340518.ap-south-1.elb.amazonaws.com/**  
(Refresh multiple times → shows different instance hostname → proves load balancing across 2 AZs)

## Architecture

<img width="937" height="847" alt="ARCHITECTURE DIAGRAM" src="https://github.com/user-attachments/assets/3bec2186-8822-4223-b592-4697265d404c" />

- Multi-AZ Application Load Balancer
- 2 EC2 instances (t3.micro, Amazon Linux 2023) in **public subnets** across **ap-south-1a & 1b**
- Apache running on port 80
- Target Group with health checks on `/`
- Security Group: HTTP 80 open to 0.0.0.0/0

## Proof Screenshots
1. ALB page loading with name<img width="1920" height="1200" alt="ALB DNS" src="https://github.com/user-attachments/assets/5a436f01-1130-48c2-8915-aac90ea3609b" />

2. Target Group → 2 Healthy targets<img width="1920" height="1200" alt="TARGET GROUPS" src="https://github.com/user-attachments/assets/1781b237-cdcc-46a8-87b1-d8ec81a2aec6" />

3. ALB spanning 2 Availability Zones<img width="1920" height="1200" alt="LOAD BALANCER LISTENER" src="https://github.com/user-attachments/assets/bbe3e769-b02d-42bc-9b43-52f787053332" />

4. Instances in different AZs<img width="1920" height="1200" alt="EC2 INSTANCES" src="https://github.com/user-attachments/assets/5e02c3b2-617d-49cd-90a9-266e60445ef8" />

5. Security Group rules<img width="1920" height="1200" alt="SECURITY GROUP" src="https://github.com/user-attachments/assets/8917bc03-3176-425f-8c55-c6c8741abcd6" />

6. Public subnets with IGW route<img width="1920" height="1200" alt="VPC SUBNETS" src="https://github.com/user-attachments/assets/70901dcf-18ab-4d6f-95de-d850248f8b89" />

7. Fleet manager <img width="1920" height="1200" alt="FLEET MANAGER" src="https://github.com/user-attachments/assets/00369634-229c-4d0b-8886-75816d75d9cf" />

8. Load balancer <img width="1920" height="1200" alt="LOAD BALANCER" src="https://github.com/user-attachments/assets/4e87dd26-6426-42dc-9f40-ac306c0143ca" />

9. Load Balancer Listener <img width="1920" height="1200" alt="LOAD BALANCER LISTENER" src="https://github.com/user-attachments/assets/a1b5be65-0aca-48e4-a081-2378bc8f2ba6" />


## What I Learned
- Why targets go unhealthy (no HTTP rule, no web server, wrong health path)
- Difference between public/private subnets
- How ALB distributes traffic across AZs
- Manual setup when ASG bugs out (real-world clutch move)

**Day 7/60 Complete – Pramod Kalangi**  
Next: Auto Scaling + Launch Template + Proper Scaling Policies

#NeverQuit #AWSGrind #Day7Dead

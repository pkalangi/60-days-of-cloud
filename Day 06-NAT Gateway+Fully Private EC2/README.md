# Day 06 – NAT Gateway + Fully Private EC2


**Date:** 27 Nov 2025

### What I Built
- NAT Gateway in public subnet with Elastic IP
- Private route table: 0.0.0.0/0 → NAT (internet for private subnets)
- EC2 instance in private subnet with NO public IP
- 3 VPC Endpoints (SSM, SSMMessages, EC2Messages) → Session Manager works
- IAM role with AmazonSSMManagedInstanceCore attached
- Proved: `yum update` works + outbound internet via NAT only

### Key Learnings
- Private instances can update packages without being exposed
- Session Manager = no SSH keys, no bastion hosts
- This is REAL production architecture (databases, workers, etc.)

### Architecture
![Diagram]<img width="1008" height="911" alt="ARCHITECTURE" src="https://github.com/user-attachments/assets/ac9a1d2b-3bee-42b5-994c-ea63bbddb978" />


### Screenshots
<img width="1920" height="1200" alt="NAT-GATEWAY" src="https://github.com/user-attachments/assets/e609cffb-9bdc-4f3d-a264-2388405312ba" />
<img width="1920" height="1200" alt="PRIVATE-ROUTE-TABLE" src="https://github.com/user-attachments/assets/efb34a68-397b-445b-a471-0baf711d5fde" />
<img width="1920" height="1200" alt="PRIVATE-EC2-NO-PUBLIC-IP" src="https://github.com/user-attachments/assets/08feb0c9-a07c-412c-bfb5-1fa861bc6838" />
<img width="1920" height="1200" alt="VPC ENDPOINTS" src="https://github.com/user-attachments/assets/359e69f7-b38c-43e6-ac47-e8f54a469b7d" />
<img width="1920" height="1200" alt="YUM-UPDATE-WORKING" src="https://github.com/user-attachments/assets/34d5a431-521e-4be9-8f90-aea1f8874ec9" />


Next → Day 07: Load Balancer + Auto Scaling

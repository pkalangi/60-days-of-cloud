# Day 05 – Production-Grade Custom VPC
#Day 05-Production-Grade CustomVPC/README.md

**Date:** 26 Nov 2025

### What I Built
- Custom VPC (10.0.0.0/16)
- 2 Public subnets + 2 Private subnets across Mumbai AZs
- Internet Gateway attached
- Public route table with default route to IGW
- Private subnets isolated (no direct internet)

### Why It Matters
This is the exact architecture 99% of companies use in real life.

### Architecture
![Diagram]<img width="1011" height="815" alt="ARCHITECTURE DIAGRAM" src="https://github.com/user-attachments/assets/9f60e3d5-5592-4c1b-8cd9-7221cbdba895" />


### Screenshots
<img width="1920" height="1200" alt="VPC CREATED" src="https://github.com/user-attachments/assets/5cb5031b-87c9-4bd3-9347-3c619499a2f5" />
<img width="1920" height="1200" alt="ALL SUBNETS" src="https://github.com/user-attachments/assets/8480c2e1-f282-466a-b84d-e1a38dcd2030" />
<img width="1920" height="1200" alt="IGW ATTACHED" src="https://github.com/user-attachments/assets/15413046-afc9-4175-add6-bbb36d1c1ba9" />
<img width="1920" height="1200" alt="ROUTE TABLE" src="https://github.com/user-attachments/assets/91db5110-2098-4038-9971-4c8bf9c428a8" />


Next → Day 06: NAT Gateway + Private EC2

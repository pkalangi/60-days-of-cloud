# Day 08/60 — AWS Auto Scaling + ALB + High Availability Web App

**Goal:** Build a fully auto-scaling web application that survives traffic spikes automatically.

### Architecture Built
- Custom VPC + 2 public subnets (Day 5 foundation)
- Application Load Balancer (ALB) across 2 AZs
- Auto Scaling Group (Min 2 → Max 5) with Target Tracking (CPU)
- Launch Template + User Data (Apache + stress tool)
- Session Manager (no SSH keys)
- Health checks, public IPs, grace period — all fixed

### Proof It Works (Live Screenshots)
1. `alb-page.png` → ALB DNS showing my name + different hostnames on refresh
<img width="1920" height="1200" alt="ALB DNS1" src="https://github.com/user-attachments/assets/f3b67f5b-1d39-4002-9a83-7a6c3eb3db8a" />
<img width="1920" height="1200" alt="ALB DNS2" src="https://github.com/user-attachments/assets/263bcbf0-8c75-4453-b066-b2ec8aa16052" />
<img width="1920" height="1200" alt="ALB DNS3" src="https://github.com/user-attachments/assets/bf8348af-907a-484f-b60b-9fab53cc5d1c" />


2. `2-healthy-targets.png` → Target Group with 2 healthy instances
   <img width="1920" height="1200" alt="TG" src="https://github.com/user-attachments/assets/1db6d5fb-42bc-4791-bd28-32f41f9a9935" />

3. `asg-3-instances.png` → Auto Scaling Group showing 3 running instances
  <img width="1920" height="1200" alt="ASG" src="https://github.com/user-attachments/assets/fb22a28c-2a63-475d-ada4-6b26b05e5288" />

4. `activity-3rd-instance.png` → ASG Activity log → "Successfully launched instance" (the 3rd one)
  <img width="1920" height="1200" alt="ASG ACTIVITY" src="https://github.com/user-attachments/assets/036255ba-559a-45d1-b9c8-8469b2aff237" />

5. `scaling-policy.png` → Target tracking policy (CPU utilization)
  <img width="1920" height="1200" alt="POLICY" src="https://github.com/user-attachments/assets/45e69c60-1dd2-4a05-a4df-1df140ea64a7" />

6. `cpu-spike-monitoring.png` → EC2 Monitoring tab → one instance at 100% CPU
   <img width="1920" height="1200" alt="CPU SPIKE" src="https://github.com/user-attachments/assets/f3ffb51c-2895-4a78-b9d0-83fb0f6185f3" />

7. `stress-command.png` → Session Manager terminal running `stress --cpu 8`
    <img width="1920" height="1200" alt="SESSION MANAGER" src="https://github.com/user-attachments/assets/48173ed5-36c9-4897-914f-d511e065b01e" />


### How I Triggered Auto-Scaling
→ Connected via Session Manager → ran `stress --cpu 8`  
→ CPU spiked to 100% → ASG detected breach → auto-launched 3rd instance in under 3 minutes  
→ ALB started sending traffic to all 3 servers

### Key Fixes Applied (Real-World Debugging)
- Enabled auto-assign public IPv4 in subnets
- Health check success code 200 only
- Added KMS decrypt permission for Session Manager
- Grace period + deregister trick for unhealthy targets

**Status: 100% LIVE & AUTO-SCALING**  
Next → Day 9: Terraform this entire setup in 1 command

#60DayAWSChallenge #AWS #CloudEngineer #DevOps #AutoScaling #ALB

8/60 → MURDERED AFTER 3 DAYS OF WAR 🔥

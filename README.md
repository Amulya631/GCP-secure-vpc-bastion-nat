🚀 Secure GCP VPC with Public & Private Subnets
📌 Overview

This project demonstrates the design and implementation of a secure Google Cloud Platform (GCP) network architecture using a custom VPC with public and private subnets.
It follows real-world cloud security best practices, including restricted access, bastion host pattern, and outbound internet access via Cloud NAT.
🏗 Architecture
Custom VPC
│
├── Public Subnet (10.0.1.0/24)
│   └── Bastion VM (Public IP)
│
├── Private Subnet (10.0.2.0/24)
│   └── Private VM (No Public IP)
│
├── Firewall Rules
│   ├── SSH allowed only to Bastion VM
│   └── SSH allowed from Bastion → Private VM
│
└── Cloud NAT
    └── Outbound internet access for Private VM
🎯 Key Objectives
Create a custom VPC with isolated subnets
Restrict direct internet access to private resources
Implement bastion host for secure SSH access
Enable outbound-only internet for private instances using Cloud NAT
Apply least-privilege firewall rules
________________________________________
🛠Tech stack
•	Google Cloud Platform (GCP)
•	VPC Networking
•	Compute Engine (VMs)
•	Cloud NAT
•	Cloud Router
•	Firewall Rules
•	SSH Agent Forwarding
________________________________________
⚙️ Implementation Summary
1️⃣ VPC & Subnets
•	Created a custom VPC
•	Added:
o	Public subnet (10.0.1.0/24)
o	Private subnet (10.0.2.0/24)
2️⃣ Firewall Rules
•	SSH allowed only to bastion VM using network tags
•	SSH allowed only from bastion VM to private VM
•	No public access to private subnet
3️⃣ Compute Instances
•	Bastion VM
o	Public IP
o	Acts as the single entry point
•	Private VM
o	No public IP
o	Fully isolated from direct internet access
4️⃣ Secure Access
•	SSH access to private VM via bastion host
•	Used SSH agent forwarding (no private keys stored on bastion)
5️⃣ Cloud NAT
•	Configured Cloud Router and Cloud NAT
•	Enabled outbound internet access for private VM
•	Verified using:
•	curl ifconfig.me
________________________________________
🔐 Security Highlights
•	No public IP on private VM
•	Strict firewall rules using network tags
•	Bastion host pattern
•	Outbound-only internet access
•	No SSH keys stored on intermediate hosts
________________________________________
🧪 Validation Checks
•	✅ SSH into bastion VM from Cloud Shell
•	✅ SSH hop from bastion → private VM
•	✅ Private VM has no external IP
•	✅ Private VM can access internet via Cloud NAT
•	❌ Private VM not reachable from the internet
________________________________________
👤 Author
Ammu
Cloud & Infrastructure Enthusiast
GCP | Networking | Cloud Security


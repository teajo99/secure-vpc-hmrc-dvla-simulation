Architecture diagram
![image alt](https://github.com/teajo99/secure-vpc-hmrc-dvla-simulation/blob/c08f3907b1c14cc3605cc54bc416c458e3355438/diagram.jpg)

Secure AWS VPC architecture simulating isolated government systems (HMRC and DVLA) within a single Virtual Private Cloud. Each system runs on private EC2 instances within separate private subnets and cannot communicate with each other. Internet access is provided only through a NAT Gateway located in a public subnet, ensuring outbound-only connectivity. Route tables control traffic flow, while IAM roles securely manage access to AWS services such as S3. The architecture demonstrates network isolation, least-privilege access, and secure cloud design principles.

# secure-vpc-hmrc-dvla-simulation
Secure AWS VPC architecture simulating isolated government departments (HMRC &amp; DVLA) using private subnets, NAT Gateway, IAM roles, and security group isolation.

🏛️ AWS VPC Government Isolation Project (HMRC vs DVLA)
📌 Overview

This project simulates two isolated government systems (HMRC and DVLA) using AWS.
It demonstrates how cloud networks are separated and secured using VPC, subnets, and IAM roles.

Each system is fully isolated but still able to access required services securely.

🎯 What This Project Shows
Network isolation between two systems
Private cloud servers (no public access)
Controlled internet access using NAT Gateway
Secure access to AWS services using IAM roles
🧱 Architecture

The setup includes:

1 VPC
Public subnet
NAT Gateway
2 Private subnets
HMRC server
DVLA server
Internet Gateway
Route tables for traffic control

👉 Built using
Amazon VPC

🖥️ Resources Created
Compute
2 EC2 instances (HMRC + DVLA)
Networking
Public subnet (NAT Gateway)
Private subnets (isolated servers)
Route tables controlling traffic
Security
Security groups block unwanted traffic
IAM roles control access to AWS services
🔐 Security Design
HMRC and DVLA cannot communicate with each other
No EC2 instance has a public IP
Only outbound internet is allowed (via NAT Gateway)
Access to AWS services is controlled using IAM roles

👉 NAT Gateway used:
NAT Gateway

🌐 Internet Access

Private servers access the internet through a NAT Gateway.

No direct inbound access from internet
Only outbound traffic allowed
📦 AWS Services Used
Amazon EC2
Amazon VPC
NAT Gateway
Amazon S3
AWS Identity and Access Management (IAM)
🧪 Tests Performed

✔ HMRC and DVLA cannot communicate
✔ Private servers cannot be accessed from internet
✔ Internet works through NAT Gateway
✔ IAM roles control AWS access

📸 Screenshots in folder

🧠 What I Learned
How to design secure AWS networks
How private subnets work
How NAT Gateway controls outbound traffic
How IAM roles secure AWS services
Real-world cloud isolation concepts
🚀 Result

This project successfully simulates a secure cloud environment where two systems are fully isolated but still functional.

👤 Author

AWS hands-on networking and security project focused on real-world cloud architecture.

🏛️ Government-Isolated AWS VPC Architecture (HMRC vs DVLA Simulation)
📌 Project Overview

This project demonstrates a secure, segmented AWS cloud architecture simulating isolated government departments (HMRC and DVLA). The goal is to enforce network isolation, controlled outbound internet access, and least-privilege security design using core AWS services.

Each workload is fully isolated in private subnets with no public exposure, replicating real-world secure cloud environments used in enterprise and government systems.

🎯 Objectives
Build a secure multi-subnet VPC architecture
Simulate isolated government department environments
Enforce strict network segmentation between workloads
Provide controlled outbound internet access
Secure AWS service access using IAM roles
Demonstrate private instance isolation
🧱 Architecture Overview

The system is built using a custom VPC with public and private subnets:

🌐 Network Design
Public Subnet
Hosts NAT Gateway for outbound internet access
Private Subnets
HMRC Server (isolated workload)
DVLA Server (isolated workload)
Internet Gateway
Attached to VPC for NAT Gateway routing
NAT Gateway
Provides outbound-only internet access for private instances
🏗️ AWS Services Used
Amazon VPC
Amazon EC2
NAT Gateway
Amazon S3
AWS Identity and Access Management (IAM)
Amazon VPC Endpoints
🔐 Security Design
Network Isolation
HMRC and DVLA workloads are deployed in separate private subnets
No direct communication is allowed between instances
IAM-Based Access Control
Separate IAM roles for HMRC and DVLA workloads
Access to S3 is restricted per department
No Public Exposure
EC2 instances are deployed without public IP addresses
Direct SSH access from the internet is not enabled (connection timeout expected in current setup)
🌐 Network Flow
Outbound Internet Access

Private instances → NAT Gateway → Internet Gateway → Internet

AWS Service Access

Private instances → VPC Endpoint → Amazon S3 (private access path)

📦 Resources Created
VPC Configuration
Custom VPC (10.0.0.0/16)
Public subnet (NAT Gateway)
HMRC private subnet
DVLA private subnet
Compute Resources
HMRC EC2 instance (private subnet)
DVLA EC2 instance (private subnet)
Storage
Separate S3 buckets for HMRC and DVLA
Security
Security groups restricting inbound traffic
IAM roles assigned per EC2 instance
🧪 Validation Tests Performed
1. Network Isolation Test
Attempted SSH communication between instances
Result: ❌ Connection failed (expected due to isolation)
2. Public Access Test
Attempted SSH from local machine to private instances
Result: ❌ Connection timed out (expected due to no public IP)
3. Internet Access Test (via NAT Gateway)
Private instances accessed external internet
Result: ✅ Successful
4. S3 Access Test
Access to own S3 bucket allowed via IAM role
Cross-access restricted
Result: ✅ Enforced correctly
🚫 Known Limitations
SSH access to private instances from local machine is not possible (by design)
Session Manager was not configured in this implementation
EC2 instances are intentionally isolated from direct public access
📸 Screenshots

Include the following in /screenshots:

VPC architecture overview
EC2 instances (HMRC & DVLA in private subnets)
Route tables (public + private)
Security groups configuration
IAM roles and policies
NAT Gateway configuration
S3 buckets
🧠 Key Learnings
Designing secure VPC architectures in AWS
Implementing network segmentation using subnets and security groups
Understanding NAT Gateway for outbound-only internet access
Applying IAM-based access control for services
Recognizing limitations of private subnet connectivity
Real-world cloud isolation principles
🚀 Outcome

This project demonstrates a secure AWS network architecture with strict isolation between workloads, simulating government-style environments where systems must remain separated but still operational.

👤 Author

AWS hands-on networking and security architecture project focused on real-world cloud infrastructure design.
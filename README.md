## Building Resilient Cloud Infrastructure with AWS

AWS 2-Tier Architecture: EC2 with MySQL RDS

# 📘 Overview

This repository documents a 2-tier AWS cloud architecture designed to host a scalable and secure web application. It consists of EC2 instances in the public subnet and a MySQL RDS database in the private subnet. The architecture is deployed in the N. Virginia Region (us-east-1) and spans two Availability Zones for high availability.

# 🧱 Components

 Amazon VPC: Custom Virtual Private Cloud to isolate network resources.

🧩 Subnets:

🌐 Public Subnets (AZ a & b): Host EC2 instances for frontend/application layer.

🔐 Private Subnets (AZ a & b): Host MySQL RDS instances securely.

 Amazon EC2: Virtual servers to run application logic or web services.

 Amazon RDS (MySQL): Managed relational database service in a private subnet.

🌍 Internet Gateway: Enables internet access for public subnet resources.

🧭 Route Tables: Control traffic routing within VPC.

# 💼 Use Case

Ideal for:

🛒 E-commerce applications

🏢 Internal business applications

✍️ CMS or blogging platforms

🚀 MVP deployments

🚀 Deployment Instructions

🔧 VPC Setup:

Create a VPC with CIDR block (e.g., 10.0.0.0/16).

Set up 2 public subnets and 2 private subnets across different AZs.

🌐 Internet Gateway:

Attach an Internet Gateway to the VPC.

Modify the route table to enable internet access from public subnets.

💻 EC2 Instances:

Launch EC2 instances in each public subnet.

Use security groups to allow HTTP/HTTPS and SSH access.

🗄️ RDS MySQL:

Launch a Multi-AZ RDS MySQL instance in the private subnets.

Restrict access using security groups that allow access only from EC2 instances.

🔐 Security Considerations

Use least privilege IAM roles.

Apply Network ACLs and Security Groups to segment access.

Enable Multi-AZ and automatic backups for RDS.

Disable public access to RDS.

📈 Scalability Recommendations

Deploy an Application Load Balancer (ALB) in front of EC2 instances.

Use Auto Scaling Groups for EC2 to handle demand.

Consider adding a NAT Gateway for outbound internet access from private subnets.

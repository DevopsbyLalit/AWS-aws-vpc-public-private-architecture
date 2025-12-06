# AWS-aws-vpc-public-private-architecture
# AWS VPC Public–Private Architecture Project

This project demonstrates how to create a secure AWS network architecture using two VPCs:
- Public VPC (Internet-facing)
- Private VPC (Internal and isolated)

Both VPCs are connected using VPC Peering, allowing internal communication without exposing private resources to the public internet.

---
## 📌 Project Objectives

- Setup two isolated VPCs
- Enable public internet access only for Public VPC
- Keep private resources fully isolated
- Allow internal communication using VPC Peering
- Setup proper route tables and security groups

---
## ☁️ AWS Services Used

- VPC
- Subnets
  - Public Subnet
  - Private Subnet
- Internet Gateway (IGW)
- Route Tables
- VPC Peering
- EC2 Instances
- Security Groups

---
## 🏗️ Network Architecture

### Public VPC
| Component | Value |
|----------|--------|
| VPC CIDR | 10.0.0.0/16 |
| Subnet   | 10.0.1.0/24 |
| Internet | Yes (via IGW) |

### Private VPC
| Component | Value |
|----------|--------|
| VPC CIDR | 192.168.0.0/16 |
| Subnet   | 192.168.1.0/24 |
| Internet | No |

---
## 🔐 Route Setup

### Public VPC Route Table

### Private VPC Route Table

---
## 🔄 VPC Peering

A VPC Peering connection was created between:
- Public VPC (10.0.0.0/16)
- Private VPC (192.168.0.0/16)

Both route tables were updated to allow private communication.

---
## 🧪 Testing Connectivity

### From Public EC2 to Private EC2
ping 192.168.1.10

### From Private EC2 to Public EC2
## 🛡️ Security Considerations

- Only Public VPC has internet access
- Private VPC has no IGW, fully isolated
- Only internal traffic allowed through peering
- SSH access only from trusted IPs

---

## 🚀 Use Case Example

| Layer | Deployment |
|-------|------------|
| Application / Frontend | Public VPC |
| Database / Backend     | Private VPC |

Example:
- Public EC2: Hosts web app (Apache, Node.js)
- Private EC2: Database server (MySQL, MongoDB)

This design prevents the database from being exposed publicly.

---
## 📷 Architecture Diagram



[ User ]
    |
Internet
    |
Internet Gateway (IGW)
    |
Public VPC (10.0.0.0/16)
       |
    VPC Peering
       |
Private VPC (192.168.0.0/16)

Add `architecture.png` to the repo.

---
## 📁 Project Structure

aws-vpc-project/
│── README.md
│── architecture.png
│── screenshots/
│── terraform/ (optional)

---

## 🏁 Conclusion

This project demonstrates how to design a secure and scalable AWS network using:
- Public and Private VPCs
- Internet isolation
- VPC Peering
- Correct routing and security

This architecture is commonly used in real-world production systems for secure applications.

---
## 👤 Author

**Name:** Lalit  
**Project:** AWS VPC Public–Private Architecture



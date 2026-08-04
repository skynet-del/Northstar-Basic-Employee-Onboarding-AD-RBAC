# 🏥 Northstar-Basic-Employee-Onboarding-AD-RBAC
**Active Directory • Windows Server • IAM • RBAC • Troubleshooting • Incident Response**
> A hands-on identity and access management lab documenting the design, deployment, and troubleshooting of a fictional healthcare organization's Active Directory environment.
## 🎯 Problem Statement

Northstar Medical Group was operating with a poorly organized identity environment that lacked a consistent Active Directory structure and standardized user provisioning process. User accounts were being managed manually without clearly defined organizational units, naming standards, or security group assignments. This created unnecessary access-control risks and made it difficult to determine which users should have access to specific departmental resources. For a healthcare organization, inconsistent identity and access management could also create potential HIPAA compliance and security concerns.

## 🛠️ Solution Overview

I built a Windows Server Active Directory environment for the fictional Northstar Medical Group using the NMG.com domain. I designed a department-based organizational structure using separate Organizational Units for Finance, HR, IT, and Operations. Each department was assigned a corresponding security group to implement Role-Based Access Control and support the Principle of Least Privilege. I provisioned 15 user accounts using consistent SAMAccountName, UPN, department, and job-title standards. I also investigated and resolved an identity and access incident involving a user who had been placed in the wrong OU and security group. The completed environment provides a more organized, scalable, and auditable approach to identity management.

## 🏗️ Architecture and Access Model

Northstar Medical Group was organized into four departmental Organizational Units:

- Finance
- Human Resources
- Information Technology
- Operations

Each department was assigned a corresponding global security group to support Role-Based Access Control.

See the complete [RBAC structure](Documentation/RBAC-Structure.md).

## 🧰 Tools and Technologies

- 🪟 Windows Server
- 🏢 Active Directory Domain Services
- 👥 Active Directory Users and Computers
- 🖥️ Oracle VirtualBox
- 📜 Group Policy
- ⌨️ Command Prompt
- 🔐 Role-Based Access Control (RBAC)
- 🐙 GitHub
- 📝 Markdown

## 📅 Project Timeline

### 🖥️ Day 1 — Domain Infrastructure

Created a Windows Server virtual machine and configured a static IP address for the server. Installed Active Directory Domain Services and promoted the server to a Domain Controller for the newly created NMG.com domain. Verified the health and functionality of the domain controller using Active Directory tools and the `dcdiag` command.

### 🗂️ Day 2 — Organizational Design

Created separate Organizational Units for Finance, HR, IT, and Operations to organize users by department. Created corresponding global security groups for each department to establish the foundation for Role-Based Access Control. Verified that each security group was located within the appropriate OU and documented the purpose of the organizational structure.

### 👥 Day 3 — Identity Provisioning and RBAC

Provisioned 15 Active Directory user accounts across the four business departments using a standardized naming convention. Configured each account with consistent usernames, UPNs, job titles, and department attributes. Assigned each user to the appropriate departmental security group to implement RBAC and support least-privilege access.

### 🎫 Day 4 — Identity and Access Incident
Investigated support ticket NMG-0047 involving Jane Cooper, an HR Payroll Specialist who could not access HR resources and was receiving incorrect desktop policies and mapped drives. During the investigation, I discovered that her account had been placed in the Operations OU and assigned to the Operations-Users security group. I corrected her OU placement, removed the incorrect group membership, added her to HR-Users, and updated her job title and department attributes. The changes were verified by reviewing her OU placement and security group memberships.

### 📦 Day 5 — Documentation and Portfolio Packaging

Organized the lab documentation, screenshots, RBAC structure, and incident-resolution report into a dedicated GitHub repository. Created a professional README that documents the business problem, technical solution, project timeline, tools used, and major accomplishments. The repository serves as a case study demonstrating the Active Directory environment and the troubleshooting process used during the project.

## 🏆 Key Accomplishments

- Built the NMG.com Active Directory domain from scratch.
- Configured and promoted a Windows Server system to a Domain Controller.
- Designed a department-based OU structure for Finance, HR, IT, and Operations.
- Implemented Role-Based Access Control using department-specific global security groups.
- Provisioned 15 user accounts using consistent SAMAccountName and UPN naming conventions.
- Applied standardized job title and department attributes across user accounts.
- Diagnosed a multi-cause identity issue involving incorrect OU placement and security group membership.
- Corrected user access while following the Principle of Least Privilege.
- Documented the investigation, root cause, corrective actions, and verification process.
- Organized technical evidence and documentation into a professional GitHub case study.

## 📁 Repository Structure

```text
.
├── Documentation/
│   ├── Domain-Config-File.txt
│   ├── Security-Group-Doc.txt
│   ├── User-List-Documentation.txt
│   └── RBAC-Structure.md
│
├── Incident-Reports/
│   └── NMG-0047-Resolution.txt
│
├── Screenshots/
│   ├── Day-1/
│   ├── Day-2/
│   ├── Day-3/
│   └── Day-4/
│
└── README.md
```

## 🚨 Featured Incident — NMG-0047

### 📋 Original Support Ticket

![NMG-0047 Support Ticket](https://github.com/skynet-del/Northstar-Basic-Employee-Onboarding-AD-RBAC/blob/1facc1a1b56ac78d5010395712185d30ca0673df/Incident-Reports/Ticket%20number%20NMG-0047.png)

Jane Cooper reported that she was unable to access HR shared resources and that her desktop policies, mapped drives, and restrictions differed from those of her HR teammates.

My investigation identified two related configuration problems: Jane's account was located in the Operations OU and she was a member of the Operations-Users security group instead of HR-Users. The incorrect OU placement affected the policies being applied to her account, while the incorrect security group membership prevented her from receiving the access associated with the HR department.

The account was moved to the HR OU, removed from Operations-Users, and added to HR-Users. Her job title and department attributes were also updated to reflect her HR Payroll Specialist role.

![Read the complete incident-resolution report](Incident-Reports/Ticket number NMG-0047.txt)

## 🎥 Video Walkthrough

Video walkthrough coming in Day 6.

## ℹ️ Disclaimer

This project was completed in an isolated lab environment for educational and portfolio purposes. Northstar Medical Group, its users, systems, and support incidents are fictional.

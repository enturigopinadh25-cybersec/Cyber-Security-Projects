# Multi-Cloud Identity & Access Management (IAM) Implementation – 2025

## Overview
This project demonstrates the implementation of secure Identity & Access Management (IAM) controls across **AWS and Azure** cloud environments. The objective was to enforce **least-privilege access**, **role-based access control (RBAC)**, and **Multi-Factor Authentication (MFA)** to reduce unauthorized access risks.

## IAM Objectives
- Enforce least-privilege permissions
- Separate administrative and user access
- Require MFA for sensitive operations
- Reduce blast radius in case of credential compromise

---

## AWS IAM Implementation

### Users
- Created individual IAM users for administrative and application access.
- Disabled root account access for daily operations.

### Groups
- `AdminGroup` – Full administrative privileges.
- `ReadOnlyGroup` – View-only access for auditing.
- `DeveloperGroup` – Limited access to EC2 and S3 resources.

### Roles
- EC2 Role for applications requiring S3 access.
- Temporary roles for administrative access using STS.

### Security Controls
- MFA enforced for all privileged users.
- Strong password policy enabled:
  - Minimum length: 12 characters
  - Password rotation enabled
  - Prevention of password reuse

---

## Azure IAM (Azure Active Directory) Implementation

### Users & Groups
- Created Azure AD users and security groups.
- Assigned users to groups based on job roles.

### Role-Based Access Control (RBAC)
- Used built-in Azure roles such as:
  - Reader
  - Contributor
  - Virtual Machine Contributor

### MFA & Conditional Access
- MFA enforced using Azure Conditional Access.
- MFA required for:
  - Azure Portal login
  - Access to production subscriptions

---

## Logging & Monitoring
- AWS CloudTrail enabled for IAM activity monitoring.
- Azure Activity Logs enabled for role changes and sign-ins.

---

## Key Security Benefits
- Reduced risk of privilege escalation
- Improved access visibility and auditability
- Strong defense against credential theft

## Conclusion
This IAM implementation aligns with cloud security best practices and demonstrates real-world identity security controls used in enterprise environments.

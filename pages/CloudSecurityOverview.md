### Cloud Security Overview
When it comes to Cloud Security we need to differ between
- Security in the Cloud (secure platform)
The Cloud provider takes care of this and ideally handles this as transparently as possible and proves it by providing certifications/attestations (e.g. for IBM Cloud see https://www.ibm.com/de-de/cloud/compliance)
- Security in the Cloud (secure workload)
The Cloud provider provides security services you configure and use to safeguard your workload

When talking about Cloud Security we need to cover the following topics
- Securing Access
Perimeter Security and Identity and Access Management
- Application and Data Security
Vulnerability Scanning and Data Encryption (in transport, at rest and sometimes even in memory)
- Security Logging and Visibility
Track and Analyze/Report Security relevant activities

A sample minimalistic mapping for a container-based workload running on IBM Virtual Private Cloud would be:
- Securing Access
Virtual Private Cloud for logical isolation with BYOIP subnets
Using Access Control Lists (ACLs) and Security Groups to permit only traffic allowed
Use public Internet connectivity only where it is really needed
Use Virtual Private Endpoints to connect to services over the IBM Cloud Private Network Only
VPN for VPC to allow private access only whereever possible (alternatively use Direct Link as private connectivity vehicle)
Use Flow Logs
IBM Cloud Identity and Access Management (IAM)

- Application and Data Security
Use Code Risk Analyzer (based on Snyk) during build of your applications
Use IBM Container Registry with vulnerability Scanning
Use IBM Secrets Manager (Vault as a Service) to store your secrets
Use Key Protect to Bring your Own Keys for Data Encrytion together with Storage (Block or Object Storage) and Databases (e.g. PostgreSQL)
Use Certificate Manager to administer your certificates

- Security Logging and Visibility
Use Activity Tracker to track security activities
Use other standard IBM Cloud observability components (Logging with LogDNA and SysDig)
Use IBM Cloud Security and Compliance Center to activate IBM Cloud CIS (Cloud Internet Security) ruleset checking

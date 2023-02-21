# Connecting to Cloud SQL instance with private IP only from local machine via Cloud SQL Proxy
---
## 1. Create a VPC network and subnet for your Cloud SQL instance.
## 2. Enable the Cloud SQL Admin API.
## 3. Create a Cloud SQL instance with private IP enabled.
## 4. Create a service account for the Cloud SQL Proxy with the Cloud SQL Admin, Cloud SQL Client, and Cloud SQL Editor roles.
## 5. Create a Compute Engine VM instance in the same VPC network as your Cloud SQL instance.
## 6. Install the Cloud SQL Proxy on the Compute Engine VM instance.
## 7. Run the Cloud SQL Proxy on the Compute Engine VM instance and add it to the instance metadata.
## 8. Enable the Cloud Identity-Aware Proxy (IAP) API.
## 9. Add the Cloud SQL Client and IAP - Secured Tunnel User roles to the service account principal.
## 10. Connect to the Cloud SQL instance using MySQL Workbench.

# Connecting to Cloud SQL instance with private IP only from local machine via Cloud SQL Auth Proxy
---
## 1. Create a VPC network:
- Go to the VPC networks page in the Google Cloud Console.
- Click on the "Create VPC network" button.
- Give your VPC network a name, select a region, and set the subnet range.
- Click on the "Create" button.
## 2. Create a Cloud SQL instance with a private IP:
- Go to the Cloud SQL instances page in the Google Cloud Console.
- Click on the "Create instance" button.
- Select "MySQL" as the database engine.
- Give your instance a name, set the root password, and select the desired region.
- Under "Connectivity", select "Private IP".
- Select the VPC network you created in step 1.
- Set a subnet for your instance.
- Click on the "Create" button.
## 3. Create a VM to tunnel through:
- Go to the VM instances page in the Google Cloud Console.
- Click on the "Create instance" button.
- Give your instance a name, select the desired region, and choose the VPC network you created in step 1.
- Under "Firewall", select "Allow HTTP traffic" and "Allow HTTPS traffic".
- Click on the "Create" button.
## 4. Set up Cloud SQL Proxy on the VM:
- SSH into the VM instance you created in step 3.
- Download the Cloud SQL Proxy binary to your VM by running the following command: `curl -o cloud_sql_proxy https://dl.google.com/cloudsql/cloud_sql_proxy.linux.amd64`
- Make the binary executable by running the following command: `chmod +x cloud_sql_proxy`
- Start the Cloud SQL Proxy by running the following command: `./cloud_sql_proxy <INSTANCE_CONNECTION_NAME> --credentials-file=<PATH_TO_CREDENTIALS_FILE>`  
Note: Replace <INSTANCE_CONNECTION_NAME> with the instance connection name of your Cloud SQL instance. You can find this information in the instance details page of the Cloud SQL Console.
`

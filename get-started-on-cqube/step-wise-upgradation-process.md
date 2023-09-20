---
description: Lists the steps to upgrade from cQube V 4.1 - Beta to cQube V 5.0
---

# Step-wise Upgradation Process

Upgradation is currently available on 3 types of servers:

1. AWS
2. Azure
3. On-Premise (Local)

Steps for each one of these servers have been explained below:

### Step 1:

**AWS**

Connect to the cQube AWS EC2 Instance

For Linux and macOS:

1. Download the .pem file generated during EC2 instance creation.
2. Open the terminal and navigate to the folder where the .pem file is downloaded.
3. Provide read permission to the .pem file: sudo chmod 400 \<aws.pem>

Connect to the instance using the following command:

4. ssh -i \<path\_to\_the\_pem\_file> \<user\_name>@\<public\_ip\_of\_the\_instance>

For Windows:

1. Download the .pem file generated during EC2 instance creation.
2. Use Puttygen to connect to the instance. Refer to this link for instructions:[ PuttyGen Instructions](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/putty.html)

**Azure**

Connect to the cQube Azure VM Instance

For Linux and macOS:

1. Download the .pem file generated during Azure VM instance creation.
2. Open the terminal and navigate to the folder where the .pem file is downloaded.
3. Provide read permission to the .pem file: sudo chmod 400 \<aws.pem>

Connect to the instance using the following command:

4. ssh -i \<path\_to\_the\_pem\_file> \<user\_name>@\<public\_ip\_of\_the\_instance>

For Windows:

1. Download the .pem file generated during Azure VM instance creation.
2. Use Puttygen to connect to the instance. Refer to this link for instructions:[ PuttyGen Instructions](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/putty.html)

\
**Local/SDC**

Prerequisites for cQube on Local Machine:

* Ubuntu 22.04 (supported)
* 16 GB of System RAM (minimum requirement)
* 4 core CPU (minimum requirement)
* Domain name (with SSL)
* 250 GB Storage

### **Step 2:**&#x20;

Clone the cqube-devops Repository

Clone the cqube-devops repository using the following command:

git clone [https://github.com/Sunbird-cQube/cqube-devops.git](https://github.com/Sunbird-cQube/cqube-devops.git)

### Step 3:&#x20;

Navigate to the Cloned Directory

Navigate to the directory where cQube is cloned or downloaded and checkout the desired branch:

`cd cqube-devops/ && git checkout <branch_name>`

### Step 4:

Give Execute Permissions to the Upgrade.sh File

Give execute permissions to the upgrade.sh file:\
`sudo chmod u+x upgrade.sh`

### Step 5:&#x20;

Upgrade cQube with Non-root User and Sudo Privileges

Upgrade cQube using the following command:

`sudo ./upgrade.sh`

### Step 6:

&#x20;Follow the prompts and enter the necessary input variables based on the server setup.

&#x20;Follow the screenshots provided in the installation guide for reference.



_Note: The upgradation process may have slight variations depending on the specific environment and configurations. Ensure that you have the required credentials, keys, and access rights before proceeding with the upgrade._

_Once the upgrade is completed, you will receive a confirmation message stating that cQube has been upgraded successfully. You can access the cQube ingestion API using the provided \<domain\_name>._



## **Appendix**

### **AWS - Network Architecture** <a href="#_n8oyt4k2rosv" id="_n8oyt4k2rosv"></a>

The following steps define the cQube setup and workflow completion processes in AWS. cQube mainly comprises the areas mentioned below:

1. EC2 Server
2. IAM user and Role creation for S3 connectivity.

The cQube network setup process is described in the block diagram below:

![](../.gitbook/assets/14.jpeg)

### &#x20;<a href="#_axzmu97gr6u7" id="_axzmu97gr6u7"></a>

### &#x20;<a href="#_36f17w9ms7xd" id="_36f17w9ms7xd"></a>
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

### &#x20;**Step 2:**&#x20;

Clone the cqube-devops Repository

Clone the cqube-devops repository using the following command:

\
git clone [https://github.com/Sunbird-cQube/cqube-devops.git](https://github.com/Sunbird-cQube/cqube-devops.git)

### &#x20;Step 3:&#x20;

Navigate to the Cloned Directory

Navigate to the directory where cQube is cloned or downloaded and checkout the desired branch:

`cd cqube-devops/ && git checkout dev`

### Step 4:

Give Execute Permissions to the Upgrade.sh File

Give execute permissions to the upgrade.sh file:\
`sudo chmod u+x upgrade.sh`

### &#x20;Step 5:&#x20;

Upgrade cQube with Non-root User and Sudo Privileges

Upgrade cQube using the following command:

`sudo ./upgrade.sh`



### Step 6:

&#x20;Follow the prompts and enter the necessary input variables based on the server setup.

&#x20;Follow the screenshots provided in the installation guide for reference.

\


_Note: The upgradation process may have slight variations depending on the specific environment and configurations. Ensure that you have the required credentials, keys, and access rights before proceeding with the upgrade._

_Once the upgrade is completed, you will receive a confirmation message stating that cQube has been upgraded successfully. You can access the cQube ingestion API using the provided \<domain\_name>._



### **Appendix**

### **AWS - Network Architecture** <a href="#_n8oyt4k2rosv" id="_n8oyt4k2rosv"></a>

The following steps define the cQube setup and workflow completion processes in AWS. cQube mainly comprises the areas mentioned below:

1. EC2 Server
2. IAM user and Role creation for S3 connectivity.

The cQube network setup process is described in the block diagram below:

![](../.gitbook/assets/14.jpeg)

### &#x20;<a href="#_axzmu97gr6u7" id="_axzmu97gr6u7"></a>

### **Microservices Details** <a href="#_36f17w9ms7xd" id="_36f17w9ms7xd"></a>

Following are the details of the microservices which get installed in the cqube server.

* **Ingestion-ms:** The ingestion-ms is used to upload the data of the events, datasets, dimensions, transformers and pipeline. All these apis will be to ingesting the data into the cQube.
* **Spec-ms:** The spec-ms is used to import schema of the events, datasets, dimensions, transformers and pipeline. All these specs will be defined by the cQube platform prior to ingesting the data into the cQube. These specifications are derived by considering the KPIs as the Indicator.
* **Generator-ms:** The generator-ms is used to create the specs & transformers for the derived datasets. Performed aggregation logics, updating data to datasets based on transformation. Status update of file processing
* **Nifi-ms:** Apache NiFi is used as a real-time integrated data logistics and simple event processing platform
* **Postgres-ms:** Postgres microservice contains the schema and tables
* **Nginx-ms:** It is commonly used as a reverse proxy and load balancer to manage incoming traffic and distribute it to slower upstream servers
* **Kong-ms:** It is a lightweight API Gateway that secures, manages, and extends APIs and microservices.
* **Dashboard-ms**: It consists of an angular app, it is used to visualize the datasets present in postgres-ms in the form of charts. On run time it requests spec-ms to fetch data from postgres-ms and load it into the client side(Browser)
* **Query\_builder-ms:** It consists of backend API, which consists of JWT,METRICS,QUERY apis

JWT - it will generate a jwt token to restrict the other apis.

METRICS - it consists of menus for the navigation bar and dashboard cards.

QUERY - this api used for executing the SQL queries which integrated with Dashboard-ms.

LASTMODIFIED - this api will use for the last modified data in the s3,azure and minio

### &#x20;<a href="#_uv71gv9vyzoa" id="_uv71gv9vyzoa"></a>

### **cQube Deployment Procedure** <a href="#_t2hz446tvcsb" id="_t2hz446tvcsb"></a>

upgradel.sh sh file contains a shell script where it will run following shell scripts and ansible-playbook to setup the cqube

**Basic\_requirements.sh:**

This script basically updates and upgrades the software packages in the server and installs the basic softwares such as

* Python3
* Pip3
* Ansible
* Docker
* Docker compose

**upgradation\_Config\_file\_generator.sh:**

This script is used to generate a configuration file which contains some constant values and few required variables should be entered by the user. Following are the variables which get added in the config file.

**Note:** Users should follow the Hints provided in the description and should enter the variables accordingly. If the entered value is wrong then an error message gets displayed and the user should modify the variable value accordingly.\
Constant Variables: These variables are auto generated

* System\_user\_name
* base\_dir
* Private\_ip
* aws\_default\_region

User Input Variables-These are variables which need to be entered by the user by following the Hint provided

* state\_name ( Enter the required state code by referring to the state list provided )
* api\_end\_point ( Enter the url in which cqube to be configured )
* storage\_type

Storage\_type is aws enter the below variables

* s3\_access\_key
* s3\_secret\_key
* s3 bucket name

Storage\_type is azure enter the below variables

* azure connection string
* azure account name
* Azure account key
* azure container name

Storage\_type is a local system that will automatically create the minio username and minio password and minio bucket.

* minio username
* minio password
* minio bucket

**Minino can be accessed by Dashboard with** [**http://localhost**](http://localhost/)**:9001 end point, here you can see the minio bucket which is created by default and the username is minioadmin and password is minioadmin**

Optional\_variables - Database credentials contain default values. If the user wishes to enter their own credentials then the user should opt for **yes** to enter their credentials otherwise can opt for **no** when the question pops up

* db\_user\_name ( Enter the postgres database username )
* db\_name ( Enter the postgres database name )
* db\_password ( Enter the postgres password )

Optional\_variables- Read Only Database credentials contain default values. If the user wishes to enter their own credentials then the user should opt for **yes** to enter their credentials otherwise can opt for **no** when the question pops up

* read\_only\_db\_user ( Enter the read only postgres database username )
* read\_only\_db\_password ( Enter the read only postgres password )

Once the upgradation\_config file is generated, A preview of the upgradation\_config file is displayed followed by a question where the user gets an option to re enter the configuration values on choosing **yes. I**f option **no** is selected then the upgrade.sh moves to the next section.

**Repository\_clone.sh:**

This script clones the following repositories in the microservices directory and checkout to the required release branch

* git clone [https://github.com/Sunbird-cQube/spec-ms.git](https://github.com/Sunbird-cQube/spec-ms.git)
* git clone [https://github.com/Sunbird-cQube/ingestion-ms.git](https://github.com/Sunbird-cQube/ingestion-ms.git)
* git clone [https://github.com/Sunbird-cQube/generator-ms.git](https://github.com/Sunbird-cQube/ingestion-ms.git)
* git clone [https://github.com/Sunbird-cQube/dashboard-ms.git](https://github.com/Sunbird-cQube/dashboard-ms.git)
* git clone [https://github.com/Sunbird-cQube/query-builder.git](https://github.com/Sunbird-cQube/dashboard-ms.git)

![](<../.gitbook/assets/15 (1).png>)

Note: If the repository is already cloned then the script will pull the updated code.

**Ansible-playbook:**

**upgrade.yml**

An upgrade.yml ansible playbook gets triggered where it triggers the required roles to build the following microservices images.

* Ingestion-ms
* Spec-ms
* Generator-ms
* Postgres-ms
* Nifi-ms
* Dashboard-ms
* Query\_builder-ms
* Kong-ms
* Nginx-ms

![](../.gitbook/assets/16.png)

**upgrade\_compose.yml:**

A docker compose ansible script gets triggered where it will up all the containers to running state.

**Note:** The following commands can be used from the Ansible directory to down the containers and to start the containers, respectively.

* docker-compose -f upgrade\_docker-compose.yml down
* docker-compose -f upgrade\_docker-compose.yml up -d

**Run\_api.sh:**

Run\_api.sh script will run the v4-data-emission api using curl command in the ingestion\_ms container. And it will run the adapter file to run VSK\_data\_transformation.sh script in the generator-ms container.

Once the Upgradation is completed, You will be prompted with the following messages and required reference urls.

**cQube Upgraded Successfully**

![](../.gitbook/assets/17.png)

We can check the containers running status by using following command

* sudo docker ps

![](../.gitbook/assets/18.png)

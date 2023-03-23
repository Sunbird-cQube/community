---
description: Lists the steps to install cQube v5.0
---

# Step-wise Installation Process

## For AWS:

#### **Configurations -**

Post creating the EC2 instance as per the defined hardware requirements [here](hardware-requirements.md), make the following configurations:

Security Group Configuration:

* Port 80 inbound from 0.0.0.0/0
* Port 443 inbound from 0.0.0.0/0
* Port 8000 inbound from nginx private ip (to communicate with kong)
* 5432 inbound to the particular ip which needs access

Kong Configurations:

* 3000 will get routed to /ingestion
* 3001 will get routed to /spec
* 3003 will get routed to /generator

#### **IAM user and Role creation for S3 connectivity** <a href="#iam-user-and-role-creation-for-s3-connectivity" id="iam-user-and-role-creation-for-s3-connectivity"></a>

An AWS Identity and Access Management (IAM) user is an entity that is created in AWS to represent the person or application that uses it to interact with AWS. A user in AWS contains a name and credentials. An IAM user with administrator permissions is different from the AWS account root user. One has to create an IAM user with a supported role to provide the connectivity between EC2 and S3. The role should have list, read and write permissions

S3 Buckets: Create the following s3 buckets -

* Archiving&#x20;
* Error logging

IAM User:

* Create an IAM user
* Assign IAM policy to the user
* Download the access key and secret key

IAM Policy:

* Create an IAM policy from AWS IAM
* Provide access to list, read and write the objects to s3 buckets

**Step-by-Step Installation Process:**

**Step - 1:** Connect to the cQube AWS ec2 instance.

For linux and macOS:

* Download the .pem file which is generated while creating the EC2 instance
* Open the terminal and navigate to the folder where .pem file has been downloaded
* Then give the read permission to the .pem file using following command

&#x20; `sudo chmod 400 <aws.pem>`

* Use the following command to connect to the instance

`ssh -i <path_to_the_pem_file>  <user_name>@<public_ip_of_the_instance>`

For windows:

* Download the .pem file which is generated while creating the EC2 instance
* Use puttygen to connect to the instance.
* Refer to [this](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/putty.html) link to use puttyGen for connecting.

**Step - 2:** Clone the cqube-devops repository using the following command:

`git clone` [`https://github.com/Sunbird-cQube/cqube-devops.git`](https://github.com/Sunbird-cQube/cqube-devops.git)

<figure><img src="../.gitbook/assets/image (4) (3) (1).png" alt=""><figcaption></figcaption></figure>

**Step - 3:** Navigate to the directory where cQube is cloned or downloaded and checkout to the desired branch

`cd cqube-devops/ && git checkout dev`

<figure><img src="../.gitbook/assets/image (3) (1) (2).png" alt=""><figcaption></figcaption></figure>

**Step - 4:** Give the following permissions to the install.sh file

`sudo chmod u+x install.sh`

**Step - 5:** Install cQube with non root user with sudo privileges

`sudo ./install.sh`

<figure><img src="../.gitbook/assets/image (6) (1) (1).png" alt=""><figcaption></figcaption></figure>

Install.sh file contains a shell script where it will run shell scripts and ansible-playbook to setup cQube.

**Step - 6:** User Input Variables - These are the variables which need to be entered by the user using the hint provided:

* state\_name ( Enter the required state code by referring to the state list provided )
* api\_end\_point ( Enter the url in which cQube to be configured )
* s3\_access\_key
* s3\_secret\_key
* s3 archived bucket name
* s3 error bucket name

<figure><img src="../.gitbook/assets/image (2) (2) (1).png" alt=""><figcaption></figcaption></figure>

**Step - 7:** Optional\_variables - Database credentials contain default values. If the user wishes to enter their own credentials then the user should opt for **yes** to enter their credentials otherwise can opt for **no** when the question pops up

* db\_user\_name ( Enter the postgres database username )&#x20;
* db\_name ( Enter the postgres database name )
* db\_password ( Enter the postgres password )

<figure><img src="../.gitbook/assets/image (5) (1) (1).png" alt=""><figcaption></figcaption></figure>

**Step - 8:** Once the config file is generated, A preview of the config file is displayed followed by a question where the user gets an option to re enter the configuration values on choosing **yes.** If option **no** is selected then the install.sh moves to the next section.

<figure><img src="../.gitbook/assets/image (8).png" alt=""><figcaption></figcaption></figure>

**Step - 9:** Once the installation is completed, You will be prompted with the following messages and required reference urls.

<mark style="color:green;">**cQube Installed Successfully**</mark>

cQube ingestion api can be accessible using \<domain\_name>

<figure><img src="../.gitbook/assets/image (7) (1).png" alt=""><figcaption></figcaption></figure>

### **Appendix** <a href="#appendix" id="appendix"></a>

#### **Network Architecture for AWS:** <a href="#aws-network-architecture" id="aws-network-architecture"></a>

The following steps define the cQube setup and workflow completion processes in AWS. cQube mainly comprises the areas mentioned below:

1. EC2 Server
2. IAM user and Role creation for S3 connectivity.

The cQube network setup process is described in the block diagram below:&#x20;

<figure><img src="../.gitbook/assets/image (2) (3).png" alt=""><figcaption></figcaption></figure>

![](blob:https://project-sunbird.atlassian.net/a67e7674-99fa-40e6-aaa8-9e4e8dbe54b0#media-blob-url=true\&id=aee85b7f-ff92-4609-9d93-24c052486a11\&collection=contentId-3280666668\&contextId=3280666668\&height=523\&width=737\&alt=)

#### **Micro services Details** <a href="#micro-services-details" id="micro-services-details"></a>

Following are the details of the micro-services which get installed in the cQube server.

* **Ingestion-ms:** The ingestion-ms is used to upload the data of the events, datasets, dimensions, transformers and pipeline. All these APIs will be ingesting the data into the cQube.
* **Spec-ms:** The spec-ms is used to import schema of the events, datasets, dimensions, transformers and pipeline. All these specs will be defined by the cQube platform prior to ingesting the data into the cQube. These specifications are derived by considering KPIs as the Indicator.
* **Generator-ms:** The generator-ms is used to create the specs & transformers for the derived datasets - Performing aggregation logics, updating data to datasets based on transformation and providing status update of file processing.
* **Nifi-ms:** Apache NiFi is used as a real-time integrated data logistics and simple event processing platform.
* **Postgres-ms:** Postgres micro-service contains the schema and tables.
* **Nginx-ms:** It is commonly used as a reverse proxy and load balancer to manage incoming traffic and distribute it to slower upstream servers.
* **Kong-ms:** It is a lightweight API Gateway that secures, manages, and extends APIs and micro-services.

#### **cQube Deployment Procedure** <a href="#cqube-deployment-procedure" id="cqube-deployment-procedure"></a>

Install.sh file contains a shell script where it will run by following shell scripts and ansible-playbook to setup cQube

**Basic\_requirements.sh:**

This script basically updates and upgrades the software packages in the server and installs basic softwares such as:

* Python3
* Pip3
* Ansible
* Docker
* Docker compose

**Config\_file\_generator.sh:**

This script is used to generate a configuration file which contains some constant values. Few required variables should be entered by the user. Following are the variables which get added in the config file.

* System\_user\_name
* base\_dir
* Private\_ip
* aws\_default\_region

**Note:** Users should follow the hints provided in the description and should enter the variables accordingly. If the entered value is wrong then an error message gets displayed and the user should modify the variable value accordingly.

User Input Variables - These are variables which need to be entered by the user by following the hint provided:

* state\_name (Enter the required state code by referring to the state list provided)
* api\_end\_point (Enter the URL in which cQube to be configured )
* s3\_access\_key
* s3\_secret\_key
* s3 archived bucket name
* s3 error bucket name        &#x20;

Optional\_variables - Database credentials contain default values. If the user wishes to enter their own credentials then the user should opt for **yes** to enter their credentials otherwise can opt for **no** when the question pops up

* db\_user\_name ( Enter the postgres database username )&#x20;
* db\_name ( Enter the postgres database name )
* db\_password ( Enter the postgres password )

Once the config file is generated, a preview of the config file is displayed followed by a question where the user gets an option to re-enter the configuration values on choosing **yes. I**f option **no** is selected then the install.sh moves to the next section.

**Repository\_clone.sh:**

This script clones the following repositories in the micro-services directory and checks out to the required release branch:

* `git clone` [`https://github.com/Sunbird-cQube/spec-ms`](https://github.com/Sunbird-cQube/spec-ms)``
* `git clone` [`https://github.com/Sunbird-cQube/ingestion-ms`](https://github.com/Sunbird-cQube/spec-ms)``
* `git clone` [`https://github.com/Sunbird-cQube/generator-ms.git`](https://github.com/Sunbird-cQube/ingestion-ms.git)``

<figure><img src="../.gitbook/assets/image (10) (1).png" alt=""><figcaption></figcaption></figure>

Note: If the repository is already cloned then the script will pull the updated code.

**Ansible-playbook**

1. **Install.yml** - An install.yml ansible playbook gets triggered where it triggers the required roles to build the following microservices images.

* Ingestion-ms
* Spec-ms
* Generator-ms
* Postgres-ms
* Nifi-ms
* Kong-ms
* Nginx-ms

<figure><img src="../.gitbook/assets/image (9) (1).png" alt=""><figcaption></figcaption></figure>

2. **compose.yml -** A docker compose ansible script gets triggered where it will up all the containers to running state.

**Note:** The following commands can be used from the Ansible directory to down the containers and to start the containers, respectively.

* `docker-compose -f docker-compose.yml down`
* `docker-compose -f docker-compose.yml up -d`

Once the installation is completed, You will be prompted with the following messages and required reference urls.

**cQube Installed Successfully**

<figure><img src="../.gitbook/assets/image (4) (1) (2).png" alt=""><figcaption></figcaption></figure>

We can check the containers running status by using following command

`sudo docker ps`

<figure><img src="../.gitbook/assets/image (20).png" alt=""><figcaption></figcaption></figure>

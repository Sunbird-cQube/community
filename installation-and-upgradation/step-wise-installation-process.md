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

<figure><img src="../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

**Step - 3:** Navigate to the directory where cQube is cloned or downloaded and checkout to the desired branch

`cd cqube-devops/ && git checkout dev`

<figure><img src="../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

**Step - 4:** Give the following permissions to the install.sh file

`sudo chmod u+x install.sh`

**Step - 5:** Install cQube with non root user with sudo privileges

`sudo ./install.sh`

<figure><img src="../.gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>

Install.sh file contains a shell script where it will run shell scripts and ansible-playbook to setup cQube.

**Step - 6:** User Input Variables - These are the variables which need to be entered by the user using the hint provided:

* state\_name ( Enter the required state code by referring to the state list provided )
* api\_end\_point ( Enter the url in which cQube to be configured )
* s3\_access\_key
* s3\_secret\_key
* s3 archived bucket name
* s3 error bucket name

<figure><img src="../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

**Step - 7:** Optional\_variables - Database credentials contain default values. If the user wishes to enter their own credentials then the user should opt for **yes** to enter their credentials otherwise can opt for **no** when the question pops up

* db\_user\_name ( Enter the postgres database username )&#x20;
* db\_name ( Enter the postgres database name )
* db\_password ( Enter the postgres password )

<figure><img src="../.gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure>

**Step - 8:** Once the config file is generated, A preview of the config file is displayed followed by a question where the user gets an option to re enter the configuration values on choosing **yes.** If option **no** is selected then the install.sh moves to the next section.

<figure><img src="../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

**Step - 9:** Once the installation is completed, You will be prompted with the following messages and required reference urls.

<mark style="color:green;">**cQube Installed Successfully**</mark>

cQube ingestion api can be accessible using \<domain\_name>

<figure><img src="../.gitbook/assets/image (7).png" alt=""><figcaption></figcaption></figure>

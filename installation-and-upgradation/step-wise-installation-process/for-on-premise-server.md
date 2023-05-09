---
description: Explains the steps to install cQube V 5.0 on On-Premise (local) Server
---

# For On-Premise Server

### **Configurations -**

Post creating the Local SDC instance as per the defined hardware requirements [here](../hardware-requirements.md), make the following configurations:

Security Group Configuration:

* Port 80 inbound from 0.0.0.0/0
* Port 443 inbound from 0.0.0.0/0
* Port 8000 inbound from nginx private IP (to communicate with kong)
* 5432 inbound to the particular IP which needs access

Kong Configurations:

* 3000 will get routed to /ingestion
* 3001 will get routed to /spec
* 3003 will get routed to /generator

Enter storage\_type as local. Then, install.sh will automatically get installed and configure the minio application in localhost. It will also configure default username and password and create a minio bucket.

### **Step-by-Step Installation Process:**

**Step - 1:** Clone the cqube-devops repository using the following command:

`git clone` [`https://github.com/Sunbird-cQube/cqube-devops.git`](https://github.com/Sunbird-cQube/cqube-devops.git)

<figure><img src="../../.gitbook/assets/image (4) (3) (1).png" alt=""><figcaption></figcaption></figure>

**Step - 2:** Navigate to the directory where cQube is cloned or downloaded and checkout to the desired branch

`cd cqube-devops/ && git checkout release-5.0`

<figure><img src="../../.gitbook/assets/image (3) (1) (2).png" alt=""><figcaption></figcaption></figure>

**Step - 3:** Give the following permissions to the install.sh file

`sudo chmod u+x install.sh`

**Step - 4:** Install cQube with non root user with sudo privileges

`sudo ./install.sh`

<figure><img src="../../.gitbook/assets/image (6) (1) (1).png" alt=""><figcaption></figcaption></figure>

Install.sh file contains a shell script where it will run shell scripts and ansible-playbook to setup cQube.

**Step - 5:** User Input Variables - These are the variables which need to be entered by the user using the hint provided:

* state\_name ( Enter the required state code by referring to the state list provided )
* api\_end\_point ( Enter the url in which cqube to be configured )
* Storage\_type : Local
* Mode\_of\_installation:Public
* Cron syntax to run adapter scheduling (EX: if want to run the adapter at 11AM )

0 0 11 \* \* ?

* Cron syntax to run nifi plug in (EX: if want to run the nifi plug in at 11:30 AM)

0 30 11 \* \* ?

* Cron syntax to run nifi processing file (EX: if want to run the nifi plug in at 11:30 AM)

0 30 11 \* \* ?

\


<figure><img src="../../.gitbook/assets/image (1) (4) (1).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (44).png" alt=""><figcaption></figcaption></figure>

**Step - 6:** Optional\_variables - Database credentials contain default values. If the user wishes to enter their own credentials then the user should opt for **yes** to enter their credentials otherwise can opt for **no** when the question pops up

* db\_user\_name (Enter the postgres database username)&#x20;
* db\_name (Enter the postgres database name)
* db\_password (Enter the postgres password)

<figure><img src="../../.gitbook/assets/image (5) (1) (1).png" alt=""><figcaption></figcaption></figure>

**Step - 7:** Optional\_variables- Read Only Database credentials contain default values. If the user wishes to enter their own credentials then the user should opt for **yes** to enter their credentials otherwise can opt for **no** when the question pops up:

* read\_only\_db\_user (Enter the read only postgres database username)&#x20;
* read\_only\_db\_password (Enter the read onlypostgres password)

<figure><img src="../../.gitbook/assets/image (29).png" alt=""><figcaption></figcaption></figure>

**Step - 8:** Once the config file is generated, a preview of the config file is displayed followed by a question where the user gets an option to re enter the configuration values on choosing **yes.** If option **no** is selected then the install.sh moves to the next section.

<figure><img src="../../.gitbook/assets/image (5) (1).png" alt=""><figcaption></figcaption></figure>

**Step - 9:** A preview of the program\_selector.yml file is displayed followed by a question where the user gets an option to enable or disable the programs on choosing **yes.** If option **no** is selected then the install.sh moves to the next section.

<figure><img src="../../.gitbook/assets/image (30).png" alt=""><figcaption></figcaption></figure>

**Step - 10:** Once the installation is completed, You will be prompted with the following messages and required reference urls.

<mark style="color:green;">**cQube Installed Successfully**</mark>

cQube ingestion api can be accessed using \<domain\_name>

<figure><img src="../../.gitbook/assets/image (4) (1) (2).png" alt=""><figcaption></figcaption></figure>

## **Appendix**![](blob:https://project-sunbird.atlassian.net/a67e7674-99fa-40e6-aaa8-9e4e8dbe54b0#media-blob-url=true\&id=aee85b7f-ff92-4609-9d93-24c052486a11\&collection=contentId-3280666668\&contextId=3280666668\&height=523\&width=737\&alt=) <a href="#appendix" id="appendix"></a>

### **Micro services Details** <a href="#micro-services-details" id="micro-services-details"></a>

Following are the details of the micro-services which get installed in the cQube server.

* **Ingestion-ms:** The ingestion-ms is used to upload the data of the events, datasets, dimensions, transformers and pipeline. All these APIs will be used to ingest the data into cQube.
* **Spec-ms:** The spec-ms is used to import schema of the events, datasets, dimensions, transformers and pipeline. All these specs will be defined by the cQube platform prior to ingesting the data into cQube. These specifications are derived by considering the KPIs as the Indicator.
* **Generator-ms:** The generator-ms is used to create the specs & transformers for the derived datasets - performing aggregation logics, updating data to datasets based on transformation. Status update of file processing.
* **Nifi-ms:** Apache NiFi is used as a real-time integrated data logistics and simple event processing platform.
* **Postgres-ms:** Postgres microservice contains the schema and tables.
* **Nginx-ms:** It is commonly used as a reverse proxy and load balancer to manage incoming traffic and distribute it to slower upstream servers.
* **Kong-ms:** It is a lightweight API Gateway that secures, manages, and extends APIs and microservices.
* **Dashboard-ms**: It consists of an angular app, it is used to visualize the datasets present in postgres-ms in the form of charts. At run time, it requests spec-ms to fetch data from postgres-ms and load it into the client side (Browser).
* **Query\_builder-ms:** It consists of backend API, which consists of JWT, METRICS, QUERY APIs

JWT - It will generate a JWT token to restrict the other APIs.

METRICS - It consists of menus for the navigation bar and dashboard cards.

QUERY - This API is used for executing the SQL queries which are integrated with Dashboard-ms.

LASTMODIFIED - This api will be used for the last modified data in s3, azure and minio&#x20;

### **cQube Deployment Procedure** <a href="#cqube-deployment-procedure" id="cqube-deployment-procedure"></a>

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
* Storage\_type (Enter the storage type as local, It automatically create the minio username and minio password and minio bucket.)
* minio username
* minio password
* minio bucket

Minino can be accessed by Dashboard with [http://localhost](http://localhost/):9001 end point, here you can see the minio bucket which is created  by default and the username is minio admin and password is minio admin

Optional\_variables - Database credentials contain default values. If the user wishes to enter their own credentials then the user should opt for **yes** to enter their credentials otherwise can opt for **no** when the question pops up

* db\_user\_name ( Enter the postgres database username )&#x20;
* db\_name ( Enter the postgres database name )
* db\_password ( Enter the postgres password )

Optional\_variables- Read Only Database credentials contain default values. If the user wishes to enter their own credentials then the user should opt for **yes** to enter their credentials otherwise can opt for **no** when the question pops up

* read\_only\_db\_user ( Enter the read only postgres database username )&#x20;
* read\_only\_db\_password ( Enter the read only postgres password )

Once the config file is generated, a preview of the config file is displayed followed by a question where the user gets an option to re-enter the configuration values on choosing **yes. I**f option **no** is selected then the install.sh moves to the next section.

**Repository\_clone.sh:**

This script clones the following repositories in the micro-services directory and checks out to the required release branch:

* `git clone` [`https://github.com/Sunbird-cQube/spec-ms`](https://github.com/Sunbird-cQube/spec-ms)
* `git clone` [`https://github.com/Sunbird-cQube/ingestion-ms`](https://github.com/Sunbird-cQube/spec-ms)
* `git clone` [`https://github.com/Sunbird-cQube/generator-ms.git`](https://github.com/Sunbird-cQube/ingestion-ms.git)
* `git clone` [`https://github.com/Sunbird-cQube/generator-ms.git`](https://github.com/Sunbird-cQube/ingestion-ms.git)
* `git clone` [`https://github.com/Sunbird-cQube/query-builder.git`](https://github.com/Sunbird-cQube/dashboard-ms.git)&#x20;

<figure><img src="../../.gitbook/assets/image (10) (1).png" alt=""><figcaption></figcaption></figure>

Note: If the repository is already cloned then the script will pull the updated code.

**Ansible-playbook**

1. **Install.yml** - An install.yml ansible playbook gets triggered where it triggers the required roles to build the following microservices images.

* Ingestion-ms
* Spec-ms
* Generator-ms
* Postgres-ms
* Nifi-ms
* Dashboard-ms
* Query\_builder-ms
* Kong-ms
* Nginx-ms

<figure><img src="../../.gitbook/assets/image (3) (2).png" alt=""><figcaption></figcaption></figure>

2. **compose.yml -** A docker compose ansible script gets triggered where it will up all the containers to running state.

**Note:** The following commands can be used from the Ansible directory to down the containers and to start the containers, respectively.

* `docker-compose -f docker-compose.yml down`
* `docker-compose -f docker-compose.yml up -d`

Once the installation is completed, You will be prompted with the following messages and required reference urls.

**cQube Installed Successfully**

<figure><img src="../../.gitbook/assets/image (7) (1) (1).png" alt=""><figcaption></figcaption></figure>

We can check the containers running status by using following command

`sudo docker ps`

<figure><img src="../../.gitbook/assets/image (20).png" alt=""><figcaption></figcaption></figure>

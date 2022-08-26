**1. What is cQube?**

cQube can be used to keep an eye on a state's educational system and, on a larger scale, on schools under various levels of management.
cQube allows Data Ingestion, Data Processing, and Data Visualization.

**2.	Why are we using cQube?**

  * It generates metrics and creates the visualizations of those metrics at the defined intervals.
  * Metrics can be downloaded for further analysis.
  * It encompasses numerous use cases.

**3.	What are predefined metrics that we are using?**

Metrics mean calculations are performed on the data. Below are the predefined metrics available in current version of cQube
   * Average
   * percentage
   * sum
   * count
   * cumulative sum.
 
 **4.	What are the benefits of the cQube?**
 
 It is open source, flexible to use, and can be extended to multiple use cases as per need. It is a configurable tool.
 
 **5.	How is cQube secure more than cQube?**
 
 cQube is having the below layers in the network and The NGINX server helps to make cQube more secure. 
 
   * Private Subnet
   * Public Subnet
   * Load Balancer
   * Difined the Identity and Access Management (IAM) users and Role for S3 connectivity.
 
 The cQube is unable to hack into professional hacker networks.
 
 For Authntication security cQube is using the below ways 
   * Keycloak authentication which works with JWT
   * OTP cinfiguration with Google Authenticator
   * For the Admin, Must connect with VPN. This provides an extra layer of security for the admin activities. 
   
For more reference, Please follow the below links

(https://cqube.sunbird.org/use/network-architecture-diagram)[use/network-architecture-diagram]

https://cqube.sunbird.org/use/admin-login-process

**6.	On which platform can cQube be adopted?**

Private data center and AWS, Azure.

**7.	What is meant by use case?**

A use case is a description of how a person who uses that process or system will accomplish a goal. It's typically associated with software systems, but can be used in any process. 

Below is the link to create the new use case in cQube

https://cqube.sunbird.org/use/use-case

**8.	What is software are we using and for what and how?**

   * **Java JDK1.8:** This provides an environment for NIFI
   * **Python3:** Python plays a role in the execution of Ansible scripts and data emission API using a virtual environment.
   * **NIFI 1.12.1:** A central orchestration tool that is connected to all the different units and all the different sections to which the data flows. Data flows from                       the S3 data storage location through the data processing unit to the data visualization stage.
   * **PostgreSQL 10.12:** This is an RDBMS database to store all the processed data in a relational data format. The data stored in PostgreSQL is used by NIFI to                           prepare the JSON format files, these JSON files can be used in the visualization charts.
   * **Angular 9.1.6 + Chart.js 2.9.3 + Leaflet 1.6.0:** Angular, Chart.js, and Leaflet are used to create dashboards and user reports. The data stored in the S3                             output bucket can directly be used to create the reports.
   * **Keycloak 10.0.2:** It is a single sign-on solution for web applications and RESTful web services.
   * **Operating system:** Ubuntu 18.04 Server





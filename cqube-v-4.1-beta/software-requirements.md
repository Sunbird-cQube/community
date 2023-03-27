# Software Requirements

Operating system : Ubuntu 18.04 Server

* Java JDK1.8: This provides an environment for NIFI installation     
* Python3: Python plays a role in the execution of Ansible scripts and data emission API  using a virtual environment. 
* NIFI 1.12.1: A central orchestration tool which is connected to all the different units and all the different sections to which the data flows.   Data flows from the S3 data storage location through the data processing unit to the data visualization stage. 
* PostgreSQL 10.12: This is an RDBMS database to store all the processed data in a relational data format. The data stored in postgreSQL is used by NIFI to prepare the JSON format files, these JSON files which can be used in the visualization charts.     
* Angular 9.1.6 + Chart.js 2.9.3 + Leaflet 1.6.0: Angular, Chart.js and Leaflet are used to create dashboards and user reports. The data stored in the S3 output bucket can directly be used to create the reports. 
* Keycloak 10.0.2: It is a single sign on solution for web applications and RESTful web services. 
* Kong 2.5: It is a lightweight API Gateway that secures, manages, and extends APIs and microservices.


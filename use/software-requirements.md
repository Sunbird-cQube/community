# Software Requirements

Operating system : Ubuntu 18.04 Server

* Java JDK1.8: This provides an environment for NIFI installation     
* Python3: Python plays a role in the execution of Ansible scripts and data emission API  using a virtual environment. 
* NIFI 1.12.1: A central orchestration tool which is connected to all the units and all the  different sections where the data flows, starting from the S3 emission data location to the data visualization stage. 
* PostgreSQL 10.12: An RDBMS database to keep all the processed data in relational

  data format. The data stored here is used by NIFI to prepare the JSON format files

  which can be used in the visualization charts.     

* Angular 9.1.6 + Chart.js 2.9.3 + Leaflet 1.6.0: Angular, Chart.js and Leaflet are used to create dashboards/ user reports. The data stored in the S3 output bucket can directly be used to create the reports. 
* Keycloak 10.0.2: It is a single sign on solution for web apps and RESTful web services. 
* Kong 2.5: It is a lightweight API Gateway that secure, manage, and extend APIs and microservices.


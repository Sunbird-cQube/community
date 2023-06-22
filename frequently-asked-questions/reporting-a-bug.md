# Running List

## What is meant by use case?

A use case is a description of how a person who uses that process or system will accomplish a goal. It's typically associated with software systems, but can be used in any process.

Below is the link to create the new use case in cQube

[https://cqube.sunbird.org/use/use-case](../cqube-v-4.1-beta/use-case.md)



## Which all softwares are we using and how?

**Java JDK1.8:** This provides an environment for NIFI

**Python3:** Python plays a role in the execution of Ansible scripts and data emission API using a virtual environment.

**NIFI 1.12.1:** A central orchestration tool that is connected to all the different units and all the different sections to which the data flows. Data flows from the S3 data storage location through the data processing unit to the data visualization stage.

**PostgreSQL 10.12:** This is an RDBMS database to store all the processed data in a relational data format. The data stored in PostgreSQL is used by NIFI to prepare the JSON format files, these JSON files can be used in the visualization charts.

**Angular 9.1.6 + Chart.js 2.9.3 + Leaflet 1.6.0: Angular, Chart.js, and Leaflet** are used to create dashboards and user reports. The data stored in the S3 output bucket can directly be used to create the reports.

**Keycloak 10.0.2:** It is a single sign-on solution for web applications and RESTful web services.

**Operating system:** Ubuntu 20.04 and 22.04 Server

\

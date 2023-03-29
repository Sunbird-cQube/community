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

Enter storage\_type as 'local'. Then, install.sh will automatically get installed and configure the Minio application in localhost. It will also configure a default username and password and create a Minio bucket.

\

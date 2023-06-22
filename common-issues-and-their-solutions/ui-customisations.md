---
description: >-
  Describes how customisations on the login (UI) layer of cQube Ed v5.0 can be
  made
---

# Deployment & ingestion related issues & their solutions

## Deployment  Issues

* **Process lock issue**

When starting the deployment we might face an issue which states “Waiting for cache&#x20;

Lock: Could not get lock /var/lib/dpkg/lock-frontend”

**Resolution:**

Check for the process which is using sudo and stop the process using process id or wait till the sudo gets de-locked and restart the deployment process



* **Redeployment of dashboard-ms**

sudo docker stop dashboard\_app

sudo docker rm dashboard\_app

sudo docker dashboard\_ms:1

cd cqube-devops/microservices/dashboard-ms

sudo git pull sudo docker build -t dashboard\_ms:1 .

sudo docker run -d -p 4200:80 --network cqube\_net --name         &#x20;

dashboard\_app dashboard\_ms:1



* **Redeployment of Querybuilder-ms**

sudo docker stop querybuilder\_app

sudo docker rm querybuilder\_app

sudo docker querybuilder\_ms:1

cqube-devops/microservices/querybuilder-ms

sudo git pull

sudo docker build -t querybuilder\_ms:1

sudo docker run -d -p 3002:3002 --network cqube\_net --name querybuilder\_app

querybuilder\_ms:1



* **Port in use error while running docker-compose**

If this error arises, please check for the port which is affecting the deployment and kill the\
the port using the port ID.                        &#x20;

sudo netstat -ntlp | grep \<PORT>

sudo kill -15 \<PID>\
&#x20;                        &#x20;

Once the port is killed follow the installation script. &#x20;



## Related to ingestion

* **Single Master of Districts, Blocks, Clusters, and Schools**:

To enable decentralized observability, a single master file should be created for each jurisdiction (district, block, cluster, and school) with a unique ID and name.

Both state and national programs on cQube will reference these masters.

Any discrepancy in the master data will result in unsuccessful data ingestion.



* **Individual Values for Grade, Subject, and Medium:**

Grade, subject, and medium data should have individual values in separate rows, instead of being stored as arrays.

Each subject should have a unique ID, and different subjects should be in different rows.



* **Change in Column Name for NISHTHA Program:**

In the diksha\_nishtha\_percentage-enrollment-certification.zip file for the NISHTHA program, the first "State" column (Column B) should be renamed to "State Name\_Correct" to avoid duplication.



* **No Quotes in the Data:**

Quotes, whether single (') or double (“), should not be present in the data being ingested.



* **Numerical Values instead of Strings:**

Certain files (udise\_program-started.zip, nas\_program-started.zip, diksha\_nishtha\_program-started.zip) should use numerical values (1 and 0) instead of strings (Yes and No) in relevant columns.



* **No Commas in Large Numerical Values:**

Large numerical values in CSVs should not have commas (,) in between the digits.

These guidelines ensure data consistency, proper formatting, and accurate ingestion in the cQube system.

\

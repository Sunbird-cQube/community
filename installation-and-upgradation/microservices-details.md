---
description: >-
  Following are the details of the microservices which get installed in the
  cqube server
---

# Microservices details

* **Ingestion-ms:** The ingestion-ms is used to upload the data of the events, datasets, dimensions, transformers and pipeline. All these apis will be to ingesting the data into the cQube.
* **Spec-ms:** The spec-ms is used to import schema of the events, datasets, dimensions. All these specs will be defined by the cQube platform prior to ingesting the data into the cQube. These specifications are derived by considering the KPIs as the Indicator.
* **Generator-ms:** The generator-ms is used to create the adapters for converting the older input data format to newer format for VSK & NVSK programs.
* **Nifi-ms:** Apache NiFi is used as a real-time integrated data logistics and simple event processing platform
* **Postgres-ms:** Postgres microservice contains the schema and tables
* **Nginx-ms:** It is commonly used as a reverse proxy and load balancer to manage incoming traffic and distribute it to slower upstream servers
* **Kong-ms:** It is a lightweight API Gateway that secures, manages, and extends APIs and microservices.
* **Dashboard-ms:** It consists of an angular app, it is used to visualize the datasets present in postgres-ms in the form of charts. On run time it requests query-builder to fetch data from postgres-ms and load it into the client side(Browser)
* **Query\_builder-ms:** It consists of backend API, which consists of JWT,METRICS,QUERY apis

**JWT** - it will generate a jwt token to restrict the other apis.

**METRICS -** it consists of menus for the navigation bar and dashboard cards.

**QUERY** - this api used for executing the SQL queries which integrated with Dashboard-ms.

**LASTMODIFIED -** this api will use for the last modified data in the s3,azure and minio

\

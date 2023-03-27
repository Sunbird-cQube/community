---
description: >-
  Lists the steps to create an adapter / ETL Pipeline to ingest data from
  adopter's data sources into cQube V 5.0
---

# Step-wise Adapter Creation Process

## Overview

cQube adapter is an ETL (Extract, Transform and Load) pipeline with processes used to move data from the adopter database to multiple CSVs after making the required transformations. A cQube adapter is needed because cQube expects data in a [specific format](cqube-schemas.md) and the output CSVs of the adapter can be ingested directly into cQube to get the programs, reports and indicators.

## Architecture

<figure><img src="https://lh4.googleusercontent.com/QQhyZRpBJX9YIt15HpCu4E9cOVTng5PzM18vdw8PwKGLrXU70_ZAVctDh8xkp3_jhtrgTvo3_Trrg-rNILgTeyvzKAQQMc8viVtUZ6CqI_0tZkhPXx0gmTty9krNcdhzuYoRPnO6dt4QtSStp7DAD4Q" alt=""><figcaption><p>Flow of data from Adopter / State DB into CSV Files as per cQube Schema via adapter </p></figcaption></figure>

\
Working of an Adapter
---------------------

1. The adapter makes a connection with the state / source database.
2. It then fetches the data from the database tables&#x20;
3. It performs the transformation to generate the Dimension and Event (Fact) CSV files. The desired format and output columns list in the dimension and event file for each program can be found [here](cqube-schemas.md).
4. Output dimension CSV files will be stored inside AWS S3 Bucket / Minio / Azure in the _input-bucket/dimensions/\<dimension\_name>.data.csv_ format.&#x20;

<figure><img src="https://lh3.googleusercontent.com/aae7jd5xWMBT83moufXDxEH_moGJbPi3X-TFXTcwny1JUxHmqEzMzI4UHSo8gESyvh1qLVJA3OjoXE7bNy09rUA9pRjO_YN-pTANYmzC9fveL2X-1NrFjklOp1Pq91PL4n2Li0e_6SEGArCZMtbsThs" alt=""><figcaption><p>Dimension Files in Minio</p></figcaption></figure>

5. Output Event CSV files will be stored inside AWS S3 Bucket / Minio / Azure in the _input-bucket/combined\_input/\<program\_name>//\<event\_name>.data.csv_ format.

<figure><img src="https://lh4.googleusercontent.com/uL5fT5jogr8fpmD-MBEs-ew5N_-iH2sOtatfVoyoA06YVnKlsIthNvd73NZpUjmLRzL4yDK59b7XzyKLJ4QdwmAI_SZt6e64aC38q50GxWzX4U05_vT9eEUJR92v5OUIxm_l7rVKKQyML8NjG3HxNS0" alt=""><figcaption><p>Event Files in Minio</p></figcaption></figure>

6. This adapter ETL pipeline will run at a specific frequency so that the output CSV data can be refreshed and the latest data will be ingested into the system. To schedule your adapter, you can use Apache Airflow. Learn how to use Apache Airflow [here](https://airflow.apache.org/docs/apache-airflow/stable/start.html).

## Technology

cQube adopter can use any system, programming language or ETL tool to develop the cQube adapter.&#x20;

For example:

1. Python scripts can be used to extract data from the source / state database, transform it and finally export the CSV files inside the AWS S3 bucket or cloud storage which is being used. Apache Airflow can be used to scheduling the python scripts.
2. Or, Apache NiFi can be used to create the end-to-end ETL Pipeline.

The only requirement is that the adapter-generated CSV files should have the same column names and the data format as mentioned [here](cqube-schemas.md).

\

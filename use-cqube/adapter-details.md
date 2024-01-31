# Adapter details

**Overview**

**Metric:** A metric is a column in an event data file on which the aggregations are done to derive the insights.

CQube adapter is an ETL (Extract, Transform and Load) pipeline with processes used to move data from the adapter database to multiple CSVs after making the required transformations. A cQube adapter is needed because cQube expects data in a specific format and the output CSVs of the adapter can be ingested directly into cQube to get the programs, reports and indicators.

## Working of an Adapter  \[Currently working for National Programs]

1. The adapter makes a connection with the  state data source (ex: azure container/aws s3 bucket/oracle file system /minio bucket).Read the zipped data file from the emission folder emission/\<date>/\<file\_name>.csv.
2. It then reads the raw data files from the datasource.It performs the transformation to generate the Dimension and Event (Fact) CSV files. The desired format and output columns list in the dimension and event file for each program can be found here.
3. &#x20;Select the required column from the report(zip file).&#x20;
4. Split the files according to the number of metrics in report
5. Output Event CSV files will be stored inside AWS S3 Bucket / Minio / Azure in the input-bucket process\_input/program/\<date>/\<event\_name>-event.data.csv. process\_input/program/\<date>/\<event\_name>-dimension.data.csv Format.&#x20;
6. NiFi will run This adapter ETL pipeline will run at a specific frequency so that the output CSV data can be refreshed and the latest data will be ingested into the system.  &#x20;



Example for illustration:&#x20;

1. **Initial file**

<table data-header-hidden data-full-width="true"><thead><tr><th></th><th></th><th></th><th></th><th></th><th></th><th></th><th></th><th></th><th></th><th></th></tr></thead><tbody><tr><td>date</td><td>district_id</td><td>block_id</td><td>cluster_id</td><td>school_id</td><td>schoolcategory_name</td><td>grade</td><td>gender</td><td>KPI-1</td><td>KPI-2</td><td>KPI-3</td></tr><tr><td><br></td><td><br></td><td><br></td><td><br></td><td><br></td><td><br></td><td><br></td><td><br></td><td><br></td><td><br></td><td><br></td></tr></tbody></table>

2. **Final files**

| date | district\_id | block\_id | cluster\_id | school\_id | schoolcategory\_name | grade | gender | KPI-1 |
| ---- | ------------ | --------- | ----------- | ---------- | -------------------- | ----- | ------ | ----- |
|      |              |           |             |            |                      |       |        |       |

<table data-header-hidden><thead><tr><th></th><th width="609"></th><th></th><th></th><th></th><th></th><th></th><th></th><th></th></tr></thead><tbody><tr><td>date</td><td>district_id</td><td>block_id</td><td>cluster_id</td><td>school_id</td><td>schoolcategory_name</td><td>grade</td><td>gender</td><td>KPI-2</td></tr><tr><td><br></td><td><br></td><td><br></td><td><br></td><td><br></td><td><br></td><td><br></td><td><br></td><td><br></td></tr></tbody></table>

| date        | district\_id | block\_id   | cluster\_id | school\_id  | schoolcategory\_name | grade       | gender      | KPI-3       |
| ----------- | ------------ | ----------- | ----------- | ----------- | -------------------- | ----------- | ----------- | ----------- |
| <p><br></p> | <p><br></p>  | <p><br></p> | <p><br></p> | <p><br></p> | <p><br></p>          | <p><br></p> | <p><br></p> | <p><br></p> |

## Architecture

<figure><img src="https://lh7-us.googleusercontent.com/qA-zynQlsoN_H1GLNISWUcQpcsT4EPgzVSHeklQ34a9J5QXbGJj2ROntJo_SEiMCDrO72tzjr0gUKeWu-zMe6pQ_npkH2kOFNgtzNtZwLZy1oxChy2adbaef4gdvgWlr6tf2Q3hlDD4O7mNkTByNWUE" alt=""><figcaption></figcaption></figure>

## Technology Used

cQube adapter can use any system, programming language or ETL tool to develop the cQube adapter.&#x20;

For example:

* Python scripts can be used to extract data from the source / state database, transform it and finally export the CSV files inside the AWS S3 bucket or cloud storage which is being used. Apache Airflow can be used to scheduling the python scripts.
* Or, Apache NiFi can be used to create the end-to-end ETL Pipeline.
* The only requirement is that the adapter-generated CSV files should have the same column names and the data format as per schema\
  \
  Refer this [link](https://docs.google.com/document/d/1F9ho\_1y3sWDCzynPAzLScYT18VmuS4K-1dNOWs1z6rE/edit#heading=h.y16u3gcmp1l8) for detailed explanation

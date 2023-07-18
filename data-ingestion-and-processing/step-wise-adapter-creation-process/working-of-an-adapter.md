---
description: Currently working for National Programs only
---

# Working of an Adapter

1. The adapter makes a connection with the  state data source (ex: azure container/aws s3 bucket/oracle file system /minio bucket).Read the zipped data file from the emission folder emission/\<date>/\<file\_name>.csv.
2. It then reads the raw data files from the datasource.It performs the transformation to generate the Dimension and Event (Fact) CSV files. The desired format and output columns list in the dimension and event file for each program can be found here.
3. &#x20;Select the required column from the report(zip file).&#x20;
4. Split the files according to the number of metrics in report
5. Output Event CSV files will be stored inside AWS S3 Bucket / Minio / Azure in the input-bucket process\_input/program/\<date>/\<event\_name>-event.data.csv. process\_input/program/\<date>/\<event\_name>-dimension.data.csv Format.&#x20;
6. NiFi will run This adapter ETL pipeline will run at a specific frequency so that the output CSV data can be refreshed and the latest data will be ingested into the system.  &#x20;
7. Output Event CSV files will be stored inside AWS S3 Bucket / Minio / Azure in the _input-bucket/combined\_input/\<program\_name>//\<event\_name>.data.csv_ format.

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


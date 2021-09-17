# Admin Features

**Create users:** 

* Admin can create new cQube users from the user interface page.
* Admin will assign the role to the user while creation by choosing the role drop down value.

**S3 buckets:**

 Admin can perform view files and download actions in the S3 buckets by the following steps:

* By using the user interface admin is able to view the raw data files from the S3 input bucket, Metrics files from the S3 output buckets, Transformed and Aggregated data files from the S3 output bucket files.
* Admin can able to download the metrics files in the JSON format, transformed and Aggregated data files in CSV format from the S3 output buckets
* Apart from the user interface Admin users can call the cQube API to download the metrics files in JSON format.
* They can use the same download API to download the transaction data files and aggregated data files in CSV format from the S3 output bucket.
* The admin users use the API to download the raw files from the S3 input bucket in the zip format also.

Admin can enter the AWS console and perform the files cleanup, files Download activities

* Raw data will be downloaded in CSV format and the metrics data will be downloaded in JSON format.

**Nifi Scheduler:** 

Admin can control the Nifi processes by choosing the start and stop times.

* All the Nifi processes will be listed.
* The Schedule Time column has a drop down box with the hours. By selecting the hour the process will be automatically started at the scheduled time every day.
* The Stopping Hours column has a drop down box with the numbers. By selecting the number the scheduled running Nifi process will be stopped after the selected number of hours.
* Nifi process information was added to the schedule table to understand the status of Nifi processes whether they are in the running state or stopped state.
* Nifi schedules added another feature of scheduling for Daily, Weekly, Monthly and Yearly.
* If the user wanted to select the Daily schedule - The user has to mention the time of the schedule

If the user wanted to select the Weekly schedule - The user has to mention the Day of the Week

If the user wants to select the Monthly schedule - The user has to mention the Date of the Month. If the month is not having the specified date then the schedule will be run on the previous day of selected day  


If the user wants to select the Yearly schedule - The user has to mention the Date & Month of the Year. 

If the month is not having the specified date then the schedule will be run on the previous day of selected day  


Below are the default schedules for each data source.   


| Data Source | Start Time | Active Run Time\(In Hours\) |
| :--- | :--- | :--- |
| Static data  | 10AM | 1 hour |
| PAT Data  | 11AM  | 2 hours |
| Infrastructure Data | 1:20PM | 1 hour |
| CRC Data | 2:30PM | 2 hours |
| Teacher Attendance Data | 4:40PM | 1 hour |
| UDISE Data | 5:50PM | 2 hours |
| Student Attendance Data | 8PM | 2 hours |
| Semester Data | 10:10PM | 2 hours |
| Diksha Data | 12:20AM | 4 hours |
| Composite Report | 5:40AM | 1 hour |
| Progress card | 6:50AM |  1 hour |

**View Logs:** 

* All the log files will be consolidated into a common folder using soft links.
* New log files will be created every day and the old logs are retained for 7 days. At any point of time, there are 6 log files in the folder, old files are deleted when new files are created.   
* Admin will have an option to view the last 200 lines on the browser with the help of the user interface provided. There will be a download option provided to download the entire log file. 
* Log files will be downloaded in .log format.
* The list of log files provided to the admin are as follows:
  * Application Logs \(Error and Info logs\)
  * Admin Logs \(Angular and Node logs\)
  * System logs
  * NIFI logs
  * Data emission process logs
  * Database logs

**Grafana Dashboard Connectivity:**

Admin has an user interface screen "Monitoring Details'' screen in the admin dashboard, which connects to Grafana. And also Admin can use the Prometheus APIs to integrate with Grafana for viewing the cQube application health. The following details are displayed in the grafana dashboard:

* RAM usage
* CPU Usage 
* Data storage disk usage
* Nifi heap memory usage
* Data source file metrics
* JVM usage

**Summary Statistics:**

* Summary statistics screen is having the processed data information.
* The records count will be displayed in the Total Records column.
* The total Number of not processed records are divided into the different validation types such as Blank lines, Duplicate Records, Null records.
* Total process records count will be displayed in the Processed Records column.
* Process Start time and Process End time is represented in the remaining columns.

**Data Replay:**

Admin can be able to delete some portion of the records from the database tables and can perform the re-computation by emitting the new data for the particular records. The data replay process will be performed as explained below

* The admin screen should be prepared with a select option having all the data sources
* All the enabled data sources should be picked up dynamically from the datasource\_config.yml file from the installation directory
* Admin will select the data source and clear the data as like below

1. CRC:  Year and Month
2. Diksha ETB: From date - to date
3. Diksha TPD: Batch Ids
4. Infrastructure: Delete all data
5. PAT: Exam code
6. Semester: Academic year and the semester
7. Static: Delete all data
8. Student Attendance: Year and Month
9. Teacher Attendance: Year and Month
10. UDISE: Delete all data

* Admin will select any one option from the above list and click on the submit button
* Reset button will be placed to clear the selected values

**Data deletion operations from backend:**

* When admin submit the selected data source, A JSON file will be created with the selected values
* NIFI reads the file and clear the data from the transaction table and aggregation table for the selected period
* The new file should be emitted for the particular period again
* The new computation should happen and replace the values into the transactional table and aggregation table.
* The S3 out file should be affected with the new values.
* UI should show the new metrics on the visualization.

**Data Retention:**

Data retention has been implemented for the transaction tables of the below data sources.  


1.Semester Assessment Test - \(semester\_exam\_result\_trans\)

2.Periodic Assessment Test - \(periodic\_exam\_result\_trans\)

3.Diksha Summary rollup - \(diksha\_content\_trans\)

4.CRC - \(crc\_inspection\_trans,crc\_location\_trans\)  


By default the data retention period is set to 90 days. The retention period can be set at a 30 day interval, 30 days, 60 days, 90 days. or Under specified days until 360 days in the data retention/replay screen. 

Based on the retention period set, the data will be cleared from the transaction tables for the above sources. The data older than the retention period cannot be emitted for the above data sources, such data will be cleared and the information is logged in nifi. If the data replay is initiated for the data older than the retention period, within 5 days data re-emission is allowed.  



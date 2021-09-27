# S3 Partitioning

## S3 bucket partitioning

S3 buckets will contain partitions for the data files to store. The partitions are created at the S3 input bucket & the S3 Output bucket. 

### S3 emission bucket partitions

* All the files in the S3 emission bucket will be in the CSV format.
* S3 emission bucket follows the folder hierarchy based on the data sources. 

```text
S3 -> Bucket name -> Data source -> emitted zip files with timestamp
```

* The emitted zip file contains the CSV data files with timestamp and a manifest file with a timestamp.
* The folders and the files will be removed from the S3 emission bucket once NIFI copies the data.
* Unprocessed data files will remain in the S3 emission bucket  for one week and then they will be deleted automatically at the end of the week.

### S3 input bucket partitions

* All the files in the S3 input bucket will be in the CSV format.
* S3 input bucket follows a hierarchical partitioning based on the Data source, Year, Month, date and timestamp

```text
S3 -> Bucket name -> Data source -> Year -> Year - Month -> date_Source name
```

Example for the S3 input bucket:

```text
S3/cqube-gj-input/student_attendance/2020/2020-05/2020-05-29_student_attendance
```

###  S3 output bucket partitions

* All the files in the S3 Output bucket will be in the JSON format.
* S3 output bucket follows the hierarchical partitioning based on the data source, Year, Month, date and timestamp, similar to the partitioning that the S3 input bucket follows.
* Metadata files will have information of the latest updated output files which helps cQube to consider the latest output file during the visualization stage.


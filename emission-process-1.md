# Emission Process

### Emission flow diagram

![](.gitbook/assets/image%20%281%29.png)

### Uploading data to S3 Emission bucket:

* Data from the state education system will be emitted into the S3 emission data folder using the cQube data emission API.
* The data emission will happen from the data source location. 
* Data emission will be performed periodically as per the scheduled time interval  from different data sources with the help of an automated extraction process.
* Once the emission process extracts the data fields which are used by cQube, it is converted into csv formatted, pipe delimited files. 
* The CSV data files will then be compressed to zip format
* Emission process will invoke cQube data-ingestion APIs to emit the data.
* The API will have different end points
* Data emission users will request the cQube admin for the emission API token.
* Data emission users incorporate the API token into the emission process code.
* The Emission process makes an API call to generate AWS S3, one time presigned URL.
* API calls to emit the data files using the https protocol into cQube.
* API takes the data file as a parameter.
* The API sends an acknowledgement on successful emission.
* Create cqube\_emission directory and place the data files as shown in file structure below inside the cqube\_emission folder.

#### Master Files

```text
cqube_emission
|
├── block_master
│   └── block_mst.zip
│       └── block_mst.csv
├── cluster_master
│   └── cluster_mst.zip
│       └── cluster_mst.csv
├── district_master
│   └── district_mst.zip
│       └── district_mst.csv
├── school_master
│   └── school_mst.zip
│       └── school_mst.csv
├── pat
│   └── periodic_exam_mst.zip
│       └── periodic_exam_mst.csv
├── pat
│   └── periodic_exam_qst_mst.zip
│       └── periodic_exam_qst_mst.csv
├── diksha
│   └── diksha_tpd_mapping.zip
│       └── diksha_tpd_mapping.csv
├── diksha
│   └── diksha_api_progress_exhaust_batch_ids.zip
│       └── diksha_api_progress_exhaust_batch_ids.csv
├── sat
│   └── semester_exam_mst.zip
│       └── semester_exam_mst.csv
├── sat
│   └── semester_exam_qst_mst.zip
│       └── semester_exam_qst_mst.csv
├── sat
│   └── semester_exam_subject_details.zip
│       └── semester_exam_subject_details.csv
├── school_category
│   └── school_category_master.zip
│       └── school_category_master.csv
├── school_management
│   └── school_management_master.zip
│       └── school_management_master.csv
├── sat
│   └── semester_exam_subject_details.zip
│       └── semester_exam_subject_details.csv
├── sat
│   └── semester_exam_grade_details.zip
│       └── semester_exam_grade_details.csv
├── pat
│   └── periodic_exam_subject_details.zip
│       └── periodic_exam_subject_details.csv
├── pat
│   └── periodic_exam_grade_details.zip
│       └── periodic_exam_grade_details.csv
```

#### Transactional Files

```text
cqube_emission
|
├── student_attendance
│   └── student_attendance.zip
│       └── student_attendance.csv
├── teacher_attendance
│   └── teacher_attendance.zip
│       └── teacher_attendance.csv
├── user_location_master
│   └── user_location_master.zip
│       └── user_location_master.csv
├── inspection_master
│   └── inspection_master.zip
│       └── inspection_master.csv
├── infra_trans
│   └── infra_trans.zip
│       └── infra_trans.csv
├── diksha
│   └── diksha.zip
│       └── diksha.csv
├── pat
│   └── periodic_exam_result_trans.zip
│       └── periodic_exam_result_trans.csv
├── sat
│   └── semester_exam_result_trans.zip
│       └── semester_exam_result_trans.csv
```

* For udise data file structure, please refer the operational document.



* The example spec for the emission API will be as like below

**API headers** 

```text
{
   "Authorization":"Bearer access_token",
   "Content-Type":"application/json"
}
```

**List Buckets Endpoint**

GET https://cqube.tibilprojects.com/data/list\_s3\_buckets

Sample Output: 

```text
{
   "input":"cqube-qa10-input",
   "output":"cqube-qa10-output",
   "emission":"cqube-qa10-emission"
}
```

**List S3 Files Endpoint**

POST https://cqube.tibilprojects.com/data/list\_s3\_files

Request Body: 

```text
{
   "bucket":"cqube-qa10-emission"
}
```

**S3 Presigned Download Endpoint**

POST https://cqube.tibilprojects.com/data/download\_uri

Request Body: 

```text
{
   "filename":"school_master/2020/2020-06/2020-06-04_school_master/04-06-2020_13:12:59.574_5e160862-c5b3-4121-9a96-ecefa34fc264_school_mst.zip",
   "bucket":"cqube-gj-input"
}
```

* After getting the emission access token from admin console, update the details mentioned below in cQube\_Workflow/development/python/client/config.py.
  * Emission access token
  * File location of the cqube\_emission directory where the files are placed as below. Example:`/home/ubuntu/cqube_emission/`
  * Emission End point i.e., emission\_url  Ex:`https://<cqube-domain>/data` Note: URL depends upon the server configured in firewall which includes SSL and reverse proxy location\)
* After completing the configuration. Save and close the file.
* Execute the client.py file located in `cQube_Workflow/development/python/client/` directory, as mentioned below to emit the data files to s3\_emission bucket.

  ```text
  python3 client.py
  ```

* Finally see the output in `https://<cqube_domain>/`


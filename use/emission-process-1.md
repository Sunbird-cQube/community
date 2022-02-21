# Emission Process

## Emission flow diagram

![](../.gitbook/assets/image%20%281%29%20%281%29.png)

## Uploading data to S3 Emission bucket:

* Data from the state education system will be emitted into the S3 emission data folder using the cQube data emission API.
* The data emission will happen from the data source location. 
* Data emission will be performed periodically as per the scheduled time interval  from different data sources with the help of an automated extraction process.
* Once the emission process extracts the data fields which are used by cQube, it is converted into csv formatted, pipe delimited files. 
* The CSV data files will then be compressed to zip format
* Emission process will invoke cQube data-ingestion APIs to emit the data.
* The API will have different end points
* Data emission users will request the cQube admin for the emission API token.
* Data emission users incorporate the API token into the emission process code.
* The Emission process makes an API call to generate AWS S3, one time preassigned URL.
* API calls to emit the data files using the https protocol into cQube.
* API takes the data file as a parameter.
* The API sends an acknowledgement on successful emission.
* Create cqube\_emission directory and place the data files as shown in file structure below inside the cqube\_emission folder.

### Static Files

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
├── diksha_enrolment
│   └── diksha_enrolment.zip
│       └── diksha_enrolment.csv
├── diksha_enrolment
│   └── diksha_etb_enrolment.zip
│       └── diksha_etb_enrolment.csv
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

### Transaction Files

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
│   └── diksha_data_summary.zip
│       └── diksha_data_summary.csv
├── diksha
│   └── diksha_tpd.zip
│       └── diksha_tpd.csv
├── pat
│   └── periodic_exam_result_trans.zip
│       └── periodic_exam_result_trans.csv
├── sat
│   └── semester_exam_result_trans.zip
│       └── semester_exam_result_trans.csv
```

**UDISE Files**

```text
├── udise
│   └── sch_facility.zip
│       └── sch_facility.csv
├── udise
│   └── nsqf_plcmnt_c12.zip
│       └── nsqf_plcmnt_c12.csv
├── udise
│   └── nsqf_plcmnt_c10.zip
│       └── nsqf_plcmnt_c10.csv
├── udise
│   └── nsqf_class_cond.zip
│       └── nsqf_class_cond.csv
├── udise
│   └── sch_exmres_c12.zip
│       └── sch_exmres_c12.csv
├── udise
│   └── sch_exmres_c10.zip
│       └── sch_exmres_c10.csv
├── udise
│   └── sch_exmres_c5.zip
│       └── sch_exmres_c5.csv
├── udise
│   └── sch_incen_cwsn.zip
│       └── sch_incen_cwsn.csv
├── udise
│   └── sch_enr_by_stream.zip
│       └── sch_enr_by_stream.csv
├── udise
│   └── sch_enr_cwsn.zip
│       └── sch_enr_cwsn.csv
├── udise
│   └── sch_enr_medinstr.zip
│       └── sch_enr_medinstr.csv
├── udise
│   └── sch_enr_age.zip
│       └── sch_enr_age.csv
├── udise
│   └── sch_enr_newadm.zip
│       └── sch_enr_newadm.csv
├── udise
│   └── sch_enr_reptr.zip
│       └── sch_enr_reptr.csv
├── udise
│   └── sch_enr_fresh.zip
│       └── sch_enr_fresh.csv
├── udise
│   └── sch_staff_posn.zip
│       └── sch_staff_posn.csv
├── udise
│   └── sch_exmmarks_c10.zip
│       └── sch_exmmarks_c10.csv
├── udise
│   └── sch_exmmarks_c12.zip
│       └── sch_exmmarks_c12.csv
├── udise
│   └── nsqf_exmres_c10.zip
│       └── nsqf_exmres_c10.csv
├── udise
│   └── nsqf_exmres_c12.zip
│       └── nsqf_exmres_c12.csv
├── udise
│   └── nsqf_trng_prov.zip
│       └── nsqf_trng_prov.csv
├── udise
│   └── nsqf_faculty.zip
│       └── nsqf_faculty.csv
├── udise
│   └── sch_exmres_c8.zip
│       └── sch_exmres_c8.csv
├── udise
│   └── sch_profile.zip
│       └── sch_profile.csv
├── udise
│   └── tch_profile.zip
│       └── tch_profile.csv
├── udise
│   └── sch_recp_exp.zip
│       └── sch_recp_exp.csv
├── udise
│   └── nsqf_basic_info.zip
│       └── nsqf_basic_info.csv
├── udise
│   └── nsqf_enr_caste.zip
│       └── nsqf_enr_caste.csv
├── udise
│   └── nsqf_enr_sub_sec.zip
│       └── nsqf_enr_sub_sec.csv
├── udise
│   └── sch_pgi_details.zip
│       └── sch_pgi_details.csv
├── udise
│   └── sch_safety.zip
│       └── sch_safety.csv
├── udise
│   └── sch_incentives.zip
│       └── sch_incentives.csv
```

* The example spec for the emission API will be as like below

## Emission file naming conventions & structure:

* All the files should be in a CSV format with PIPE\("\|"\) separated.
* The data files should be emitted individually in zip format.
* The list of columns which have to be emitted for a data source are provided in the [file](https://docs.google.com/spreadsheets/d/16t_YpoKFkXK6NBrVZPgSbzdtM5GLptLC0ZKZmAMB1vg).
* The header should be in the same order as described in the [file](https://docs.google.com/spreadsheets/d/16t_YpoKFkXK6NBrVZPgSbzdtM5GLptLC0ZKZmAMB1vg), for that respective data set.
* Data emission overview of data flow can be viewed [here](https://docs.google.com/document/d/1wXWIf7MDEShmNxIq32NgwMGkWwYucMPNd-TaUpmLhIc/edit)
* Below is the list of data sources used in various reports. 

| Source Name | Used in report | cQube Data Source Name |
| :--- | :--- | :--- |
| District Master | All reports | district\_master |
| Block Master | All reports | block\_master |
| Cluster Master | All reports | cluster\_master |
| School Master | All reports | school\_master |
| CRC Inspection Master | CRC Report | inspection\_master |
| CRC User Location Master | CRC Report | user\_location\_master |
| Student Attendance | SAR Report | student\_attendance |
| Infrastructure Master | Infrastructure Report | infra\_trans |
| Semester | SEMESTER Report | semester |
| Diksha | DIKSHA | diksha |
| School Facility | UDISE | sch\_facility |
| NSQF Class 12 Placement | UDISE | nsqf\_plcmnt\_c12 |
| NSQF Class 10 Placement | UDISE | nsqf\_plcmnt\_c10 |
| NSQF Class Condition | UDISE | nsqf\_class\_cond |
| School Exam Result Class 12 | UDISE | sch\_exmres\_c12 |
| School Exam Result Class 10 | UDISE | sch\_exmres\_c10 |
| School Exam Result Class 5 | UDISE | sch\_exmres\_c5 |
| School Incentives CWSN | UDISE | sch\_incen\_cwsn |
| School Enrollment by stream | UDISE | sch\_enr\_by\_stream |
| School Enrollment by CWSN | UDISE | sch\_enr\_cwsn |
| School Enrollment by Medium of Instruction | UDISE | sch\_enr\_medinstr |
| School Enrollment by Age | UDISE | sch\_enr\_age |
| School Enrollment by Report | UDISE | sch\_enr\_reptr |
| School Enrollment by Fresh | UDISE | sch\_enr\_fresh |
| School Enrollment by New Admission | UDISE | sch\_enr\_newadm |
| School staff position | UDISE | sch\_staff\_posn |
| School Exam Class 10 marks | UDISE | sch\_exmmarks\_c10 |
| School Exam Class 12 marks | UDISE | sch\_exmmarks\_c12 |
| NSQF Exam Class 10 Results | UDISE | nsqf\_exmres\_c10 |
| NSQF Exam Class 10 Results | UDISE | nsqf\_exmres\_c12 |
| NSQF Training Provision | UDISE | nsqf\_trng\_prov |
| NSQF Faculty | UDISE | nsqf\_faculty |
| School Exam class 8 results | UDISE | sch\_exmres\_c8 |
| School Profile | UDISE | sch\_profile |
| Teacher Profile | UDISE | tch\_profile |
| School Receipt Expenditure | UDISE | sch\_recp\_exp |
| NSQF Basic information | UDISE | nsqf\_basic\_info |
| NSQF Enrollment by Caste | UDISE | nsqf\_enr\_caste |
| NSQF Enrollment by Sub section | UDISE | nsqf\_enr\_sub\_sec |
| School PGI Indicators | UDISE | sch\_pgi\_details |
| School Safety | UDISE | sch\_safety |
| School Incentives | UDISE | sch\_incentives |
| Periodic Exam Master | Periodic Exams | periodic\_exam\_mst |
| Periodic Exam Question Master | Periodic Exams | periodic\_exam\_qst\_mst |
| Periodic Exam Results | Periodic Exams | periodic\_exam\_result\_trans |
| Semester Exam Master | Semester Exams | semester\_exam\_mst |
| Semester Exam Question Master | Semester Exams | semester\_exam\_qst\_mst |
| Semester Exam Results | Semester Exams | semester\_exam\_result\_trans |

**API headers**

```text
{
   "Authorization":"Bearer access_token",
   "Content-Type":"application/json"
}
```

**List Buckets Endpoint**

GET [https://cqube.tibilprojects.com/data/list\_s3\_buckets](https://cqube.tibilprojects.com/data/list_s3_buckets)

Sample Output:

```text
{
   "input":"cqube-qa10-input",
   "output":"cqube-qa10-output",
   "emission":"cqube-qa10-emission"
}
```

**List S3 Files Endpoint**

POST [https://cqube.tibilprojects.com/data/list\_s3\_files](https://cqube.tibilprojects.com/data/list_s3_files)

Request Body:

```text
{
   "bucket":"cqube-qa10-emission"
}
```

**S3 Preassigned Download Endpoint**

POST [https://cqube.tibilprojects.com/data/download\_uri](https://cqube.tibilprojects.com/data/download_uri)

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

### Emission order & instructions:

* Static files as defined in above in this page need to be emitted first.
* For the CRC report, the inspection\_master needs to be emitted prior to user\_location\_master to visualize the CRC reports.
* For PAT \(Periodic assessment report\), periodic\_exam\_mst and periodic\_exam\_qst\_mst needs to be emitted prior to periodic\_exam\_result\_trans
* school\_grade\_enrolment file can be emitted either as periodic\_exam\_grade\_details or semester\_exam\_grade\_details. The data will be updated to school\_grade\_enrolment and will be used in school\_hierarchy\_details. The count from school\_hierarchy details will be used in pat & sat reports. Before the sat & pat workflow the school\_grade\_enrolment needs to be emitted.
* Execute the client.py file located in `cQube_Workflow/development/python/client/` directory, as mentioned below to emit the data files to s3\_emission bucket.

```text
python3 client.py
```

* Finally see the output in `https://<cqube_domain>/`


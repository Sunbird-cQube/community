# cQube data replay process

The data replay process takes place based on the data source. Mentioned below are the steps that are involved in the data replay process:

● Admin will be provided with a screen to select the options to clear the data for each of the data sources. The admin screen will contain the following selection options:

1. For student attendance, Teacher attendance the admin will be able to select the ‘year and month’ using the year & month drop down.
2. For CRC and Diksha summary rollup the admin will have the calendar selection. The data will be deleted for the selected dates.
3. For the Semester reports, admin will be able to select the required semester from the available semesters. The selected semester data will be deleted.
4. For Periodic Assessment Test, admin selects the exam code option from the multiple select box which is having all the available exam codes. The complete data which is related to the selected exam code will be deleted.
5. For Diksha TPD, Admin selects the Batch ID option from the select box which is having all the available Batch IDs. The complete data which is related to the selected Batch ID will be deleted.
6. For UDISE & Infrastructure data sources, admin can delete overall data with the selection of ‘Yes or No’ option from the select box. Full refresh will happen with the new data.
7. For the static data sources, admin can delete overall data with the selection of ‘Yes or No’ option from the select box. Full refresh will happen with the new data.

● A submit and Reset all buttons will be given in the admin screen to Submit the request and reset the options.\
● When admin clicks on submit button, All the data sources will be created as JSON file as shown below

```
{"student_attendance": { 
"year":"2020",
"months":["01", "03"] 
}, 
"teacher_attendance": { 
"year":"2020",
"months":["01", "03"]
},
"crc": {
"year":"2020", 
"months":["01", "03"]
},"diksha_summary_rollup": { 
"from_date":"", 
"to_date":"" 
},
"semester": { 
"semester":[1,2] 
}, 
"periodic_assessment_test": { 
"exam_code":["PAT010101012021", "PAT010201012021"] 
}, 
"diksha_tpd": { 
"batch_id":["03052315462389", "046789546783"] 
}, 
"udise": { 
"selection":"yes/no" 
}, 
"Infrastructure": { 
"selection":"yes/no" 
}, 
"static": { 
"selection":"yes/no" 
}
}
```

● The JSON file containing the values selected by the admin will be placed in the S3 emission bucket.\
● A scheduler will be created for the data replay process for all reports. And the scheduler will run based on the schedule defined by the admin.\
● The scheduler will initiate the NIFI to get the file from S3 input bucket. NIFI performs the data deletion operation based on the inputs given by the admin (for all the data sources).

## Data deletion process

Once the file is emitted to the S3 bucket, NIFI function will be invoked at the scheduled time and get the input parameters from the JSON file. The queries will be executed and delete the data from transaction tables. Once the workflow is run the output files will be updated according to the deleted data.

## Data reprocessing (for previously deleted data) flow

Data reprocessing will take place in the normal cQube emission process.

● The latest data file will be emitted to S3 emission bucket

● The file will be processed as the regular data process from NIFI All the validations will be performed by NIFI and the validated data will be inserted into the transaction tables.

● All the metrics will be re-calculated and updates of the output files.

● The new metrics will be affected in the reports.

The complete workflow process will be like below.

![Workflow Process](<../.gitbook/assets/image (6) (2) (2) (1) (2).png>)

List of tables cleared for the data source

| datasource                 | parameter           | list of tables                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            | function call                                                                                                                               |
| -------------------------- | ------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- |
| student\_attendance        | month,year          | student\_attendance\_meta,student\_attendance\_staging\_1,student\_attendance\_staging\_2,student\_attendance\_trans,school\_student\_total\_attedance                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    | select del\_data(p\_data\_source=>'student\_attendance',p\_year=>2022,VARIADIC p\_month=>array\[1,2]);                                      |
| teacher\_attendance        | month,year          | teacher\_attendance\_meta,teacher\_attendance\_staging\_1,teacher\_attendance\_staging\_1,teacher\_attendance\_temp,teacher\_attendance\_trans,school\_teacher\_total\_attendance                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         | select del\_data(p\_data\_source=>'teacher\_attendance',p\_year=>2022,VARIADIC p\_month=>array\[1,2]);                                      |
| crc                        | month,year          | crc\_location\_trans,crc\_inspection\_trans,crc\_visits\_frequency                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        | select del\_data(p\_data\_source=>'crc',p\_year=>2022,VARIADIC p\_month=>array\[1,2]);                                                      |
| semester\_assessment\_test | exam\_code/semester | semester\_exam\_mst,semester\_exam\_result\_staging\_2,semester\_exam\_school\_qst\_result,semester\_exam\_result\_temp,semester\_exam\_school\_result,semester\_exam\_qst\_mst,semester\_exam\_result\_staging\_1,semester\_exam\_result\_trans                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          | select pat\_del\_data(p\_data\_source=>'periodic\_assessment\_test',VARIADIC p\_exam\_code=>array\['PAT0302290720201','PAT0302290720202']); |
| periodic\_assessment\_test | exam\_code          | periodic\_exam\_mst,periodic\_exam\_result\_staging\_2,periodic\_exam\_school\_qst\_result,periodic\_exam\_result\_temp,periodic\_exam\_school\_result,periodic\_exam\_qst\_mst,periodic\_exam\_result\_staging\_1,periodic\_exam\_result\_trans                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          | select pat\_del\_data(p\_data\_source=>'periodic\_assessment\_test',VARIADIC p\_exam\_code=>array\['PAT0302290720201','PAT0302290720202']); |
| diksha\_tpd                | batch\_id           | diksha\_tpd\_agg,diksha\_tpd\_trans,diksha\_tpd\_content\_temp,diksha\_tpd\_staging                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       | select diksha\_tpd\_del\_data(p\_data\_source=>'diksha\_tpd',VARIADIC p\_batch\_id =>array\['0302290720201','0302290720202']);              |
| diksha\_summary\_rollup    | from\_date,to\_date | diksha\_content\_staging,diksha\_content\_temp,diksha\_content\_trans,diksha\_total\_content                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              | select diksha\_summary\_rollup\_del\_data('diksh a\_summary\_rollup','2022-12-27','2022-1 2-31');                                           |
| infrastructure             | all                 | infrastructure\_temp,infrastructure\_trans                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                | select all\_del\_data('infrastructure');                                                                                                    |
| static                     | all                 | block\_tmp,block\_mst,district\_tmp,district\_mst,cluster\_tmp,cluster\_mst,school\_master,school\_tmp,school\_hierarchy\_details,school\_geo\_master                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     | select all\_del\_data('static');                                                                                                            |
| udise                      | all                 | udise\_sch\_incen\_cwsn,udise\_nsqf\_plcmnt\_c12 udise\_sch\_enr\_reptr,udise\_nsqf\_basic\_info,udise\_sch\_incentives,udise\_nsqf\_trng\_prov,udise\_sch\_exmmarks\_c10, udise\_nsqf\_class\_cond,udise\_school\_metrics\_trans,udise\_sch\_exmmarks\_c12 udise\_sch\_pgi\_details,udise\_nsqf\_enr\_caste,  udise\_sch\_enr\_age,udise\_sch\_exmres\_c10,udise\_sch\_profile,udise\_nsqf\_enr\_sub\_sec,udise\_sch\_enr\_by\_stream, udise\_sch\_exmres\_c12,udise\_sch\_recp\_exp,udise\_nsqf\_exmres\_c10,udise\_sch\_enr\_cwsn,udise\_sch\_exmres\_c5,udise\_sch\_safety, udise\_nsqf\_exmres\_c12,udise\_sch\_enr\_fresh, udise\_sch\_exmres\_c8,udise\_sch\_staff\_posn,udise\_nsqf\_faculty,udise\_sch\_enr\_medinstr, udise\_sch\_facility,udise\_tch\_profile,udise\_nsqf\_plcmnt\_c10,udise\_sch\_enr\_newadm | select all\_del\_data('udise');                                                                                                             |

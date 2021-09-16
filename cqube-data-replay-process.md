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

● A submit and Reset all buttons will be given in the admin screen to Submit the request and reset the options.  
● When admin clicks on submit button, All the data sources will be created as JSON file as shown below

```text
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

● The JSON file containing the values selected by the admin will be placed in the S3 emission bucket.  
● A scheduler will be created for the data replay process for all reports. And the scheduler will run based on the schedule defined by the admin.  
● The scheduler will initiate the NIFI to get the file from S3 input bucket. NIFI performs the data deletion operation based on the inputs given by the admin \(for all the data sources\).

### Data deletion process

Once the file is emitted to the S3 bucket, NIFI function will be invoked at the scheduled time and get the input parameters from the JSON file. The queries will be executed and delete the data from transaction tables. Once the workflow is run the output files will be updated according to the deleted data.

### Data reprocessing \(for previously deleted data\) flow

Data reprocessing will take place in the normal cQube emission process. 

● The latest data file will be emitted to S3 emission bucket 

● The file will be processed as the regular data process from NIFI All the validations will be performed by NIFI and the validated data will be inserted into the transaction tables. 

● All the metrics will be re-calculated and updates of the output files. 

● The new metrics will be affected in the reports. 

The complete workflow process will be like below.

![Workflow Process](.gitbook/assets/image%20%286%29.png)




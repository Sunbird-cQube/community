# Datasource Configuration

cQube supports creating new data sources using configuration files. Through which User can enter the required details like the name of the new data source, columns , data types, Metric type and type of visualization reports. 

Through configuration files, Users can also create new reports with the existing data sources.

**List of report types supported through configuration**

- Map report
- Table report
- Heat chart
- Bar chart
- Multi Bar chart
- Pie chart
- Line chart



Below is the link for sample configuration file format

[sample configuration file](https://github.com/Sunbird-cQube/community/blob/master/use/textbook_distribution.csv)


**steps to create the configuration file**

**secion-1 []**
- Table_name: The Table/datasource name
- Columns: The column names in the raw data file.
- Data_Type:  The postgres supported data types.
- Constraints: The postgres supported contraints
- Ref_Table: If constraint is foreign key, then specify the referenced table name.
- Ref_column: If constraint is foreign key, then specify the referenced column name.
- Null_validation_required: column to be included in null validation.
- check_same_id:  Column to be included in same id duplicate validation.

**secion-2 [table_1_trans]**

- level_of_data: Type/level of raw data. Example: school or student level.

- filters_required: dimensions of data required in UI
 Example: District/block/cluster/ etc..

- time_selections: supported time selections
    - daily
    - weekly
    - monthly
    - last_30_days
    - last_7_days
    - overall

- date_column_to_filter: date column to consider for metrics generation.
- nifi_select_columns: columns to display on UI.

**secion-2 [type_of_data]**

- metric_type: supported metric_type
    - sum.
    - count.
    - cummulative. 
    - percentage.


**Steps to configure the new data source**
- Prepare the configuration file according to the above link, save as csv and compress to .zip format.
- Schedule the configure_datasource processor group under admin console --> NiFi scheduler.
- Emit the zipped configuration file to the emission directory  in the below directory structure.
Filename should be the datasource name.
```text
├── configure_datasource
│   └── datasourcename.zip
│       └── datasourcename.csv
```
- Navigate to the admin console/Logs and check the NiFi app log

On successfull file processing, you should see the below message 
 ```
 **** Succesfully Executed! ****
 file: <filename> executed succesfully.
```
- Navigate to the admin console page, Click on configuration, Under configurable Data Source section
click the drop drown and choose the new data source and click Submit.

- Wait until the timer stops. Then go to the scheduler page, On successful build, you should see the new data source name under the list and schedule the newly added data source.

- Emit the file into ```new_datasource_name/```  directory into emission directory.
- After data processing,the configured reports will be available with data in cQube Dashboard.

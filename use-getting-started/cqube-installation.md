# cQube Setup

The cQube product can be installed in a two-step installation process. cQube installation package is divided into below 2 components 

* cQube base installation
* cQube workflow Installation

**cQube base installation:** The cQube base installation installs the complete cQube stack, which includes Ansible automation scripts to install Java, Python, NIFI, Angular, ChartJS, Leaflet and PostgreSQL installations. All the softwares will be installed without any data or data processing units. S3 emission data, S3 input bucket, S3 output bucket and the remaining S/W configurations will be taken care by cQube base installation. 

**cQube Workflow installation:** The cQube Workflow installation is the top-up layer of the cQube base installation. Once the cQube base installation is completed, Admin has to start the cQube workflow installation. 

Based on the data source configuration the following are setup

* Database tables will be created at PostgreSQL from the relevant data source sql files. 
* NIFI data processor groups will be created by using the relevant data source nifi  templates and the parameters will be updated based on the configurations set. 
* The reports will be shown for the enabled data source in angular dashboard.

**cQube - Configurations**

Configurations are done as a part of the installation process by the ansible scripts. All the properties of the sensible information like URLs and passwords are saved in the ansible properties file which is encrypted by default. Configuration is an automated process, no manual interactions are required in this stage. 

cQube configurations through Ansible code:

* Nifi template would be uploaded & instantiated with the variables & parameters.
* All the Nifi controllers will be enabled and all the Nifi processors will be started.
* Postgres static, transaction, aggregation tables will be created in the newly created database.

The below configurations should be done in cQube while the installation and the data process.

*  Enable / Disable the process groups - At installation time
*  Keycloak two factor authentication - Need to verify for the roles Admin and Report viewer  togo with 2 factor authentications at the time of login.
* Nifi process configurations - Change the query parameters for Nifi process and verify whether those are affecting the process or not
* Infrastructure configuration - Need to check if the selected infra values are affecting or not.

 The above four configurations in explanation,

#### State specific configurations

This configuration should be performed at the installation stage of cQube. The state will be specified in the config.yml file. The state code will be specified with 2 letters of uppercase characters which are referred from the below file.

[https://github.com/project-sunbird/cQube/blob/release-1.7/ansible/installation\_scripts/state\_list](https://github.com/project-sunbird/cQube/blob/release-1.7/ansible/installation_scripts/state_list)

#### Enable / Disable the process groups

This configuration should be performed at the installation / Up-gradation stage of cQube. The cQube user may select the process groups which they wanted to include into the cQube. While the installation / Up-gradation of the cQube user will be available to select the existing process group by giving the true / false in the datasource\_config.yml document which is available at the link below.

[https://github.com/project-sunbird/cQube/blob/release-1.2.1/ansible/installation\_scripts/datasource\_config.yml](https://github.com/project-sunbird/cQube/blob/release-1.2.1/ansible/installation_scripts/datasource_config.yml)

All the configuration should be given like below,

```text
crc: true
attendance: true
infra: true
diksha: true
telemetry: true
udise: true
pat: true
composite: true
progresscard: true
teacher_attendance: true
data_replay: true
sat: true
```

As of now there are a total of 12 processor groups available in cQube.

#### Keycloak Two-Factor Authentication

Keycloak will allow single sign-on with Identity and Access Management services to cQube. Keycloak will be configured to cQube at the time of installation in the execution process of install.sh command. If two factor authentication is set up the below screen would appear after first time login for all the users. Users need to set up two factor authentication for the first time from his/her mobile using the Google authenticator.

Figure : QR code registration for 2 factor authentication ![](https://lh6.googleusercontent.com/rbRWqEk6wtxadP678tTHE43-hQdOwa98ta1v4wzoH_nZpbyaHurJ3E7-ud4JtkIfh3M_T7Il-hUOzBxiM4g23SzIdhQ5D3jhepe4QsmjmEGWtZwyUeDHQ73EukQFoZMZPACC2AcF=s0)

  Below are steps:

* Download Google Authenticator app into your mobile.
* Scan the QR code to integrate cQube dashboard with Google authenticator app.
*  Provide the OTP to login.

#### Session time-out

Session time should be mentioned in the config.yml File during the installation / Upgradation. 

The default time for the session expiry would be 7 days. Users have the facility to decrease the session out time to a minimum of 30 minutes and maximum of 3650 days.  


Minutes should be mentioned as ‘M’ and Days mention ‘D’. 

Example: 7D for 7 days 

                30M for 30 minutes

#### Nifi query parameter configurations

The Nifi configuration process allows us to change the query parameters before the installation process starts. To change the query of a nifi processor, we need to update the query parameter of that processor. 

*  Query should be re constructed outside the cQube. 
*  Query parameters should be defined in the configuration files of the nifi processor group.
* Additional filters can be added in the query parameter. 
* Cast, round other functions can be used to update the query in the parameter configuration.
* The query in the NIFI process should be replaced with the new Query.
* The Query results should be affected on UI Reports.
* Below are a few examples to add or remove filters & apply functions to the query.

Example:  


1. Adding a filter to the existing query for the static processor  


By default the static\_get\_invalid\_names parameter in static\_data\_parameters.txt would be  


The Original Query:

"static\_get\_invalid\_names":'''select school\_id,school\_name,block\_id,district\_id,cluster\_id from school\_hierarchy\_details where cluster\_name is null or block\_name is null or district\_name is null  


The Updated Query:

"static\_get\_invalid\_names":'''select school\_id,school\_name,block\_id,district\_id,cluster\_id from school\_hierarchy\_details where cluster\_name is null or block\_name is null or district\_name is null or school\_name is null''',  


Output: By adding the additional filter to not allow the school\_name with null records into cQube reports.  


2. Updating infra parameter based on active infrastructure attributes

By default the infra\_normalize parameter in infra\_parameters.txt would be  


The Original Query parameter:  


"infra\_normalize":'''select school\_id ,

case when HaveDrinkingWater &lt;&gt;1 then 0 else 1 end as drinking\_water,

case when NoOfToilet=0 or NoOfToilet is null then 0 else 1 end as toilet,

case when HaveCWSNToilet &lt;&gt;1 then 0 else 1 end as cwsn\_toilet,

case when HaveElectricity &lt;&gt;1 then 0 else 1 end as electricity,

case when HaveCCTV &lt;&gt;1 then 0 else 1 end as cctv,

case when HaveLibrary &lt;&gt;1 then 0 else 1 end as library from flowfile'''  


The above query parameter can be changed according to the data fields activated by the state.  


If only three of the fields choose to be activated by the state the query needs to be updated as below.  


The Updated Query parameter:  


"infra\_normalize":'''select school\_id ,

case when NoOfToilet =0 then 0 else 1 end as toilet,

case when HaveElectricity&lt;&gt;1 then 0 else 1 end as electricity,

case when solarpanel\_yn=TRUE then 1 else 0 end as solar\_panel from flowfile'''  


We need to update the query in the infrastructure configuration file i.e., infra\_parameters.txt file after that the installation process can be started. This will map with the infrastructure input data with the cQube database tables.

#### Infrastructure configuration

cQube is having the flexibility to support multiple state data with minimal changes in UI code for the fluctuated data sources like Infrastructure,  Infrastructure score weights, Semester assessment subjects. 

Below Steps will be performed to implement the database configuration stage:

* Before cQube is installed, the infrastructure data source needs to be configured depending on the emission data fields required by the state in the infrastructure configuration file.
* Depending on the infrastructure attributes and its datatype the infrastructure query parameter, a case statement is written to map the input data field and the cQube infrastructure table. 
* The case statement needs to be updated in the infrastructure configuration file [infra\_parameters.txt](https://github.com/project-sunbird/cQube/blob/release-1.8/development/python/infra_parameters.txt) file by updating the parameter: infra\_normalize.
* From the below table the infra\_normalize parameter will look like :

"infra\_normalize":'''select school\_id ,

case when NoOfToilet =0 then 0 else 1 end as toilet,

case when HaveElectricity&lt;&gt;1 then 0 else 1 end as electricity,

case when solarpanel\_yn=TRUE then 1 else 0 end as solar\_panel from flowfile''',  


* Example table :

| datatype | input data | infrastructure\_master.csv | case statement |
| :--- | :--- | :--- | :--- |
| integer | NoOfToilet | Toilet | case when NoOfToilet =0 then 0 else 1 end as toilet, |
| bit | HaveElectricity | Electricity | case when HaveElectricity&lt;&gt;1 then 0 else 1 end as electricity, |
| boolean | Solar Panel | Solar Panel | case when solarpanel\_yn=TRUE then 1 else 0 end as solar\_panel, |

Note :- For infrastructure\_master column the values should be converted to lowercase and spaces are converted to underscore\(\_\) example : Solar Panel converted to solar\_panel

* Based on the configuration, the changes are made to handle state specific data fields
* After successful validations, data tables are created with only active and required data fields for the active data fields are processed and metrics are generated
* The metrics generated will be stored in JSON files, which is used for visualization
* Change only the score & status of the infrastructure in [infrastructure\_master.csv](https://github.com/project-sunbird/cQube/blob/release-1.8/development/postgres/infrastructure_master.csv), don't update any other column values.
* Make sure the sum of score of all infrastructure is 100 \(For status=1\(active\)\)

To select the infrastructure fields, please fill the details in infrastructure\_master.csv file which is available at the link below.

https://github.com/project-sunbird/cQube\_Base/blob/release-1.8/development/postgres/infrastructure\_master.csv

The Infrastructure calculation will happen as in the below example.

If a school has drinking water, handwash, electricity, toilet, playground, hand pumps, library then the score would be calculated as below

$$20*1 + 10*1 + 10*1 + 20*1 + 20*1 + 10*1 + 10*1 = 100$$ 

The total infrastructure score would be 100, if the school does not have any infrastructure available, then for that infrastructure it would be awarded with 0.

If the school does not have playground, handpump, library, the score would be calculated as

$$20*1 + 10*1 + 10*1 + 20*0 + 20*1 +10*0 + 10*0 = 60$$ 

The total infrastructure score would be calculated to 60.

If we need to calculate the score at different levels such as district, block, cluster, the school infrastructure count would be added for all the blocks, clusters, districts.

To get the infrastructure score at district, block, cluster add all the infrastructure of all the schools available.

$$Weight * (infrastructure of all the school/ Total number of schools)$$ 

For example, if there are two schools in cluster the infrastructure score would be calculated as below$$20*(1+1)/2 + 10*(1+0)/2 + 10*(1+1)/2 + 20*(0+0)/2 + 20*(1+1)/2 +10*(0+0)/2 + 10*(0+0)/2 = 55$$ 

Infrastructure score for the cluster would be 55.

The Metrics will be stored in the JSON files for infrastructure visualization. An example JSON document for the district infrastructure is given below:

```text
{
   "district":{
      "id":2101,
      "value":"test_district_name"
   },
   "block":{
      "value":"test_block_name",
      "id":210107
   },
   "infra_score":{
      "value":"79.00"
   },
   "average":{
      "value":"170",
      "percent":"79.81"
   },
   "total_schools":{
      "value":213
   },
   "total_schools_data_received":{
      "value":"213"
   },
   "hand wash":{
      "value":"213",
      "percent":"100.00"
   },
   "solar_panel":{
      "value":"203",
      "percent":"95.31"
   },
   "library":{
      "value":"210",
      "percent":"98.59"
   },
   "drinking_water":{
      "value":"13",
      "percent":"6.10"
   },
   "tap_water":{
      "value":"13",
      "percent":"6.10"
   },
   "hand_pumps":{
      "value":"158",
      "percent":"74.18"
   },
   "playground":{
      "value":"159",
      "percent":"74.65"
   },
   "news_paper":{
      "value":"213",
      "percent":"100.00"
   },
   "digital_board":{
      "value":"3",
      "percent":"1.41"
   },
   "electricity":{
      "value":"207",
      "percent":"97.18"
   },
   "toilet":{
      "value":"213",
      "percent":"100.00"
   },
   "boys_toilet":{
      "value":"213",
      "percent":"100.00"
   },
   "girls_toilet":{
      "value":"213",
      "percent":"100.00"
   }
}
```

Steps to be taken in case of upgradation:

1. In case of upgradation the infrastructure score and status needs to be updated in the cQube/development/postgres/infrastructure\_master.csv as per the existing active fields and weights configured in the previous release.

#### U-DISE configuration

cQube is having the flexibility to support configuring multiple indices and its metrics with minimal changes in UI code for udise indices and metrics, udise score weights and there are 32 input data files updated in this page that need to be emitted to visualise the UDISE report.   


Below Steps needs to be performed to implement the UDISE configuration stage:

* Before cQube is installed, UDISE data source needs to be configured depending on the emission data fields  required by the state in the udise configuration file.
* During configuration users can activate/deactivate the indices and metrics status and their corresponding weights, but not the key columns \(ex : id,description,column,type,indice\_id should not be modified/edited\). Only fields like status and score are updated based on the active indices,metrics and their weights.
* In configuration stage fields will be activated/deactivated for that state, based on requirement
* We can also create our own indices and metrics during the udise configuration stage.
* There is an [exhaustive list](https://github.com/project-sunbird/cQube/blob/release-1.5/documents/UDISE_Metrics.xlsx) of calculated metrics available by default in cQube which is calculated from the UDISE raw input tables.
* The [exhaustive](https://github.com/project-sunbird/cQube/blob/release-1.5/documents/UDISE_Metrics.xlsx) calculated metrics can be used for creation of a normalised metric.
* We can create any number of normalised metrics from the [exhaustive list](https://docs.google.com/spreadsheets/d/1MDKVYexLGdMboxt3rrr6kRn61o9pXSP0LdHguco0bGQ) by choosing to add any of the calculated metrics. 
* The normalised metric can be defined under

1. Newly created index with new normalised metrics
2. Newly created index with few new normalised metrics and few existing normalised metrics with different name and metric\_id.
3. Existing index with new normalised metrics

* After successful validations the active metrics and indices are generated.
* The metrics/indices generated will be stored in JSON files, which is used for visualisation
* There are 3 types of directions and they are No, Forward, Backward, based on the metric the direction can be configured. Based on this normalisation takes place between 1 to 0 for backward metrics and between 0 to 1 for forward metrics. 
* If the schools are not having any particular metrics, the total weights\(denominator\) are considered for the available schools. Here is an [example](https://github.com/project-sunbird/cQube/blob/release-1.5/documents/UDISE_Metrics.xlsx) in the Metric level configuration sheet.

Check [udise\_config\_example](https://github.com/project-sunbird/cQube/blob/release-1.5/documents/UDISE_Metrics.xlsx) sheet for examples of above three possible configurations.

To select the Udise indices,metrics please fill the details in the udise\_config.csv file which is available at the link below.

https://github.com/project-sunbird/cQube\_Base/blob/release-1.5/development/postgres/udise\_config.csv

Note :- 

1. For providing weights the sum of score of all active indices should be 100
2. And also the score of all active metrics of each active indices should be 100
3. Change only status and score column from the [udise\_config.csv](https://github.com/project-sunbird/cQube/blob/release-1.5/development/postgres/udise_config.csv) file, depending on the use case.
4. While opening [udise\_config.csv](https://github.com/project-sunbird/cQube/blob/release-1.5/development/postgres/udise_config.csv) file in excel , please use ‘\|’ as a delimiter.
5. For newly created metrics/indices the field metric\_config is updated as value 'created' in udise\_config.csv file to differentiate the existing static metrics/ indices with newly created metrics/indices

The indices,metrics normalization and  calculations will happen as in the below example.

If a state selected community participation and medical index indices and their metrics as below

| id | description | column | type | indice\_id | status | score |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| 3000 | community participation | Community\_Participation | indice |  | 1 | 60 |
| 3001 | % SMC members provided training | cp\_smc\_members\_training\_provided | metric | 3000 | 1 | 40 |
| 3002 | Total meetings held by SMC | cp\_total\_meetings\_held\_smc | metric | 3000 | 1 | 40 |
| 3003 | SMDC in school | cp\_smdc\_school | metric | 3000 | 1 | 20 |
| 7000 | medical index | Medical\_Index | indice |  | 1 | 40 |
| 7001 | Medical Check-up Conducted | med\_checkup\_conducted | metric | 7000 | 1 | 60 |
| 7002 | De-worming Tablets | med\_dewoming\_tablets | metric | 7000 | 1 | 20 |
| 7003 | Iron Tablets | med\_iron\_tablets | metric | 7000 | 1 | 20 |

The total infrastructure score will be calculated using below formulas :

1. Before start doing calculation, we will normalise the data by grouping them in quartiles as in the following document ,[udise metric calculation logic](https://docs.google.com/presentation/d/1WBfh62IzEBorQHZZuNqLvOBJ39MVOQkA2Z7pcqnXGW8/edit?ts=5f55f9e9#slide=id.g95637e0387_0_5)
2. Community participation $$(cp)= (cpm1*40)/100+(cpm2*40)/100+(cpm3*20)/100$$ 
3. Medical index $$(med)= (medm1*60)/100+(medm2*20)/100+(medm3*20)/100$$ 
4. infra\_score= $$(cp*60)/100+(med*40)/100$$ 

#### Composite report configuration

cQube has the facility to combine the information of all reports and showing it in a single scatter plot and such report is called Composite report, Composite report is the combination of multiple reports which is used to co-relate the information between data sources in school, cluster, block, district level. Example : We can compare the attendance and semester performance of the school in a single scatter report.

1. This configuration should be performed at the installation / Up-gradation stage of cQube. 
2. The user may select the process groups which they wanted to include into the cQube. The metrics available in the selected processor groups will be used in the composite report.
3. If composite report is required to be enabled, make sure the \[ nifi\_comp: true \] processor group is enabled in [composite\_enable](https://github.com/project-sunbird/cQube/blob/release-1.2.1/ansible/installation_scripts/datasource_config.yml).

#### Diksha API Configuration

Diksha configuration for progress-exhaust & summary-rollup dataset:

We have integrated Diksha progress-exhaust & summary-rollup dataset through the API with cQube. During the installation/upgradation user needs to configure the Diksha production base\_url,token, encryption key to progress-exhaust & summary-rollup datasets. We need to configure the cQube/development/python/cQube-raw-data-fetch-parameters.txt file before upgradation or installation process with the production parameters.

Diksha Summary-rollup dataset:

The diksha summary-rollup dataset contains the course & textbook usage data and daily files are downloaded from the Diksha API configured in the above step directly to cQube s3 emission bucket. Once the summary-rollup CSV file is downloaded to the emission bucket the data processing takes place and the visualization reports will populate.

Diksha progress-exhaust dataset:

The diksha progress-exhaust dataset contains the course enrollment & completion data. This dataset is downloaded based on the batch\_id passed to the diksha API. The list of batch\_id's needs to be emitted in a CSV file through the emission API. All the data related to batch\_id's are downloaded to the emission bucket. Once the progress-exhaust zip file is downloaded it is unencrypted using the configured encryption password and stored into an emission bucket. The data processing takes place and the visualization reports will populate.

#### Diksha Columns Configurations

Diksha columns will be configured at the Installation / Upgradation stage. The summary-rollup dataset has two columns 1. content\_gradelevel 2. collection\_gradelevel. If the columns are available in the summary-rollup dataset exhaust, the "diksha\_columns" parameter needs to be true in the config.yml & upgradation\_config.yml else if the columns are not available the diksha\_columns parameter needs to be false.

If the columns are true,Diksha “Usage by user profile” report will be enabled from the dashboard else the report will be diabled if the configuration value is false at config.yml & upgradation\_config.yml.  


#### State/Udise table configuration

Static table configuration \(Udise/State tables\): During the installation Udise/State specific tables can be configured. 

The static table configuration is enabled for below tables

1. district\_master

2. block\_master

3. cluster\_master

4. school\_master

Based on the availability of state/udise tables, accordingly it needs to be configured in config.yml before installation.

Once after installation, if the configuration needs to be changed, the user can reinstall cQube. 

All the data will be lost if the user reinstall's cQube. the aggregated table data & s3 output files will be wiped off. 

Users need to remit the data files to generate the aggregate tables & s3 output files.  


During the upgrade the configuration cannot be performed. Only for release-1.8.1 the configuration has been enabled to change from state to udise and vice versa. For subsequent release this option would be disabled.

#### Semester Assessment Test \(SAT\) Configurations**:**

SAT configuration will happen from the emission file.

There are 2 files which need to be emitted to configure the Semester Assessment Test, they are semester\_exam\_mst, semester\_exam\_qst\_mst. 

The semester\_exam\_mst file needs to be updated with the following details: exam\_id, assessment\_year, standard, subject, exam\_code, total\_questions, total\_marks & semester information. 

The other file is semester\_exam\_qst\_mst and it needs to be updated with question\_id, exam\_id, question\_title, question\_marks, indicator\_id, indicator\_title, indicator. 

Please refer to the [emission fields document](https://github.com/project-sunbird/cQube/blob/release-1.11/documents/cQube_emission_table_fields.pdf) for the fields details semester\_exam\_mst, semester\_exam\_qst\_mst.

Users can emit these 2 files with incremental load whenever there is a new exam conducted. Once a user emitted these files, the user can emit the marks scored by each student for all the schools for newly conducted exam’s. 

Nifi will process the data based on the semester\_exam\_mst & semester\_exam\_qst\_mst and the data file to aggregation tables and S3 output files.  



# cQube Software Architecture


### cQube Architecture describes about three main layers of the application. 

1. Data Input
2. Data Cleansing, Data Transformation and Data Processing
3. Data visualization

![cQube software architecture](../.gitbook/assets/cQube%20software%20architecture.png)


### Data Input
Data emission will be performed periodically as per the specified time interval from different data sources with the help of an automated extraction process. Once the emission process extracts the data fields which are used by cQube, it is converted into csv formatted, pipe delimited files. The CSV data files will then be placed into the state data center by the automated process. 
[Emission automated processes](./emission-process-1.md) will invoke cQube data-ingestion APIs to emit the data. 

Once the raw data reaches to emission storage location, Nifi starts fetching the specified data sources related csv files at the scheduled time of each data source. 
For the future reference, Nifi keeps a copy of raw data into the data input storage location.

### Data Cleansing, Data Transformation and Data Processing
Once the raw data file copy is saved into the data input storage location, NIFI inserts the raw data into the staging tables (Referred as temporary tables) of PostgreSQL where the data is ready for the data cleaning process. Data cleaning includes the data validations as well as duplicate records handlings.

The cleaned and transformed data will be inserted to the transaction tables of the PostgreSQL.

NIFI invoke the PostgreSQL quires to perform the metrics calculations on the cleaned and transformed data. Resulted data will be saved into the Aggregation tables of PostgreSQL.

The below images describes the data flow steps happening in cQube


![cQube Dataflow](../.gitbook/assets/cQube%20dataflow.png)

### Data visualization
As earlier said cQube is a “decision making tool”. 

In explanation, cQube’s every report in Analytics is made up of dimensions and metrics. cQube reports provide good predictive insight and anticipates upcoming correlations at different components of the data and activities of the educational system. These reports help cQube admins to make appropriate decisions based on the insights. 

cQube visualizations can be customized according to the user’s views. cQube allows to create different cQube themes to create different look & feel designs into reports 







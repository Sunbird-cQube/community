# Technology Used

cQube adapter can use any system, programming language or ETL tool to develop the cQube adapter.&#x20;

For example:

* Python scripts can be used to extract data from the source / state database, transform it and finally export the CSV files inside the AWS S3 bucket or cloud storage which is being used. Apache Airflow can be used to scheduling the python scripts.
* Or, Apache NiFi can be used to create the end-to-end ETL Pipeline.
* The only requirement is that the adapter-generated CSV files should have the same column names and the data format as per schema\
  \
  Refer this [link](https://docs.google.com/document/d/1F9ho\_1y3sWDCzynPAzLScYT18VmuS4K-1dNOWs1z6rE/edit#heading=h.y16u3gcmp1l8) for detailed explanation

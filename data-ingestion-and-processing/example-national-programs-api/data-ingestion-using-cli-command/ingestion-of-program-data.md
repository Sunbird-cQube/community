# Ingestion of Program Data

### **Data Prep and Data Upload into server:**

For the ingestion of events data, we have to make sure, we have grammar and data files present in the below directory respective to each program inside the server.

`/ingest/<program_type>/programs`

The value for program type is read from the .env file and it can have two values VSK or NVSK.

&#x20;`yarn cli ingest-data`

This command will ingest the data to the dataset tables for all the programs. It also provides an option to ingest the data for the particular program

yarn cli ingest-data ---filter=\<program\_name>.

&#x20;The program name passed should be the same as the namespace specified in the config file.

* It will read all the programs present in the config.json file.
* It will check for the data files inside the programs folder and process the data.
* Then the process dataset update request is created.
* The transformer processes the request and updates the data to the dataset tables created. These datasets are used for visualization in the UI.

Below command can be used to upload the data for PGI program. Here in the filter we are passing pgi.

`yarn cli ingest-data --filter='pgi’`

<figure><img src="https://lh3.googleusercontent.com/46a__K6jQdpG68yOYEBPJRhK8Iy7WZQLmyyu2AeOWYeZ2zZ5Axx9spikgUE5Zg4XK5ettwdz_phAeoUqpMfuIh_u6ViK7ucriOTz76V97b94_YIKa9Hm8NV4zq3s6dtPIyxwOleTG-aFH0nYj0-RQrI" alt=""><figcaption></figcaption></figure>

&#x20;The above figure shows the ingestion of data for the program PGI. The data ingested can then be used by the visualization to derive statistical data.

\

# Data Processing using CLI command



&#x20;  **Ingestion of Dimensions:**

&#x20;         For the ingestion of dimension, we have to make sure, we have grammar and data files present in the below directory inside the server.

`/ingest/<program_type>/dimensions`

Run the below command from the /ingest/ folder to upload the dimensions in the database.

&#x20;   `yarn cli ingest`

* It will read the config.json file of a specific program type present inside the ingest folder.
* Then it will process all the dimension grammar present in the dimensions folder.
* The dimension grammars are stored in the “spec.dimensionGrammar” table and the dimensions tables are created in the dimensions schema.
* It will also look for data files respective to each dimension grammar file name and ingest all the dimension data to the respective tables.
* After the dimensions are ingested the programs array present in config.json is read and the event grammars are processed from the corresponding \<program-name> folder. The event grammars are stored in the spec.”EventGrammars” table.
* The dataset grammars are also stored in the spec.”datasetGrammars” table and the dataset tables are created based on the combination of timeDimension, dimension and metric present in the event grammars.
* In addition to the above combination of datasets created the user can also specify the combination of datasets that can be created in the whitelist array.

&#x20;    The below screenshot shows the final output of the yarn cli ingest command when all the dimension,event and dataset grammars are processed. The dimension data is also ingested in this process.

<figure><img src="https://lh3.googleusercontent.com/s0otTPD7cD9TYoghGwoUf2BsRopUpsb7hTVUuzfNa3xm_e1i26tdv99zb1TqP15dkPDXahRVs4RFz1pD0oGIGffqBCV3z6FkOWDU_xvmTuADFf59_YEYJYif31a5DJyxg9gYq_frCHPyGorjNbhSRAA" alt=""><figcaption></figcaption></figure>

**Note:** When you ingest dimensions everything gets deleted and re ingested. So to update the dimensions data, you should reupload the full dimensions data file and run the command (yarn cli ingest) to ingest dimensions

&#x20;       **Ingestion of Program Data**

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

<figure><img src="https://lh3.googleusercontent.com/ecHW9kEiJgPuOkCh9QwZQXphF6Qld7XfI3cpTUqCb-WKl0XJCV70oLtIpvIp7t2bfqEFMHI_Tf0imt-QKP5hkLu4A1T51LEKiPIX-DLhEiwg5sSfWf9a_bQ-75cZKRfpn0AxAetATZmnzxEXzcBHkn0" alt=""><figcaption></figcaption></figure>

The above figure shows the ingestion of data for the program PGI. The data ingested can then be used by the visualization to derive statistical data.

&#x20;      **Delete the data in the database**

`yarn cli nuke-db`: This command will delete all the data present in the database.




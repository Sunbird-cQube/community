# Ingestion of Dimensions

### Data Prep and Data Upload into server:

For the ingestion of dimension, we have to make sure, we have grammar and data files present in the below directory inside the server.

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

<figure><img src="https://lh4.googleusercontent.com/T5NSLwkYyPSHcXCf99GAWhQ8lEluccF6P5EIkqp2tU8loIvK_f5vnU6uw0dYsODNUSUGfesG6kGaHs69bpkWRp7KX7UBibEEMgGhtGwyyzI1qCII86XSUrtXB3NZ3j8ZdGJiU2hfWYN4AgOe8qHqdIg" alt=""><figcaption></figcaption></figure>

&#x20;  &#x20;

Note: When you ingest dimensions everything gets deleted and re ingested. So to update the dimensions data, you should reupload the full dimensions data file and run the command (yarn cli ingest) to ingest dimensions

\

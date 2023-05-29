---
description: Explains the process to add a new program into cQube Ed
---

# Adding a New Program

**Introduction:** This guide will help you add a new program in cQube by following the steps outlined below. Ensure that you have the latest version of cQube installed to access all the latest features and functionalities.

1. **Install or Update cQube:** Before you start adding a new program, make sure you have the most recent version of cQube installed. If you need assistance with the installation or upgrading process, refer to the following guides:

* [Installation Guide](https://cqube.sunbird.org/installation-and-upgradation/step-wise-installation-process): Provides step-by-step instructions for installing cQube.
* [Upgradation Guide](https://cqube.sunbird.org/installation-and-upgradation/step-wise-upgradation-process): Offers detailed steps for upgrading your cQube installation to the latest version.

2. **Create Event and Dimension Schema:** Design the event and dimension schema for your program. This schema defines the structure and relationships between different data elements, such as event attributes and dimensions.

* Event Schema: The event schema defines the structure of the events to be ingested into the system. It includes information such as the event name, its attributes (e.g., event timestamp, user ID, etc.), and data types.
* Dimension Schema: The dimension schema defines the dimensions, or attributes, that will be used to group and filter events. It includes information such as the dimension name, its attributes (e.g., dimension value, category, etc.), and data types.

3. **Create a Config.json:** Config.json provides directives to the processing engine on how to process the grammar and data files, where they are stored, etc.

* Place the Config.json in the /ingest/<state_code> folder.
*   Define the following settings in the Config.json file:

    * globals: Global settings for the cQube processing engine.
    * dimensions: Includes the file format, location, and namespace for dimensions.
    * programs: Program-specific settings like namespace, description, input location, output location, and dimensions to be considered.

    <img src="../.gitbook/assets/image5.png" alt="" data-size="original">

4. **Upload the Event and Dimension Grammar Files:** Convert the Event and Dimension Grammar to JSON format as given in the below example
Example: if there is a event with two columns
    school_id and school_name 

		Below would be the JSON object

		{
    			"program": "school-attendance",
    			"input": {
        			"type": "object",
        			"properties": {
           				 "school_id": {
              			 		 "type": "string",
              			 		 "shouldNotNull": true
            					},
           				 "school_name": {
                					"type": "string",
               					 "shouldNotNull": true
            				}
}

* Dimension Grammar: Use the /spec/dimension API to upload the dimension grammar

* Place the dimension grammar file as \<xyz>-dimension.grammar.csv in the /processing-ms/impl/c-qube/ingest/<state_code>/dimensions/ folder, or as specified in the Config.json settings

![](<../.gitbook/assets/image1.png>)

Contents of the district-dimension.grammar.csv

![](<../.gitbook/assets/image2.png>)

* Event Grammar can be ingested in 2 ways: 
   i. Though API Method
Event spec API: spec/event
   
   ii.Through YARN CLI
YARN CLI INGEST

   This command is used to ingest Event and Dimension Spec and Dimension Data based on the configuration we have
   
* Create a new program folder in the /processing-ms/impl/c-qube/ingest/<state_code>/   programs/ directory. 

* Place the event grammar file as <xyz>-event.grammar.csv in processing-ms/impl/c-qube/ingest/<state_code>/programs/<new-program> folder as seen below (example for diksha program)
This would be based on default config.json or else it should be as per config.json


![](<../.gitbook/assets/image4.png>)
   
Contents of the district-event.grammar.csv

![](<../.gitbook/assets/image3.png>)

5. **Data Ingestion:** Ingest data into the cQube platform using one of the following methods:

* [Uploading through CSV](https://cqube.sunbird.org/data-ingestion-and-processing/step-wise-ingestion-process#by-converting-data-into-a-csv-and-then-pushing-it-through-the-api): Upload data by providing a CSV file containing the necessary information. For detailed instructions, refer to the Uploading through CSV Guide.
* [Connecting to Database](https://cqube.sunbird.org/data-ingestion-and-processing/step-wise-ingestion-process#by-directly-connecting-the-database-and-then-pushing-the-data-through-api): Connect directly to a database to ingest data. For more information on how to establish this connection, consult the Connecting to Database Guide.

6. **Add Event Data Regularly:** To keep your program up-to-date, continuously add new event data to the platform. Determine an appropriate frequency for updating the data, such as daily, weekly, or monthly. Ensure that the new data is compatible with the existing event

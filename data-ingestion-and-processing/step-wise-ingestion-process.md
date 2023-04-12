---
description: >-
  Lists down the steps to ingest data (events, dimensions & datasets) into cQube
  V 5.0 for state as well as national programs
---

# Step-wise Ingestion Process

## State Programs:

This focusses on ingestion of programs like student attendance, teacher attendance & review meetings.

Data ingestion can be done using APIs. Please use postman as a tool to run these APIs. If you have already set up postman on your system, you can directly read the document from [here](step-wise-ingestion-process.md#step-wise-ingestion-process).

### **Setting up Postman** <a href="#setting-up-postman" id="setting-up-postman"></a>

* [Download](https://www.postman.com/downloads/) the postman application and import the collection.
* Select the import option in postman to import the collection. Please refer to the screenshot.

<figure><img src="../.gitbook/assets/image (6) (1) (2).png" alt=""><figcaption></figcaption></figure>

## Step-wise Ingestion Process:

The data can be ingested into cQube in two ways:

1. [By converting data into a CSV and then pushing it through the API](step-wise-ingestion-process.md#by-converting-data-into-a-csv-and-then-pushing-it-through-the-api)
2. [By directly connecting the database and then pushing the data through API ](step-wise-ingestion-process.md#by-directly-connecting-the-database-and-then-pushing-the-data-through-api)

### **By converting data into a CSV and then pushing it through the API**

Events, Dimensions & Datasets can be ingested into cQube via the ingestion APIs.

**Step 1:** Select the 'csv\_import' folder in the postman collection.

**Step 2:** Open the specified request & add details.

API Endpoint: \<domain\_name>/ingestion/new\_programs

HTTP Method: POST

<figure><img src="../.gitbook/assets/image (7) (2).png" alt=""><figcaption></figcaption></figure>

This API will import the event / dimension / dataset CSV and upload it into the combined\_input folder in cloud / local SDC if there are no errors. Then, the adapter in cQube will use the same files to breakdown the combined input into multiple input files. Later, those files will be used by the NiFi processor to process and create datasets into the database.

**Step 3**: Build the request body with reference to YAML file. The request body for the above API is attached here for yaml: [https://github.com/Sunbird-cQube/spec-ms/blob/march-release/spec.yaml](https://github.com/Sunbird-cQube/spec-ms/blob/march-release/spec.yaml)

Provide valid input details for the parameters shown below.

* **file** : Attach the CSV file for the importing&#x20;
* **ingestion\_type** : Specify the type of ingestion
* **ingestion\_name** : Name of the event / dimension / dataset (event / dimension / dataset name should be present in the database)

<figure><img src="../.gitbook/assets/image (19).png" alt=""><figcaption><p>Ingestion of Events</p></figcaption></figure>

<figure><img src="../.gitbook/assets/image (15) (1).png" alt=""><figcaption><p>Ingestion of Dimensions</p></figcaption></figure>

**Step 4**: Click on the send button for request and if the request is successful the user should see a response message. Please refer to the below screenshot.

<figure><img src="../.gitbook/assets/image (12) (1).png" alt=""><figcaption><p>Ingestion of Events</p></figcaption></figure>

<figure><img src="../.gitbook/assets/image (17).png" alt=""><figcaption><p>Ingestion of Dimensions</p></figcaption></figure>

After successful execution of the CSV import API, we get the response and we can see the file status indicating if the file is uploaded or not through GET file status API. If the file is successfully uploaded we will get the response as uploaded and if there is any error it will send us the response indicating there was an error in the file.

### By directly connecting the database & then pushing the data through API&#x20;

Events, Dimensions & Datasets can be ingested into cQube via the ingestion APIs.

**Step 1:** Open the specified request & add the details

API Endpoint:&#x20;

1. \<domain\_name>/ingestion/event
2. \<domain\_name>/ingestion/dimension
3. \<domain\_name>/ingestion/dataset

HTTP Method: POST

<figure><img src="../.gitbook/assets/image (3) (1).png" alt=""><figcaption><p>Ingestion of Events</p></figcaption></figure>

<figure><img src="../.gitbook/assets/image (14).png" alt=""><figcaption><p>Ingestion of Dimensions</p></figcaption></figure>

<figure><img src="../.gitbook/assets/image (5) (1) (2).png" alt=""><figcaption><p>Ingestion of Datasets</p></figcaption></figure>

This API will be used to write events into the CSV file and upload it in to the combined\_input folder in cloud / SDC if there are no errors. Then, the adapter will use the same files to break down the combined input into multiple input files. Later, those files will then be used by the NiFi processor to ingest the data into the database. The API can be used to add individual events into CSV.

**Step 2:** Build the request body with reference to YAML file. The request body for the above API is linked here: [https://github.com/Sunbird-cQube/spec-ms/blob/march-release/spec.yaml](https://github.com/Sunbird-cQube/spec-ms/blob/march-release/spec.yaml)

Provide the valid input details for the parameters as shown below. The request body should conform to the schema stored in the database for the particular event name.

<figure><img src="../.gitbook/assets/image (10).png" alt=""><figcaption><p>Ingestion of Events</p></figcaption></figure>

<figure><img src="../.gitbook/assets/image (16) (1).png" alt=""><figcaption><p>Ingestion of Dimensions</p></figcaption></figure>

<figure><img src="../.gitbook/assets/image (4) (3).png" alt=""><figcaption><p>Ingestion of Datasets</p></figcaption></figure>

**Step 3:** Click on the send button for the request and if the request is successful the user should see a response message. Please refer to the screenshot.

<figure><img src="../.gitbook/assets/image (18).png" alt=""><figcaption><p>Ingestion of Events</p></figcaption></figure>

<figure><img src="../.gitbook/assets/image (2) (4).png" alt=""><figcaption><p>Ingestion of Dimensions</p></figcaption></figure>

<figure><img src="../.gitbook/assets/image (4) (1).png" alt=""><figcaption><p>Ingestion of Datasets</p></figcaption></figure>

After successful execution of the event / dimension / dataset API, we get the response and the data sent in the request body will be written to the CSV file. Any errors will be written to a CSV file and valid data will be written to a separate CSV file.

## National Programs:

This focusses on ingestion of programs like UDISE, PGI, NISHTHA, DIKSHA, NAS, PM-POSHAN.

The already existing files with the states will be automatically ingested into cQube v5.0. In case any new files needs to be ingested for the programs mentioned above, the following process needs to be followed:

This API accepts the data in a zip file format and adds it to the emission folder in the respective cloud storage / SDC.

**Step 1:** Open the specified request and add the details.

API Endpoint: \<domain\_name>/ingestion/national\_programs

HTTP Method: POST

<figure><img src="../.gitbook/assets/image (1) (1) (3).png" alt=""><figcaption></figcaption></figure>

**Step 2:** Build the request body with reference to YAML file. The request body for the above API is attached here for yaml: [https://github.com/Sunbird-cQube/spec-ms/blob/march-release/spec.yaml](https://github.com/Sunbird-cQube/spec-ms/blob/march-release/spec.yaml). Provide the valid input details for the parameters as shown below.

<figure><img src="../.gitbook/assets/image (11) (1) (1).png" alt=""><figcaption></figcaption></figure>

**Step 3:** Click on the send button for the request and if the request is successful, the user should see a response message as “File uploaded successfully”. The files will be uploaded to the emission folder created in the respective cloud storage / SDC.

The zip file will be extracted and will be read by the adapters and then moved into the input folders.

<figure><img src="../.gitbook/assets/image (13) (1).png" alt=""><figcaption></figcaption></figure>


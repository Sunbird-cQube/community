---
description: >-
  This page focusses on ingestion of programs like student attendance, teacher
  attendance & review meetings.
---

# Step-wise Ingestion Process \[State Programs]

Data ingestion can be done using APIs. Please use postman as a tool to run these APIs. If you have already set up a postman on your system, you can directly read the document from here.

Note: There could be some common errors in the files which could lead to unsuccessful data ingestion into cQube. Look at these errors here and resolve them before ingesting data into cQube.

### Setting up Postman

* [Download](https://www.postman.com/downloads/) the postman application and import the collection.
* Select the import option in postman to import the collection. Please refer to the screenshot.

<figure><img src="https://lh4.googleusercontent.com/s22Ym2ILCgRSwAN-tqciXxrRCxXXwNsqdds2G2YYaAiORNzCEtlsAtAiRG2_6h0mEtjfH9Cwv8r__WoXYrjhnWspDLnNc8sCG-l46a5xwFxALmiQd6gqWsF8fOEjg-DhrdREQtKfaLNOXEshVSW4VdU" alt=""><figcaption></figcaption></figure>

\
\


### Adding a grammar  for a program to validate data during csv upload&#x20;

\
**Steps to add the schema for programs**

&#x20;**Step 1:** Create a postman request and add details

API Endpoint: \<domain\_name>/spec/event

HTTP Method: POST

<figure><img src="https://lh5.googleusercontent.com/XGLiwQ71zd7ckEAh8dWtiXO42es5MkBYHf0KOD4a_QfNUiMDCsDJ30UjVkoUIJJwwKgWT2z-tMWYKgu4OO6wwEInS9JoMEowTomcxTmt15_1d8Dqvbi_IKHOzqkF8WPrPzjG5aow8qS5vnM1jwaxuV0" alt=""><figcaption></figcaption></figure>

**Step 2:**  Build the request body with reference to YAML file. The request body for the above API is attached here for yaml:[ ](https://github.com/Sunbird-cQube/spec-ms/blob/march-release/spec.yaml)[https://github.com/Sunbird-cQube/spec-ms/blob/dev/spec.yaml](https://github.com/Sunbird-cQube/spec-ms/blob/dev/spec.yaml) Provide valid input details for the parameters shown below.

<figure><img src="https://lh3.googleusercontent.com/b_ANaJ7xtbtKI491nW35t1AC6rC8Fea248iEcBr5vVBY5B6_0xZjqaPAUYrBVmzlvmq5YEboMaXic_zxkWQLzyJDStDynveYqHNQ0W9h7WnyvMJ7iuhrP39FTIm5CllKK88so97ivG787MIbZJSq8LM" alt=""><figcaption></figcaption></figure>

**Step 3:** Click on the send button for request and if the request is successful the user should see a response message. Please refer to the below screenshot.

<figure><img src="https://lh6.googleusercontent.com/odV4rl1IlXx7syho5HI4Rkx7OnlCaojSGySUF_2Wok3qIVhNXVcN8xb2Gr0m0RgCU1LCAuXITsLiGzjOCBAx729ahjE28jwAv7pgSQi9cecgmKKVH0Cj1T5SkcDk55Yk5t3gwVNIc0j062t_5PXg-1c" alt=""><figcaption></figcaption></figure>

Once the API response is successful then the schema is stored in the spec.”EventGrammar” table.

### &#x20;Step-wise Ingestion Process:

The data can be ingested into cQube in three ways:

&#x20;**Steps to upload the csv data file for new programs using ingestion API**

Events, Dimensions  can be uploaded  into respective cloud storage  via the ingestion APIs.



**Step 1:** Select the 'csv\_import' folder in the postman collection.

**Step 2:** Open the specified request & add details.

API Endpoint: \<domain\_name>/ingestion/new\_programs

HTTP Method: POST

<figure><img src="https://lh4.googleusercontent.com/n2vcuxvh_Ml3UgLz9UDZ61Hk6z_bGhn7fXD7JZVSoE-dKIyL5VUthVta8utWUS3uxejLYY3rbQCgjxE7UBIofZ9nXM8Ww5QESkjITFzVXJLSVqoM3OIubwUfYmJ5rt-wVtwnNb0G-zJ503AZDucruyg" alt=""><figcaption></figcaption></figure>

This API will import the dimension csv and upload it in to the combined\_input folder in cloud if there are no errors.&#x20;

**Step 3:** Build the request body with reference to YAML file. The request body for the above API is attached here for yaml:[ ](https://github.com/Sunbird-cQube/spec-ms/blob/march-release/spec.yaml)[https://github.com/Sunbird-cQube/spec-ms/blob/dev/spec.yaml](https://github.com/Sunbird-cQube/spec-ms/blob/dev/spec.yaml) Provide valid input details for the parameters shown below.

* file : Attach the CSV file for the importing
* ingestion\_type : Specify the type of ingestion
* ingestion\_name : Name of the event / dimension / dataset (event / dimension / dataset name should be present in the database)

<figure><img src="https://lh4.googleusercontent.com/570uPELR7f0Qd_VW6O_2JQj2cXLoDeHWtS1OG059_gql2LGDxWrNz-44S3Af0rAzN-P-4r5kCbNk6_krQ62MUPeHxZoG0MnVqUvFcVccT6IV1nwpa1gx1_I4Rp4EbRy9ElnjYUKmQA6IC0Mx6IIxOek" alt=""><figcaption></figcaption></figure>

**Step 4:** Click on the send button for request and if the request is successful the user should see a response message. Please refer to the below screenshot.

<figure><img src="https://lh5.googleusercontent.com/Uvjhn54DlRRbEZaLxDmHMrI_nu4bYrQp8NznOR15qB_wDIPkVk7v9akZFFzEJmOJyFmhoPpPXPtNLLUemEajWB_hckNZfhd2vQcdK-1XvAvV5pNygzH1AfGXwqP55vSb2qB5VOJc_ajZg5tiILHEPqk" alt=""><figcaption></figcaption></figure>

After successful execution of the csv import api we get the response and we can see the file status indicating if the file is uploaded or not using GET file status API. If the file is successfully uploaded we will get the response as uploaded and if there are any errors it will send us the response indicating there was an error in the file.

### GET file status API

**Step 1:**  Open the specified request & add the details

API Endpoint: \<domain\_name>/ingestion/file-status

HTTP Method: GET&#x20;

<figure><img src="https://lh6.googleusercontent.com/ktHsTn48mu8K7FebhikEaO7YTxJ5IbS4qkrXDaSQOebu3s_reHo-FUMpTA0Dd_qwNLWtjotv0K7z5fxg2rVL5KQmVPtz4sMEkSspgYkPqJRj9B3Hnen6lx_IX_XrSG5LWqdSiK6vvoHADZ6nc-YA9BE" alt=""><figcaption></figcaption></figure>

**Step 2:** Send the query parameters with reference to the YAML file. The query parameters for the above api is attached in  Link for yaml:  [ <img src="https://lh6.googleusercontent.com/oFxpwMh3EzL4iSZDpXtajMM9wollZPHGHYMtX7FCwAUl9H--KpBlV6HR5KjW3xAr_11EGTcEj54iCfm5IFCpDfKTXvHh_ZnD01xtDmkwS58yZjFfTGoAWp19MVQV2JyoCTsPi_VfPJMV2gLDEEfsM1k" alt="" data-size="line">spec-ms/spec.yaml at dev · Sunbird-cQube/spec-ms](https://github.com/Sunbird-cQube/spec-ms/blob/dev/spec.yaml)

Provide the valid input details for the parameters shown below.

&#x20;

<figure><img src="https://lh6.googleusercontent.com/-P0OTB--dXEdxxSV_Jsav0prju6mF0ShvIXIj7SbwokO_4pI8F6Z_s_t6IZxnmc0lvUQK5H950GGyX6QoNVgKcrMOyIXSkhPxRny6VXlHi-hD58AC8eFBv3inxxsYF0PLWm-Ln7Bw9OOG0Ri2lMW8sE" alt=""><figcaption></figcaption></figure>

**Step 3:** Click on the send button for the request and if the request is successful the user should see a response message which contains the status of the file.

<figure><img src="https://lh5.googleusercontent.com/0TGmdUvoYepCzV6_RAD8SlD8z23Oxgc4q082kuIkr4_aeTbVCbfPQku5hSGiIVoqJzRrqNxoCx4TEJZJVQjUgCe10kiWIavRWwlfOArbp7wm92MLQHc3yxlLqajpGYo0w7InvNzSW2qPwDu-MISWFzk" alt=""><figcaption></figcaption></figure>

If the csv files are too large in size, the upload process of those files will take more time which will make users wait for longer duration to receive the response from the API. As a result, the upload process will be running asynchronously and we have developed this api to know the status of the file at any particular time.

### Schedule API

This API helps to schedule the processor group at any particular time.

**Step 1:** Open the specified request & add the details

API Endpoint: \<domain\_name>/spec/schedule

HTTP Method: POST

<figure><img src="https://lh3.googleusercontent.com/sKhMROOl8drsDYhiyrltL7tkzwYl9OUo-zuoSNvfyv7CryEFMmhd3GkRxc2UgSkDbR1Na702kGClXsQe6za5TV8O71DlRwC_A_qo-Cmz5szCNFoNyAfiBB2U1ob0m25mfjbIPi5B3AnQQiq3HvhOmLw" alt=""><figcaption></figcaption></figure>

**Step 2:** Build the request body with reference to YAML file. The request body for the above api is attached in Link for yaml:[ <img src="https://lh3.googleusercontent.com/Qhq8hUyBQygL1WHJ7IuBn4NE9kiUB6lhrWnqE9cHlKd2j43KCiFj5X6e9GB5WMIdeH8DXzI1VTT90IDiPxVN-JPChTsrarcCyoZksYq0dVGPVpCcgyFBqxO6WqHVIwxQDJDQ2Cv_v40-zuOFW0UROds" alt="" data-size="line">spec-ms/spec.yaml at dev · Sunbird-cQube/spec-ms](https://github.com/Sunbird-cQube/spec-ms/blob/dev/spec.yaml)   . Provide the valid input details for the Parameters shown below.&#x20;

<figure><img src="https://lh5.googleusercontent.com/RsK_3kZYG58_BaJCW52EybAQ8smkE8yVzES38tuc58n7nMD5BNrm875GuPJqOfAKmPN9_E9U-Uu0Gcp0GEcSMYhzIfPI06_OacoufFzjpXtZ-40kLhhEScCYr10hDx9otiNSP0ZnnD49j_f5u7f-S4M" alt=""><figcaption></figcaption></figure>

**Step 3:** Click on the send button for the request and if the request is successful the user should see a response message. The schedule time will be updated in the processor group.

<figure><img src="https://lh3.googleusercontent.com/6BtfWo4W9zVHarLfzXSg1BjsLvTGGx4rt2xJQtmdeK-4TNybBSaytOX1SfVO1fQa6u9dNii1IJlEDNBfENV37EoqdfVGLjk2meZzsIADD1S3b-1iglktpZpu42sSfeLbTW7E29LHQBzJfNcXvKiGX0Y" alt=""><figcaption></figcaption></figure>

The schedule api helps to run the processor group in Nifi at a scheduled time. The schedule time can be updated by changing the cron expression for scheduled\_at property in the request body.&#x20;

\


## **Error Monitoring**

The error file will store all the error records during the ingestion process and will be uploaded to the appropriate cloud storage. The user can login to the respective cloud storage and download the file to take a look at the error records present in the csv. The below mentioned steps will specify on how to access the error file.

For VSK programs the error files are stored in the emission\_error folder and inside the folder there will be folders with \<date> as folder name. If there are any errors in the file which was uploaded in the present day then there will be a folder created with \<current\_date> which stores all the error files containing error data.

For new programs the when data ingestion is done using ingestion API’s the error handling is done as follows:

1. The cloud storage bucket/container will be named as cQube-edu.
2. Inside the bucket there will be multiple folders for different processing stages and the ingestion error files  will be stored in ingestion\_error folder. This folder will in turn contain folders for each program(for new programs), the name of the folder will be same as the \<program\_name>.
3. The \<program\_name> folder will internally have a folder which will have current date as the name.
4. The user can access the current date folder if its present and can see the error files present in it and download the error files to view the errors present in the csv.

\


<figure><img src="https://lh3.googleusercontent.com/EyoceJIJicQnTVZayH_ZS1MnlyPBJ6E3OTetcP2A6d4vQUVZ75y0-oMe3B4sRB3T-to6CX5NfifjRw1a98Ba15rIdqs_806_zw0671EfzK8zmmut1vou_c0HNJdI9GHWzWiPJd6hKvPWawn6X_Sp4aw" alt=""><figcaption></figcaption></figure>

\


<figure><img src="https://lh6.googleusercontent.com/tW7hqyvu0C4-tsUBDaKoESySBmfH28LRKRn6EuVF8I2duVHnIE0eWtBO1HlB4DEabriU03XS75hWd6aN8Z5bAm9A0ZzgFetUa4X_owk_KhHy7JLaF5ygiyMLb_zu-QYJfrSbImzT_0up9-aaf3S9PJA" alt=""><figcaption></figcaption></figure>

\


<figure><img src="https://lh6.googleusercontent.com/LxOkj0znuGRDq-Yb855aQyjFJWExU7OBJYuaz1FknJgsNe8npFt8e9EKBUUtYr8ULA0aOyvXv9SlKQwY0qnzs3IVdtW7n-cKzV0ckr-3eVhUyiGOD6nTSGj-eC6PjJDVPP3ixvWZlFTeffyM_rMqYjc" alt=""><figcaption></figcaption></figure>

\


<figure><img src="https://lh3.googleusercontent.com/G0Pl4jnTCCgE3WLpRGilwgqCurLv4Or2QT11lxX4KsvwqP5m7awC7oR4mUfC8v-KyJkZhp9XlaFfVxSK_CNMGiUh5my_7vdD-4Vd6s9k_NltDo28XglHdQV57yvaN5X2jkXkdaTPEgMLB1AL0Yh7wds" alt=""><figcaption></figcaption></figure>

\


<figure><img src="https://lh5.googleusercontent.com/LJk0w6M2YL1Tu4-8GwfMP8KEzvqmn6jbzyLPmhPt0hsSkjq2FVEYnDLl4jGpCwRXGGK6j90hdSABFr-pjiyMLyfZ-_teEBa69wLKQDxpreaqrCHU2wUpTdbcuxzFYckBFRb-sssOL2FTsokDJSSFKHg" alt=""><figcaption></figcaption></figure>

### Data Ingestion using CLI command

#### **Ingestion of Dimensions**

* Data Prep and Data Upload into server:

For the ingestion of dimension, we have to make sure, we have grammar and data files present in the below directory inside the server.

/ingest/\<state\_code>/dimensions

Run the below command from the /ingest/ folder to upload the dimensions in the database.

&#x20;  `yarn cli ingest`

* It will read the config.json file of a specific state present inside the ingest folder.
* Then it will process all the dimension grammar present in the dimensions folder.
* The dimension grammars are stored in the “spec.dimensionGrammar” table and the dimensions tables are created in the dimensions schema.
* It will also look for data files respective to each dimension grammar file name and ingest all the dimension data to the respective tables.
* After the dimensions are ingested the programs array present in config.json is read and the event grammars are processed from the corresponding \<program-name> folder. The event grammars are stored in the spec.”EventGrammars” table.
* The dataset grammars are also stored in the spec.”datasetGrammars” table and the dataset tables are created based on the combination of timeDimension, dimension and metric present in the event grammars.
* In addition to the above combination of datasets created the user can also specify the combination of datasets that can be created in the whitelist array.

&#x20;    The below screenshot shows the final output of the yarn cli ingest command when all the dimension,event and dataset grammars are processed. The dimension data is also ingested in this process.

<figure><img src="https://lh5.googleusercontent.com/JVo4mNmNHbQTHb7e63vY8bOztpOAPAYQjq74yhWyy6vCwBek8w49N2gMHUTWDY0LpJORd2QZ_ZCOONOxOFHuMWmQIw4BfGoaeIAV8SKQF5EEEG5sRVNNVyLss1k38tOlomaPulIfovF51XmBr1Tsieg" alt=""><figcaption></figcaption></figure>

&#x20;  &#x20;

Note: When you ingest dimensions everything gets deleted and re ingested. So to update the dimensions data, you should reupload the full dimensions data file and run the command (yarn cli ingest) to ingest dimensions.

Ingestion of Programs data

* Data Prep and Data Upload into server:

For the ingestion of events data, we have to make sure, we have grammar and data files present in the below directory respective to each program inside the server.

/ingest/\<state\_code>/programs

&#x20;yarn cli ingest-data

This command will ingest the data to the dataset tables for all the programs. It also provides an option to ingest the data for the particular program

yarn cli ingest-data ---filter=\<program\_name>.

&#x20;The program name passed should be the same as the namespace specified in the config file.

* It will read all the programs present in the config.json file.
* It will check for the data files inside the programs folder and process the data.
* Then the process dataset update request is created.
* The transformer processes the request and updates the data to the dataset tables created. These datasets are used for visualization in the UI.

Below command can be used to upload the data for PGI program. Here in the filter we are passing pgi.

`yarn cli ingest-data --filter='pgi’`

<figure><img src="https://lh6.googleusercontent.com/jeTfHAoeyoqD3wqB0ms4HHeXUJ98zt4jPFpPTLpvfQNQMnGX9Ekrs3vx2P3uDDve9C4DgJon8sdhxfNztYu8iLnYTV0sqbofs5Ckr98JbQobnpID0KmoGKoIKhTieTDNp5YHMJ0Ls3GiqMAs-ftlcBU" alt=""><figcaption></figcaption></figure>

The above figure shows the ingestion of data for the program PGI. The data ingested can then be used by the visualization to derive statistical data.

Delete the data in the database

`yarn cli nuke-db`: This command will delete all the data present in the database.

\

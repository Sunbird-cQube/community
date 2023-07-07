# Steps to upload the csv data file for new programs using ingestion API

Events, Dimensions  can be uploaded  into respective cloud storage  via the ingestion APIs.

The jwt token has to be passed in the API headers.



Step 1: create a postman request & add details.



**API Endpoint:** \<domain\_name>./api/ingestion/new\_programs

HTTP Method: POST

<figure><img src="https://lh6.googleusercontent.com/OHL57vDrOaOhCviKFIXlpsJqkoEGQPdlrGbFpM2PqjQJm6ha1M_qu9mNqKna6cqk-Vz-A5i9qomtPwPA9kbQNKOwdaLPEEiChL1GCLUpvDYzogHPb7TZOec4tNJDsS6paA-ftYJ0IokdrbEajIFvxQ0" alt=""><figcaption></figcaption></figure>

This API will import the dimension csv and upload it in to the combined\_input folder in cloud if there are no errors.&#x20;

Step 2: Build the request body with reference to YAML file. The request body for the above API is attached here for yaml:[ ](https://github.com/Sunbird-cQube/spec-ms/blob/march-release/spec.yaml)[https://github.com/Sunbird-cQube/spec-ms/blob/dev/spec.yaml](https://github.com/Sunbird-cQube/spec-ms/blob/dev/spec.yaml) Provide valid input details for the parameters shown below.

* file : Attach the CSV file for the importing
* ingestion\_type : Specify the type of ingestion
* ingestion\_name : Name of the event / dimension / dataset (event / dimension)

<figure><img src="https://lh4.googleusercontent.com/PcGL1t0rRHf5LaniuAbraKLxf2DI-3RC0DUgYvk2cdcfN5llUEJattQzq0xZcF-5xi9GIaz0WzhiBnXB0TV-9DUCtBqKHczGdYx9TezZ85MYB0oP-2mBozUZT-EWLvnO8tcmG6cvlcHqbJCa8VYKvxg" alt=""><figcaption></figcaption></figure>



Step 3: Click on the send button for request and if the request is successful the user should see a response message. Please refer to the below screenshot.

<figure><img src="https://lh6.googleusercontent.com/najKRUWW6OvJuevXHdj6rZJ2aQZhbeZesXEWNwfws1xXuOBI-R-VVzEDPplQYtqppHaVWOCB65Hl57STd5_83Mbnj0xSoZSa90eIO9VSv7OJEsfCMJl2MQJRtXCHR9L6xiCNgzfiS0UUmPp11JI7MzQ" alt=""><figcaption></figcaption></figure>

After successful execution of the csv import api we get the response and we can see the file status indicating if the file is uploaded or not using GET file status API. If the file is successfully uploaded we will get the response as uploaded and if there are any errors it will send us the response indicating there was an error in the file.

\

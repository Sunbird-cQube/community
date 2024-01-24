# Upload the .csv data file for state specific programs using ingestion API

Events, Dimensions  can be uploaded  into respective cloud storage  via the ingestion APIs. The event upload is done for only state programs using this API.

The jwt token has to be passed in the API headers.

**Step 1**: create a postman request and add details.

API Endpoint: \<domain\_name>/api/ingestion/new\_programs

HTTP Method: POST

\


<figure><img src="https://lh5.googleusercontent.com/MaPHj49DDiYoBuI0G5glMvm4ucxnr8jY9xMAKEHf4pt1V_r0D-F5fz659CbHMTkXrxSKzbEA-EeDKa1pEfaBKGVvYuF4NdxP_LYp6-PW-9aRkqvEvFebTQDwfXvitxflOv2Ne_wyTRzWImH0cKEZQtg" alt=""><figcaption></figcaption></figure>

This API will import the dimension csv and upload it into the process\_input folder in the cloud if there are no errors.&#x20;

**Step 2:** Build the request body with reference to YAML file. The request body for the above API is attached here for yaml:[ ](https://github.com/Sunbird-cQube/spec-ms/blob/march-release/spec.yaml)[https://github.com/Sunbird-cQube/spec-ms/blob/dev/spec.yaml](https://github.com/Sunbird-cQube/spec-ms/blob/dev/spec.yaml) Provide valid input details for the parameters shown below.

* file : Attach the CSV file for the importing
* ingestion\_type : Specify the type of ingestion (value should be event when uploading the event data file. If it is a dimension data file it should be dimension)
* ingestion\_name : Name of the event or dimension&#x20;
* program\_name: Name of the state program (This key is required only for ingestion\_type = ‘event’)

Note: The value for the key program\_name should be the same name as the folder name present inside ingest->VSK or NVSK->programs folder in processing-ms.

Example: [https://github.com/Sunbird-cQube/processing-ms/blob/dev/impl/c-qube/ingest/VSK/config.json](https://github.com/Sunbird-cQube/processing-ms/blob/dev/impl/c-qube/ingest/VSK/config.json)

The above link has a list of programs array.

&#x20;**Example:** For a school attendance program the folder name is school-attendance so the same name should be given while passing the value for program\_name.

&#x20;"files": "./ingest/VSK/programs/school-attendance" => The folder name can be identified as school-attendance.

<figure><img src="https://lh5.googleusercontent.com/zMTxWtC_vlt6V5ZmUV92cWSPQ7LjlGVGPtcvGK5JraDALW4ZzE2kjLTC6oidv3nihdalb7nGDzCkAwmGLqdpSaltNwJRgZM0f0uDJOeoX98EnU0ixKckqlYnhw3ZM_WkjdQBz7ESXmZsdaoGUEeafys" alt=""><figcaption></figcaption></figure>

### Step 3:&#x20;

Click on the send button for request and if the request is successful the user should see a response message. Please refer to the below screenshot.

<figure><img src="https://lh5.googleusercontent.com/IU5Zb0WByjHEYpg2Vq2-dttEcHNafU091uAX5CR_1yxALTS1ZVmy0tmGSI1t8FChA7a-ctq2zO6gsN8LPWOcN_BUNcGKNqc4q02SE3ks2a88DuexpWu_c9e9Z0RGFgGsDr1SBpwvHZdVTzHqEHJwFXQ" alt=""><figcaption></figcaption></figure>

After successful execution of the csv import api we get the response and we can see the file status indicating if the file is uploaded or not using GET file status API. If the file is successfully uploaded we will get the response as uploaded and if there are any errors it will send us the response indicating there was an error in the file.

\

---
description: >-
  This focuses on ingestion of programs like UDISE, PGI, NISHTHA, DIKSHA, NAS,
  PM-POSHAN. The jwt token has to be passed in the API headers.
---

# National Programs API to upload starter Pack Data files

**Note:** There could be some common errors in the files which could lead to unsuccessful data ingestion into cQube. Look at these errors here and resolve them before ingesting data into cQube.

The already existing files will need to be ingested into cQube via the following process:

This API accepts the data in a zip file format and adds it to the emission folder in the respective cloud storage / SDC.

\


&#x20;**National Programs API:**

### Step 1: &#x20;

Open the specified request & add the details

**API Endpoint:** \<domain\_name>/ingestion/file-status

**HTTP Method:** GET&#x20;

<figure><img src="https://lh4.googleusercontent.com/FxBb2naDMzrSwyVBQqO-icyzVjsZXAOUwAJS4_iZQUAEOG8d4eaASjtmHjXsDydBgFc6MzzXzWZjIu6kr20Sb7rakoanaIN609omZPk28cIgDFl43xQxaWpWZ7JbcGD0VCvuF2Qb9e22DQucpueddRY" alt=""><figcaption></figcaption></figure>

### Step 2:&#x20;

Send the query parameters with reference to the YAML file. The query parameters for the above api is attached in  Link for yaml:  [ ](https://github.com/Sunbird-cQube/spec-ms/blob/dev/spec.yaml)[<img src="https://lh6.googleusercontent.com/vz1PVdRSVzygs-DlegHLT1KDUWzJ5y6WDQD3V5CE-Szl9udxKtyL3yuPSqPy3tpkwN2UbYDE43uFQV-qzU1yjCeV6ESNlJD5xkmTSZds-4yEy3NWIt10Fs-D3UfRV6IZg-mNQD-HBg78jlreb_eY_q8" alt="" data-size="line">](https://github.com/Sunbird-cQube/spec-ms/blob/dev/spec.yaml)[spec-ms/spec.yaml at dev · Sunbird-cQube/spec-ms](https://github.com/Sunbird-cQube/spec-ms/blob/dev/spec.yaml)

Provide the valid input details for the parameters shown below.

<figure><img src="https://lh5.googleusercontent.com/dYFL3X-Vkq1W9HHJv2XInIso2b5nofh7yaHVDzWjJkHUKbwgIe8EIBtpJP1uzkaDHe0mT9ceX2m3yiCWn7r6CWbdA4lIBMwUpXM2AVcq26GOJWdExaXPsHb5UsBSeEvzHgvjPFKp4NEfcbzNebzSBxA" alt=""><figcaption></figcaption></figure>

### Step 3:&#x20;

Click on the send button for the request and if the request is successful the user should see a response message which contains the status of the file.

If the csv files are too large in size, the upload process of those files will take more time which will make users wait for longer duration to receive the response from the API. As a result, the upload process will be running asynchronously and we have developed this api to know the status of the file at any particular time.

<figure><img src="https://lh4.googleusercontent.com/ZYvquzK3X_OlYqpX6LucWKlOywN07ulIUh7qvxGUAzi2H9KAZiPXkgCv7PIgEMCHr_tiPLMKY1UmBRse3ug75SCkKKlJJ3IgSXDxc6XmXPYvG1SMcyoB1Uvu9kAAvf0QNaqwgUJxUlzwcQ4qLyG7lGU" alt=""><figcaption></figcaption></figure>

#### GET file status API

**Step 1:**  Open the specified request & add the details

API Endpoint: \<domain\_name>/ingestion/file-status

HTTP Method: GET&#x20;

<figure><img src="https://lh6.googleusercontent.com/2mo-a6hRB01iXeJERI76ZtsT1Vw5SK1gT9BJ8P4oFp_a0ahdOJY0N6X-xyBizr6SUxsfF3XlkHYoGhy17GHhLzinHp-_oTCqTg0YQAgevh6noSBK15zhYyWhNgJCdjPDZ-ZOx6hFGMcoldE7drudMv4" alt=""><figcaption></figcaption></figure>

**Step 2:** Send the query parameters with reference to the YAML file. The query parameters for the above api is attached in  Link for yaml:  [ spec-ms/spec.yaml at dev · Sunbird-cQube/spec-ms](https://github.com/Sunbird-cQube/spec-ms/blob/dev/spec.yaml)

Provide the valid input details for the parameters shown below.

<figure><img src="https://lh4.googleusercontent.com/TgsJXYCXs1XmNr3lBHZklJCukt0HoGTpADliB9stGX_HGPVkS05cuYD1ZeyaWP4Y1_oGqvrKQtc1iz5zTJxkHwZA3T0PV-8cB2Hlyj8iR-04HVnLWEJIN9LbA8G2zVGC75EIeCaO5f4Ek2ldErey-sE" alt=""><figcaption></figcaption></figure>

**Step 3:** Click on the send button for the request and if the request is successful the user should see a response message which contains the status of the file.

<figure><img src="https://lh6.googleusercontent.com/JtKc_052YB5zo2WNvIr-HEF0iUH3UD370b2wEENX3NSHORfdRWyfjzTcV57WMkHu0N6e6Kh29CRTDg_sPNQbHSdlNwCUYJmkbj9YEjVg-XFR8ZHA3CbIF5Gv1VvS_qxYMhghuHZXMhBb-Kn_O45uerA" alt=""><figcaption></figcaption></figure>

If the csv files are too large in size, the upload process of those files will take more time which will make users wait for longer duration to receive the response from the API. As a result, the upload process will be running asynchronously and we have developed this api to know the status of the file at any particular time.\


**Schedule API :**

This API helps to schedule the processor group at any particular time.

### Step 1:&#x20;

Open the specified request & add the details

**API Endpoint:** \<domain\_name>/api/spec/schedule

**HTTP Method:** POST

<figure><img src="https://lh4.googleusercontent.com/NB-aZ4e20WfpPJlzzv9tuYarjLxYkCJ2bfimAFeiABrjSxYTc4TrRuLWslRhMsDbUpRcYqhvXH9o61IoFh2lqmgSw7jHwS2IwNZCemmt_TqrTOR0Rdh-b2UqTIq4mK0RJLxMkWFSq-Fp79lkBpjHYwQ" alt=""><figcaption></figcaption></figure>

### Step 2:&#x20;

Build the request body with reference to YAML file. The request body for the above api is attached in Link for yaml:[ <img src="https://lh6.googleusercontent.com/6iHBv7-J6xyy-5gQJP5LFct6CCSQtWwle7mfLmderwHe8v6_YMtGn_fu6PStM26dCx9TCW2Cqczakl5bTHifrH-LWpnUHrCyJbcIUcY6qKS2tvJqc4eOxtgSbk6-cw_i_XznwisTSBuwldWvQFP1WLU" alt="" data-size="line">spec-ms/spec.yaml at dev · Sunbird-cQube/spec-ms](https://github.com/Sunbird-cQube/spec-ms/blob/dev/spec.yaml)   . Provide the valid input details for the Parameters shown below.&#x20;

<figure><img src="https://lh4.googleusercontent.com/jRI10tM1uT30UwtTaCoFaADJ_Ye_F5eASi_PU3nTA9OhJ1vT1Ct_ahXYLuCn8mmPUTdBxlp2QGQN6gvhto7G1SH_Et8RbOFD0fUGr10pYCyamczk5DGimoOO5todVMI0JB-hHnBhpWAqA5v6OtuG-NQ" alt=""><figcaption></figcaption></figure>

### Step 3:&#x20;

Click on the send button for the request and if the request is successful the user should see a response message. The schedule time will be updated in the processor group.

<figure><img src="https://lh5.googleusercontent.com/FcloJ0J3uWjLSAzzPJG5UyOSJnVKHiJ7rzbZGvafXUfRkYL3c-wxwsaQM4Xp2qbEZydGexoi23ndSVFzAVQSAIkjVB0-B6BEM-iMRQZl77Dcj0Q3o5Dm2Q9cugPCRRQo9tskb6dioeBVMBpm_LEjGAw" alt=""><figcaption></figcaption></figure>

The schedule api helps to run the processor group in Nifi at a scheduled time. The schedule time can be updated by changing the cron expression for scheduled\_at property in the request body.

**Error Monitoring :** &#x20;

The error file will store all the error records during the ingestion process and will be uploaded to the appropriate cloud storage. The user can login to the respective cloud storage and download the file to take a look at the error records present in the csv. The below mentioned steps will specify on how to access the error file.

For VSK programs the error files are stored in the emission\_error folder and inside the folder there will be folders with \<date> as folder name. If there are any errors in the file which was uploaded in the present day then there will be a folder created with \<current\_date> which stores all the error files containing error data.

For new programs  when data ingestion is done using ingestion API’s the error handling is done as follows:

1. Login to respective cloud storage bucket/container.
2. Inside the bucket there will be multiple folders for different processing stages and the ingestion error files  will be stored in ingestion\_error folder. This folder will in turn contain folders for each program(for new programs), the name of the folder will be same as the \<program\_name> specified while adding schema using spec API’s.
3. The \<program\_name> folder will internally have a folder which will have current date as the folder name.
4. The user can access the current date folder if its present and can see the error files present in it and download the error files to view the errors present in the csv.

<figure><img src="https://lh6.googleusercontent.com/xmSXg-XIrqrKy16pJoQv18hCGHOGPub3MIxYBd3rbPrvbGK1Bi_O0-GhzRX10FxVOycU-oJofN5n27n8KOSsptuZ7CTl9FrBx1K_UqYpRWnVTZy3UWguff1LKl56lH5kHJXMaDghkal7Vgt5Jigj8DA" alt=""><figcaption></figcaption></figure>

<figure><img src="https://lh6.googleusercontent.com/hs2vi_4NAxA3RvWAe9Uao-AECvVgXCqq3bZOZXlSBxCMB4_dJ6Gx90BRPt9RTjjOY62OFRaFUlBwtT2VFka8fnGaqa-vnOJuMyZzgLOFtacffIvQIZXv_dJqL1wO0W1kNfjlyICWkN3gQU_FYE21A4E" alt=""><figcaption></figcaption></figure>

<figure><img src="https://lh3.googleusercontent.com/Wr24sgCtU1irUNwNB5-TIfbnt4VumnqNqRPfiBjUADAIwcGVnMJ3HiHrjp9NZ5qEfF0YklmTc2DAC557cn5cFOIDx4Ivw0rdAw2RI48a6Mx9eZPJk6XVFOWazw0zRNaiDjgPkTNz3I8-BkR2E85Bqrs" alt=""><figcaption></figcaption></figure>

<figure><img src="https://lh3.googleusercontent.com/OcYgUnBHf4p0UI7FW-Y1EuN5trC-6z_ALZO69YA526OTjljegAlWJoL3LIWBN87QGdiUDo1oxFXBFB32MVicYpgdsvXBYMco1lmemJKEZLW-7c_4zc53GjHE4yZirRqqvH-mdQoDb_RxsntxcsmUxU4" alt=""><figcaption></figcaption></figure>

<figure><img src="https://lh6.googleusercontent.com/Mrx7TcRBV4TqWZqkDv_cRGu9O53ROJ7jIJ3Dyk62WaEWLsawVh9SI8dFgRBlJe7beiPXpkV_w96YfT6Ffr3keXz_zpm3cjLoOntBm9CB3oMZmjTjeOrtSunQndFTk04wcBgNvkoxsccUrYPgASsYab4" alt=""><figcaption></figcaption></figure>



\

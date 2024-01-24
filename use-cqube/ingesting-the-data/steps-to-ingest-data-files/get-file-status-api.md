# Get file status API

#### Here are the steps for the get file status API

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

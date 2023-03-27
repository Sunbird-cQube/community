---
description: Describes how the status of data ingestion in cQube V 5.0 can be monitored
---

# Monitoring status of ingestion

This can be done via an API in cQube v5.0 in the following manner:

**Step 1:**  Open the specified request & add the details

API Endpoint: \<domain\_name>/ingestion/file-status

HTTP Method: GET

<figure><img src="../.gitbook/assets/image (13) (2).png" alt=""><figcaption></figcaption></figure>

**Step 2:** Send the query parameters with reference to the YAML file. The query parameters for the above API is attached here for yaml: [https://github.com/Sunbird-cQube/spec-ms/blob/march-release/spec.yaml](https://github.com/Sunbird-cQube/spec-ms/blob/march-release/spec.yaml). Provide the valid input details for the parameters as shown below.&#x20;

<figure><img src="../.gitbook/assets/image (6) (1).png" alt=""><figcaption></figcaption></figure>

**Step 3:** Click on the send button for the request and if the request is successful the user should see a response message which contains the status of the file.

<figure><img src="../.gitbook/assets/image (15).png" alt=""><figcaption></figcaption></figure>

If the CSV files are too large in size, the upload process of those files will take more time which will make users wait for longer duration to receive the response from the API. As a result, the upload process will be running asynchronously and we have developed this API to know the status of the file at any particular time.

---
description: >-
  Describes how the processing of ingested data in cQube v5.0 can be scheduled
  at any particular time
---

# Scheduling the processing of ingested data

This can be done through an API in the following manner:

**Step 1:** Open the specified request & add the details

API Endpoint: \<domain\_name>/spec/schedule

HTTP Method: POST

<figure><img src="../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

**Step 2:** Build the request body with reference to YAML file. The request body for the above API is attached here for yaml: [https://github.com/Sunbird-cQube/spec-ms/blob/march-release/spec.yaml](https://github.com/Sunbird-cQube/spec-ms/blob/march-release/spec.yaml). Provide the valid input details for the parameters as shown below. The pipeline name passed in the request body should be present in the database.

<figure><img src="../.gitbook/assets/image (2) (2).png" alt=""><figcaption></figcaption></figure>

**Step 3:** Click on the send button for the request and if the request is successful, the user should see a response message. The schedule time will be updated in the processor group.

<figure><img src="../.gitbook/assets/image (21).png" alt=""><figcaption></figcaption></figure>

The schedule API helps to run the processor group in NiFi at a scheduled time. The schedule time can be updated by changing the cron expression for scheduled\_at property in the request body. The processor group processes the CSV file at a scheduled time and ingests the data into the database.

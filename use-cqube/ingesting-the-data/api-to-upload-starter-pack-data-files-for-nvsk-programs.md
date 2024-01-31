---
description: >-
  This focuses on ingestion of programs like UDISE, PGI, NISHTHA, DIKSHA, NAS,
  PM-POSHAN. The jwt token has to be passed in the API headers.
---

# API to upload starter pack data files for NVSK programs

**Note:** There could be some common errors in the files which could lead to unsuccessful data ingestion into cQube. Look at these errors here and resolve them before ingesting data into cQube.

The already existing files will need to be ingested into cQube via the following process:

This API accepts the data in a zip file format and adds it to the emission folder in the respective cloud storage / SDC.

\


&#x20;**National Programs API:**

### Step 1: &#x20;

Open the specified request & add the details

**API Endpoint:** \<domain\_name>/api/ingestion/national\_programs

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

**Difference between State Specific programs and National programs API**



| State Specific                                                                                                                                         | National Programs                                                                                                     |
| ------------------------------------------------------------------------------------------------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------------------- |
| <ol><li>Accepts file in .csv format</li></ol>                                                                                                          | <ol><li>Accepts file in .zip format</li></ol>                                                                         |
| <ol start="2"><li>It is mainly used when the state team  wants to onboard new programs apart from the starter pack.</li></ol>                          |       2. This API can be used for starter pack             programs of VSK and NVSK                                   |
| <ol start="3"><li>The uploaded file will be present in the process_input folder in cloud storage given that there are no errors in the data.</li></ol> | 3. The uploaded file will be present in the emission folder in cloud storage given if there are no errors in the data |

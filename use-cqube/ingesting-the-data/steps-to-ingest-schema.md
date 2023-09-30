# Steps to ingest schema

## **Note:**&#x20;

To see the API documentation please go to this link [https://editor.swagger.io/](https://editor.swagger.io/) and paste the contents of the github links provided below. The example data provided in the request body is for understanding purposes it is not the actual data.

The API endpoint specified in the below document is for public mode of installation.

## Steps to add the schema for programs&#x20;

### &#x20;Step 1:&#x20;

Create a postman request and add details

**API Endpoint:** \<domain\_name> /api/spec/event&#x20;

**HTTP Method:** POST

<figure><img src="https://lh6.googleusercontent.com/faVudKEqjMTYCjiDPpWIHCF8OqtnDrrZHYoWj-uWAtbN7S_Q747w3Kpt-dpZbvjvxKYE5afpGfgXZbOl9jVrAKDqd1Uhha6ZE1DBqDMugO8jl1qfkpNYdjeAevHp50uxKuC52HIkyQykIjziimINz5U" alt=""><figcaption></figcaption></figure>

### **Step 2:** &#x20;

Build the request body with reference to YAML file. The request body for the above API is attached here for yaml:[ ](https://github.com/Sunbird-cQube/spec-ms/blob/march-release/spec.yaml)[https://github.com/Sunbird-cQube/spec-ms/blob/dev/spec.yaml](https://github.com/Sunbird-cQube/spec-ms/blob/dev/spec.yaml) Provide valid input details for the parameters shown below.

<figure><img src="https://lh6.googleusercontent.com/Da49GbryaKw33EF1MfP7CGHcBi61wNMG8B6UhjhBu29oXl8KWBveEyFqAC1sI6qNtsJhLthtAwck7uuG9BBQifM1SU7zE-S2RlExrV_ViWEThJMMfHL-AKbmHBxEmVkUcr4DcvpbDuDhly0YvW_50d0" alt=""><figcaption></figcaption></figure>

### **Step 3:**  &#x20;

Click on the send button for request and if the request is successful the user should see a response message. Please refer to the below screenshot.

<figure><img src="https://lh3.googleusercontent.com/r62qXfcINgzPCDMasadG90znjEUKOdUzBTdSsKy8li6fcls1U854Zml8-R-0oQhk2ilGQGZtokNiqhACjRN3i5kz3vRqfFtRJgo8-PLwI1HL9_EvatgoDJ9Tmddl3AjpLdkeMVx77jVRkwP-7Wfi72s" alt=""><figcaption></figcaption></figure>

Once the API response is successful then the schema is stored in the spec.”EventGrammar” table.

## Steps to add the schema for dimensions

### &#x20;Step 1:&#x20;

Create a postman request and add details

**API Endpoint:** \<domain\_name> /api/spec/dimension&#x20;

**HTTP Method:** POST

\


<figure><img src="https://lh4.googleusercontent.com/ucPn9qM4H122SF8sZfTQfr6G6lh21xv25yqqTuHCRa4fk4y0xspy1XLXlYdWPuz-5vuDz35ONzAihLzjtbQlC3NowmVO97JkVX3v48IS4LSLsSUuTEvBsuygLyhACU13NrUo5PGz6x7-Sx6lIXI_VCk" alt=""><figcaption></figcaption></figure>

**Step 2:** &#x20;

Build the request body with reference to YAML file. The request body for the above API is attached here for yaml:[ ](https://github.com/Sunbird-cQube/spec-ms/blob/march-release/spec.yaml)[https://github.com/Sunbird-cQube/spec-ms/blob/dev/spec.yaml](https://github.com/Sunbird-cQube/spec-ms/blob/dev/spec.yaml) Provide valid input details for the parameters shown below.

<figure><img src="https://lh6.googleusercontent.com/qKDqFmHtdsNHEHrl18DymaBLbTUD9SNtp2fR7_Riy_vL3-MaOoWv_0iiSjXAMxK_4fLZwi-S5gvfvsCLN5KcG3KZ24ZHDZDyfiAKUTr8Pqkypr88HwVGtTRduuGGoN29r41EWiwzQ52LJbTygyGOZKE" alt=""><figcaption></figcaption></figure>

### Step 3:&#x20;

Click on the send button for request and if the request is successful the user should see a response message. Please refer to the below screenshot. Once the API response is successful then the schema is stored in the spec.”DimensionGrammar” table.

<figure><img src="https://lh6.googleusercontent.com/AM13aDosp284LtloR_Sk2CVcW9uWDlXT0fMdHVLCa15-bVzpf7ckpHJ-K3GB9VrZ_Wv-a9Adv52tj2q-moG5yaUe6OLB_bLRE1F2nezfaP1W-txqn6gf8vHHP8JknMAiNlY2lXUH8p-PRGzJ5ol1k5c" alt=""><figcaption></figcaption></figure>

\

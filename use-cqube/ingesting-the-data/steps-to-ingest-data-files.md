# Steps to ingest data files

### **Note:**&#x20;

The ingestion API’s have prerequisites to work. Whenever any file is uploaded it should have the specified schema stored in the DB. This can be done by making use of spec API’s.

## Generate JWT token API

### Step 1:&#x20;

Create a postman request & add details.

**API Endpoint:** \<domain\_name>/api/ingestion/generatejwt

**HTTP Method:** GET

<figure><img src="https://lh4.googleusercontent.com/mvKxXnKs2Ec2v9gCYXUq8fhsC2hOt6GVU30JLYg1ukgj_sQ9ImQUI0ApO_6DYOW6ziNbyy9c75xKFKO37IE-d5qSDx7yEV3p0_U3Yz55A8Yv6DPgfA_lU16-7jikEtGQ7b7yhAVtiCvWBUm_Uk280ZQ" alt=""><figcaption></figcaption></figure>

### Step 2:

Click on the send button for request and if the request is successful the user should see      a jwt token generated. Please refer to the below screenshot.

<figure><img src="https://lh6.googleusercontent.com/r1WVmOHtC-g_6DArNJVl6m7YvHMh2lfkzGA7Sqd3g_moKxQWUX_ZaELhAEVUdBD0-VW-kxFltDkIK9w5sXSvGpNhBsghwlAR3IUWYcxuMglPsQVoUjk5-MdewyPirXzC6JffIVOiUuJta9Bcv9l0HPs" alt=""><figcaption></figcaption></figure>

## **Note:**&#x20;

The token generated using the above API is passed in Authorization headers in all the ingestion API’s. If the token is not passed then the API will not work. To pass the token in postman go to the Authorization tab in postman and select the bearer token option from the drop down present on the left menu. On the right side paste the jwt token generated through API. Please refer to the below screenshot.

<figure><img src="https://lh4.googleusercontent.com/Di1Qb5hSfcVRulri86DyeGRdWLBJDU4Q_wvbx7kNz9bRv0uhtEqb53ZGKtizVKqP1cLjpHrOMBxED-8GEr4SLUs-uCWngwU_YhQSQSS2sp0eHVOQrh0f4bsWgk88y1gjx3QRTYnJo1sjqnC_RSaxg3Q" alt=""><figcaption></figcaption></figure>

##

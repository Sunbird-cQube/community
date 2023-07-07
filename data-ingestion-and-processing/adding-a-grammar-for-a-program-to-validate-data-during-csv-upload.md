# Adding a grammar  for a program to validate data during csv upload

**Note:**&#x20;

To see the API documentation please go to this link [https://editor.swagger.io/](https://editor.swagger.io/) and paste the contents of the github links provided below.&#x20;

**The example data provided in the request body is for understanding purposes it is not the actual data.**

The API end specified in the below document is for public mode of installation.

### **Steps to add the schema for programs**&#x20;

&#x20;

Step 1: Create a postman request and add details

API Endpoint: \<domain\_name> /api/spec/event&#x20;

HTTP Method: POST

<figure><img src="https://lh3.googleusercontent.com/iGt4we2P26eJXwEe4lGKcrFy1EyQhLqsU-z7QHYMv8B9v7IASz9GnVRa66VnTbxUHkcdMJDTEQHMrihEaaruGCBbkIcKA8PbsTcVDNEI7Onl36-g2y7xc1BrOtWTvc7V-SWDUH1yDxi0A1avLvSXuHs" alt=""><figcaption></figcaption></figure>

\
Step 2:  Build the request body with reference to YAML file. The request body for the above API is attached here for yaml:[ ](https://github.com/Sunbird-cQube/spec-ms/blob/march-release/spec.yaml)[https://github.com/Sunbird-cQube/spec-ms/blob/dev/spec.yaml](https://github.com/Sunbird-cQube/spec-ms/blob/dev/spec.yaml) Provide valid input details for the parameters shown below.

<figure><img src="https://lh5.googleusercontent.com/xvQgKxGL6XlrcKzwoRdn_SGBMedgxSb5_qAO1qkm_X0JSVfVRpdqJNGaFaslVAyFQFSvWSocMY1KTKihOQOhyHUQ_YbCQ9HBA9ZzeIMXZQVGip7kh8lhMRr8B8FAlO-n9AUFQ3tbg5J2uI2ky4notIg" alt=""><figcaption></figcaption></figure>

\


Step 3: Click on the send button for request and if the request is successful the user should see a response message. Please refer to the below screenshot.

<figure><img src="https://lh5.googleusercontent.com/FZlEqfNZht8XbQSVUuhcnACCezQ_fZiFmw7jiwudfnExvTmkZ9t_goXhBcnWPDEFFnRBDwaZ2k4ZHqNqywkL3ViZVdfBdz97SFd8uY7fwW0o9vfL8YzgtYpQTKFcaReXXgOuj9DUgzlzKwwLn2svk2w" alt=""><figcaption></figcaption></figure>

Once the API response is successful then the schema is stored in the spec.”EventGrammar” table.

\


### **Steps to add the schema for dimensions**

&#x20;Step 1: Create a postman request and add details

API Endpoint: \<domain\_name> /api/spec/dimension&#x20;

HTTP Method: POST



<figure><img src="https://lh5.googleusercontent.com/6m7Ad2EZqo8a7-XdmjdTruNdnH7_b-nTuxaLD_gyJRogIJQv6VLj24lpsjPbz6nYgbISHcIVLazNo3FIogI5U89Kbsonr47xdrPP_Z7ApBvBaUmGxm2s5VNF-JdrcvchMNgAeLfU6FnfneuAEBC8poQ" alt=""><figcaption></figcaption></figure>

Step 2:  Build the request body with reference to YAML file. The request body for the above API is attached here for yaml:[ ](https://github.com/Sunbird-cQube/spec-ms/blob/march-release/spec.yaml)[https://github.com/Sunbird-cQube/spec-ms/blob/dev/spec.yaml](https://github.com/Sunbird-cQube/spec-ms/blob/dev/spec.yaml) Provide valid input details for the parameters shown below.

<figure><img src="https://lh4.googleusercontent.com/aIGwugDmTq20cYTuG5JPii7MIsCbBmMMzNGbTa1F4CTBGm0qLRPxelv16XBGfoVKlhqb5k5qTw5vrR2HjaOtSq3baluP64mqGeV-8THJdOYQwBg-XKr-b4bzPnJ2vXTWx3VErz9oJOZeSK6v96wk5Yk" alt=""><figcaption></figcaption></figure>

Step 3: Click on the send button for request and if the request is successful the user should see a response message. Please refer to the below screenshot. Once the API response is successful then the schema is stored in the spec.”DimensionGrammar” table.

<figure><img src="https://lh3.googleusercontent.com/WDwXamOboc0d1slpKKBDiTpCe9VwAZr8sAGJR0gGvTxJk4WOAQmKIM-isJDKO3oQCC4KgCkE5AOLKI62EIqOYmg-BqnTtOrxvfsQgGZZEskHV8iaCquD1z76x9pjY7MKJCF53bR71yj9E8D_8IrXUj8" alt=""><figcaption></figcaption></figure>


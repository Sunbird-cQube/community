---
description: >-
  This focuses on ingestion of programs like UDISE, PGI, NISHTHA, DIKSHA, NAS,
  PM-POSHAN. The jwt token has to be passed in the API headers.
---

# Example: National Programs API

### **Note:**&#x20;

There could be some common errors in the files which could lead to unsuccessful data ingestion into cQube. Look at these errors here and resolve them before ingesting data into cQube.

The already existing files will need to be ingested into cQube via the following process:

This API accepts the data in a zip file format and adds it to the emission folder in the respective cloud storage / SDC.

### **Step 1:**&#x20;

Open the specified request and add the details.

**API Endpoint:** \<domain\_name>/api/ingestion/national\_programs

**HTTP Method:** POST

<figure><img src="https://lh5.googleusercontent.com/yWBsnV6tn-lLM2Zl9yYIcbb3CmcYAg4gsYjDewYQY2SxLw9pulK7UvkVQ4WOJZDcYlQdynC-cDym0yTe5sorkhT2Ec8CnAe-2ttfVh-HzywyRkMkVj4p7MBjSHk4TUj9vt6FV2kyJ5sL8YJPyQGHqc0" alt=""><figcaption></figcaption></figure>

### **Step 2:**&#x20;

Build the request body with reference to YAML file. The request body for the above API is attached here for yaml:[https://github.com/Sunbird-cQube/spec-ms/blob/dev/spec.yaml](https://github.com/Sunbird-cQube/spec-ms/blob/dev/spec.yaml). [ ](https://github.com/Sunbird-cQube/spec-ms/blob/march-release/spec.yaml)Provide the valid input details for the parameters as shown below.

<figure><img src="https://lh3.googleusercontent.com/2VqgB1mrO9_C2wUZrEpjZQCftLc7e3w89CTMtL0jEdGV4_twGa75vjuNEfu1F-JywpmnQ4OxKoeDmr0xlXUyXQkRNNd1SjkUPLa9K-PRETIR5dLx_Ulkr2D0xl76F4I1uKfQLbeZEATiWfIfLuJV65Y" alt=""><figcaption></figcaption></figure>

### Step 3:&#x20;

Click on the send button for the request and if the request is successful, the user should see a response message as “File uploaded successfully”. The files will be uploaded to the emission folder created in the respective cloud storage / SDC.

The zip file will be extracted and will be read by the adapters and then moved into the input folders.

<figure><img src="https://lh5.googleusercontent.com/z4bDExAa1r5JxQvUtaSIpXhBlMvcfNW2Ty2agQ2cmGYQ4CuS41m0p7rle6qLStKyIs1JkOdOZMDDN03mOqe70Sm0SRN2NkA3qmFd3vUnKwercCXSOrba0nPMcceM4ldmALql0IPEp1imHVnFXqEPS-I" alt=""><figcaption></figcaption></figure>

\

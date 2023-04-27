---
description: >-
  Describes how customisations on the login (UI) layer of cQube Ed v5.0 can be
  made
---

# UI Customisations

cQube V 5.0 offers customisations on the UI layer of the login page. Post making these customisations, the UI layer of cQube will need to be redeployed for the changes to reflect on the dashboard as explained [here](ui-customisations.md#steps-for-redeploying-cqube-ui-post-changes).

## Changing Login Page Title, Image, Tagline and Logo

There are 4 configurations enabled here for the login pages.&#x20;

All of these configurations will be done in the UI configuration file, which can be found in the dashboard-ms micro service. You can access this file in this manner: dashboard-ms > src > assets > config > **ui\_config.json**.&#x20;

There are certain keys specified under 'loginObj' for respective configuration to be changed as mentioned below. If there is a need to change any of these configurations, the users need to go to specified location directory (in **ui\_config.json**) as shown below and make the changes:

<figure><img src="../.gitbook/assets/image (31).png" alt=""><figcaption></figcaption></figure>

1. **title :** This key is used to change the title in the login page of the application.

<figure><img src="../.gitbook/assets/image (41).png" alt=""><figcaption></figcaption></figure>

2. **imageURL :** This key is used to change the side image of the application as shown below. The size of the image should be 780px \* 600px. It is depicted in the image below:

<figure><img src="../.gitbook/assets/image (47).png" alt=""><figcaption></figcaption></figure>

The user needs to upload the image into the specified directory: dashboard-ms > src > assets > images.

3. **tagLine :** This key is used to change the tag line specified in the login page of the application.

<figure><img src="../.gitbook/assets/image (46).png" alt=""><figcaption></figcaption></figure>

4. **logoURL :** This key is used to change the logo in the login page of the application. The size of the image should be 60px \* 60px. It is depicted in the image below:

<figure><img src="../.gitbook/assets/image (33).png" alt=""><figcaption></figcaption></figure>

The user needs to upload the image into the specified directory: dashboard-ms > src > assets > images.

## **Steps for redeploying cQube UI post changes**

Run the commands below in the given order to redeploy the UI config file changes for them to be reflected in the visualisation layer:

`sudo docker stop ansible_dashboard_app_1`

`sudo docker rm ansible_dashboard_app_1`&#x20;

`sudo docker dashboard_ms:1`

`cd cqube-devops/microservices/dashboard-ms`

`sudo git pull sudo docker build -t dashboard_ms:1 .`

`sudo docker run -d -p 4200:80 --network ansible_cqube_net --name dashboard_app dashboard_ms:1`

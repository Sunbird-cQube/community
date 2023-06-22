# Changing Dashboard Logos and Headers

There are 5 configurations enabled here for the dashboard pages.

All of these configurations will be done in the UI configuration file, which can be found in the dashboard-ms micro service. You can access this file in this manner: dashboard-ms > src > assets > config > ui\_config.json.

There are certain keys specified for each configuration to be changed as mentioned below. If there is a need to change any of these configurations, the users need to go to specified location directory (in ui\_config.json) as shown below and make the changes:

<figure><img src="https://lh3.googleusercontent.com/_gYxo1u9p6K9Uj-ZH5m6Z_r-ce8LqQKxNwfcNvEV3Mtzi_ZtKXpm2aPnCX8_hLdzs9xefdA0oHXMCK3GzswVFbyBURAAKloZrIKCqOSYz4e4bc3EO0Y2fhoMsL6pRgBnkW7QBHcdNvs2mUzWTiq2xHI" alt=""><figcaption></figcaption></figure>

14.1.1 dashboard\_header1\_title : This key is used to change the title of the cQube dashboard page mentioned at the top. It is depicted in the image below:\
\
\


<figure><img src="https://lh3.googleusercontent.com/nu_iNLhRlzTrs-y-J68fA58q70F7QKCp_xYx82n6F58mVd8uHd6aEWVVma1O-F8k2ZBxSCq35mqDyTf3HGrcr_UJgBaKNv2tdDjLDW6DAnVSBKVlmEDhY_nxJtL74yw0O_wpiJDvozDeuMjR6EihUII" alt=""><figcaption></figcaption></figure>

14.1.2 dashboard\_header1\_image : This key is used to change the image of the cQube dashboard page present at the top. The size of the image should be 32px \* 32px. It is depicted in the image below:

<figure><img src="https://lh6.googleusercontent.com/k3bBGSRqUENx7BamyiI34iyzPqEozqlBSmR6OaQz-trP-uHXi-uEe3Sv6EmzVQCHtzuJCV5TcJC-g8CuUXR89IT2EYcsVce1PkQnEyF8lJx7J6jNcqiCAxXKtjnGp6i6xKzriC-ki3eHXXAI3gUVG88" alt=""><figcaption></figcaption></figure>

dashboard\_header1\_image

The user needs to upload the image into the specified directory: dashboard-ms > src > assets > images

14.1.3 dashboard\_header2\_title : This key is used to change the state name in the title of the cQube dashboard. It is depicted in the image below:

<figure><img src="https://lh5.googleusercontent.com/tY6b_hG_faCC3BpzMCeMk3alzSWg12lJ4ULJWGUA3G2exIAdbpR9uxYoMAL6MuiK3Gkp2w-q7Y1T1I-A0-lwkJlSnY-n1X8JBokhzo_QuWZUUMkRsCy8jCGw5TNt36udpe87yp8bBvi3HZcDowWLLY8" alt=""><figcaption></figcaption></figure>

dashboard\_header2\_title

14.1.4 dashboard\_header2\_image1 : This key is used to change the first image next to the title of the cQube dashboard. The size of the image should be 45px \* \<Any>. It is depicted in the image below:

<figure><img src="https://lh4.googleusercontent.com/PQhJ47xNC8u-QGEdxcy6k6bmoR_L5-dXqPMxj0RoqWPiIO-NeYORCSjwP_IpnmfRwLPU_ElfPvunglLY452vMsZAYZidEJ3jYTCI04KF-B1jAY2Ln66IicbwIMbaIdX2-BkEDepIjvpPhh1JoeS206E" alt=""><figcaption></figcaption></figure>

dashboard\_header2\_image1

The user needs to upload the image into the specified directory: dashboard-ms > src > assets > images

14.1.5 dashboard\_header2\_image2 : This key is used to change the second image next to the title of the cQube dashboard. The size of the image should be 45px \* 45px. It is depicted in the image below:

<figure><img src="https://lh3.googleusercontent.com/KCElwHVWXGDPGPoJypbnv_R2_GKmHdEHyhlv9pOict0OdtwIHraja0XgowlDEh_M3LtjKic2JxFsQWpZ1Ilm5flO1-A3H7Caw-LUxI_EuOAGsNUN7Ukt8vtXjr7lsZGmM6EvLr_kGebFgtBqsdzLrLo" alt=""><figcaption></figcaption></figure>

dashboard\_header2\_image2

The user needs to upload the image into the specified directory: dashboard-ms > src > assets > images

Post making the changes, the user needs to redeploy the code again as explained below.



### Steps for redeploying cQube UI post changes

Run the commands below in the given order to redeploy the UI config file changes for them to be reflected in the visualization layer:

`sudo docker stop dashboard_app`

`sudo docker rm dashboard_app`

`sudo docker rmi dashboard_ms:1`

`cd cqube-devops/microservices/dashboard-ms`

`sudo git pull`&#x20;

`sudo docker build -t dashboard_ms:1 .`

`sudo docker run -d -p 4200:80 --network cqube_net --name dashboard_app dashboard_ms:1`

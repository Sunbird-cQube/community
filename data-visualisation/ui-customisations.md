---
description: >-
  Describes how customisations on the dashboard (UI) layer of cQube Ed v5.0 can
  be made
---

# UI Customisations

## Changing Dashboard Logos and Headers

There are 5 configurations enabled here.&#x20;

All of these configurations will be done in the UI configuration file, which can be found in the dashboard-ms micro service. You can access this file in this manner: dashboard-ms > src > assets > config > **ui\_config.json**.&#x20;

There are certain keys specified for respective configuration to be changed as mentioned below. If there is a need to change any of these configurations, the users need to go to specified location directory (in **ui\_config.json**) as shown below and make the changes:

<figure><img src="../.gitbook/assets/image (7) (3).png" alt=""><figcaption><p>ui_config.json file</p></figcaption></figure>

1.  **dashboard\_header1\_title** **:** This key is used to change the title of the cQube dashboard page mentioned at the top. It is depicted in the image below:\


    <figure><img src="../.gitbook/assets/image (22).png" alt=""><figcaption><p>dashboard_header1_title</p></figcaption></figure>
2. **dashboard\_header1\_image :** This key is used to change the image of the cQube dashboard page present at the top. It is depicted in the image below:

<figure><img src="../.gitbook/assets/image (11) (1).png" alt=""><figcaption><p>dashboard_header1_image</p></figcaption></figure>

The user needs to upload the image into the specified directory: dashboard-ms > src > assets > images

3. **dashboard\_header2\_title :** This key is used to change the state name in the title of the cQube dashboard. It is depicted in the image below:

<figure><img src="../.gitbook/assets/image (2) (1) (2).png" alt=""><figcaption><p>dashboard_header2_title</p></figcaption></figure>

4. **dashboard\_header2\_image1 :** This key is used to change the first image next to the title of the cQube dashboard. It is depicted in the image below:

<figure><img src="../.gitbook/assets/image (2) (5).png" alt=""><figcaption><p>dashboard_header2_image1</p></figcaption></figure>

The user needs to upload the image into the specified directory: dashboard-ms > src > assets > images

5. **dashboard\_header2\_image2 :** This key is used to change the second image next to the title of the cQube dashboard. It is depicted in the image below:

<figure><img src="../.gitbook/assets/image (13).png" alt=""><figcaption><p>dashboard_header2_image2</p></figcaption></figure>

The user needs to upload the image into the specified directory: dashboard-ms > src > assets > images

Post making the changes, the user needs to redeploy the code again.

## &#x20;Changing Program Name, Icon and Side Menu Sequence

The name of the programs, icons and sequence of the side menubar can be changed as explained below.

<figure><img src="../.gitbook/assets/image (1) (3).png" alt=""><figcaption></figcaption></figure>

This can be changed in the menu configuration file present in the query-builder micro service (query-builder > menus.csv).&#x20;

![](<../.gitbook/assets/image (16) (2).png>)

The users can change the menu sequence and program name in this file. They need to add the required details mentioned in the CSV to add a new program in the menu bar. If they add / change any icon for the menu, they need to upload the icon images into the following directory dashboard-ms > src > assets > images

The sample CSV filled is shown below:

<figure><img src="../.gitbook/assets/image (5) (1).png" alt=""><figcaption></figcaption></figure>

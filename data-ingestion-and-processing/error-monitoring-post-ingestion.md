---
description: >-
  Describes how the errors during data ingestion in cQube V 5.0 can be monitored
  and rectified
---

# Error monitoring post ingestion

There may be some errors in the data that is being ingested by the cQube adopter into cQube. All the errors during ingestion can be monitored in cQube.

### Monitoring errors during ingestion

An error file will be created during ingestion, which will store all the error records during the ingestion process and will be uploaded to the appropriate cloud storage. The user can login to the respective cloud storage and download the file to take a look at the error records present in the CSV.&#x20;

### Accessing the error file

Following steps need to be followed to access the error file:

**Step-1:** Go to the cloud storage and locate the bucket / container named as _cQube-edu_.

<figure><img src="../.gitbook/assets/image (16).png" alt=""><figcaption><p>Minio Storage (On-premise)</p></figcaption></figure>

<figure><img src="../.gitbook/assets/image (28).png" alt=""><figcaption><p>Azure Storage</p></figcaption></figure>

<figure><img src="../.gitbook/assets/image (24).png" alt=""><figcaption><p>AWS Storage</p></figcaption></figure>

**Step-2:** Inside the bucket / container, there will be multiple folders for different processing stages. In order to access the ingestion error files, select the _ingestion\_error_ folder.&#x20;

**Step-3:** The _ingestion\_error_ folder will contain folders for each program, the name of the folder will be same as the \<program\_name>.

<figure><img src="../.gitbook/assets/image (27).png" alt=""><figcaption><p>Minio Storage (On-premise)</p></figcaption></figure>

<figure><img src="../.gitbook/assets/image (12) (2).png" alt=""><figcaption><p>Azure Storage</p></figcaption></figure>

<figure><img src="../.gitbook/assets/image (5) (2).png" alt=""><figcaption><p>AWS Storage</p></figcaption></figure>

**Step-4:** If there are errors during ingestion, the \<program\_name> folder will have a folder named as the current date.&#x20;

<figure><img src="../.gitbook/assets/image (3) (3).png" alt=""><figcaption><p>Minio Storage (On-premise)</p></figcaption></figure>

<figure><img src="../.gitbook/assets/image (1) (1).png" alt=""><figcaption><p>Azure Storage</p></figcaption></figure>

<figure><img src="../.gitbook/assets/image (7) (4).png" alt=""><figcaption><p>AWS Storage</p></figcaption></figure>

**Step - 5:** The user can access this folder to see the error files and download the same to view it in the format of CSV.

<figure><img src="../.gitbook/assets/image (25).png" alt=""><figcaption><p>Minio Storage (On-premise)</p></figcaption></figure>

<figure><img src="../.gitbook/assets/image (26).png" alt=""><figcaption><p>Azure Storage</p></figcaption></figure>

<figure><img src="../.gitbook/assets/image (2) (1).png" alt=""><figcaption><p>AWS Storage</p></figcaption></figure>

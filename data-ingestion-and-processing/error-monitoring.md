# Error Monitoring

The error file will store all the error records during the ingestion process and will be uploaded to the appropriate cloud storage. The user can login to the respective cloud storage and download the file to take a look at the error records present in the csv. The below mentioned steps will specify on how to access the error file.

1. The cloud storage bucket/container will be named as cQube-edu.
2. Inside the bucket there will be multiple folders for different processing stages and the ingestion error files will be stored in ingestion\_error folder. This folder will in turn contain folders for each program, the name of the folder will be same as the \<program\_name>.
3. The \<program\_name> folder will internally have a folder which will have current date as the name.
4. The user can access the current date folder if its present and can see the error files present in it and download the error files to view the errors present in the csv.

Please refer to the below screenshots of different storage type( Minio, Azure and AWS) on how to access the error files

## Accessing error files in Minio Storage

<figure><img src="https://lh3.googleusercontent.com/cQAogX6m7eNo4CtREV30lST5a9RVQkG-TelJ07ltRP-G67iYAQEUc3R3B74Z71T2-GGyuN5sRiOLaVAUuwf7eAuxCIzH59eXV_FdM4DEhAVTAW0Ls-L4F3drdPBC33YeJfXodUBHd7qp36Hq0d4Drxs" alt=""><figcaption></figcaption></figure>

<figure><img src="https://lh6.googleusercontent.com/QaHPn5a8ZsFNhrzLeSMNw0n6sOG8SBsKIAdbWlSBTRJ_gSAgTQPLJeqNoKGmh1Oy9lok9q09ZzNS-xaEAKdtvAlcZakewjfw4OSgray8-J-BU9oTygI9AI4gG_gytOnzojbeLj9wMITlBa2-PxUhQnc" alt=""><figcaption></figcaption></figure>

<figure><img src="https://lh4.googleusercontent.com/UBiFAGfKSH94_aGnm_fbUePUAQ2xE7k4lROeTzSJfD3aD1rxFD558qAgWWxKlXUacTDUhkDBSxbTE3GUItS3gUA4p-93rt74zpc4WEKK7azeOmxKFUakiNXmcd_pW9yO-tyxZqp_KHbGSDfdfPvFHJs" alt=""><figcaption></figcaption></figure>

<figure><img src="https://lh5.googleusercontent.com/vYddGGqO3m4YdyVVv7iKRsWF9A9uNvMLYbTSLfU1_daOoT9guN168nPVY7M61NWQhf-qDVJBTM6yfMLXq2Wz43l4tDr7lP_GDwg5E1cVKbA4aJZ1cE89xuLk8XJbQ4e1NpRu4EkD4hAiTXEXPSZWVcg" alt=""><figcaption></figcaption></figure>

## **Accessing error files in Azure**

<figure><img src="https://lh4.googleusercontent.com/cZMUvi4S4o2Bs41c7sPo_XBB7KytgP4l5GyAmxjQIDHog92P0TxG1BwtEgQuAIr59_anqf-cYybkqN_Yd6C46Mfbk6ueZr5d0y-Enn2NPVvo9jqgAn0TL7Q7E7ZdShgGEum3IlY8GIu1Ve-12BUk0tQ" alt=""><figcaption></figcaption></figure>

<figure><img src="https://lh5.googleusercontent.com/CXTDjjXZ0AZSEADSlVp1fJyygNzJvdKs8WG9ou4lwtMv6zulSfJPa-a9i2uBi2E0KsyjtpjifVL_iC1jLpuqyi1BSv9RVRGyqvKQeAiQDpQzV2lNaVrv3GepxPDvglhuFJKnHti2aHPuULK0bwIGoVE" alt=""><figcaption></figcaption></figure>

<figure><img src="https://lh6.googleusercontent.com/c8w-e4UbsKeMtVDJ6JVZsOdJ3QKbD8FQOgpmyleIjV958iLvh_cKMm9FxPaJuElpddy7G5T_VxbmP7TzR28yBuIiz3jpCEhzQiHR-HVAiuCKy7MfJ6wHCl8p71BR4yA3t31_TUD2j398ouuUC_SpnAA" alt=""><figcaption></figcaption></figure>

<figure><img src="https://lh3.googleusercontent.com/bIexexPCbOHPbApFVUHkDOhhFH5HySXTGAnExrX60GSs4xpI2lh8QMuPfPMf-z6R79ZDvyEKPN_7q8Y1B5wrDDPTmQMBPIyYHvrZ1NeDHE12EsA-92zrdoKqFH7xTAwBdTieU6y17e-jQweedltSt2s" alt=""><figcaption></figcaption></figure>

## Accessing error files in AWS

<figure><img src="https://lh6.googleusercontent.com/ImNNOQ3E55gIRphxZer9S8_bGFE7JC3j1LGs1PoSz-ptUuNz8rKJbOGs2cEg6ix_t2EQyjI_p7-Vx_J-O8ekw8xPOLkmFnjfYoKsh1O14jJgUcXQd33pjmmUOKHHNvm6OhRE5km4sZiDaFD5sYlGd5M" alt=""><figcaption></figcaption></figure>

<figure><img src="https://lh5.googleusercontent.com/Zn2im2wsxMDUGt9uqEK1q86dT6zEjAJ88uqSDEGoOZvb3YYwY51LiaMeXRzcctfS_zBPPbcw8VyndDLmj3kPdhMHdXV0aE9CKe7LJwiR0y5fSapf80zedSZTHmN2-m-k4u3nWZHqJHtDQs8XChLEUw8" alt=""><figcaption></figcaption></figure>

<figure><img src="https://lh6.googleusercontent.com/lp0xGtfdgLSECHq_EIpsQ-LjBmJpHdttFCdR3dcZUJzH9CL8-dmAcot_AvplbxZ06k4_UFryWMznrAswIxNXXNTkhNs8QYQJRBazpeyqm1yAiBHOpPQEk4TR9KkemQUwDsKI-ebRi3JfuLZTVv9WqDQ" alt=""><figcaption></figcaption></figure>

<figure><img src="https://lh6.googleusercontent.com/AWD6HWTY-1cgvSinQUZotwzxpZ2RKvqUdrVTNUHwRInByr-5vsybHbYsBAjYBpNNCFpyyvTnhEntB6fbqhwLwp-8yIazgdgin4NE_0A_BUKcNz1D2S70GJxogHIJdzZG2_clw-WejFOKvCowiWbBE4U" alt=""><figcaption></figcaption></figure>

To get the count of processed records and error records GET /ingestion/file-status API can be used.

\

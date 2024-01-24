# Error Monitoring

The error file captures all error records during the ingestion process and is uploaded to the relevant cloud storage. Users can log in to the respective cloud storage platform, navigate to the designated bucket created during installation, and follow these steps to access the error file:

1. For the new\_program API: a) Error files are stored in the "ingestion\_error" folder within the bucket. b) Within "ingestion\_error," there are folders for each program (named after the program\_name). Inside these program folders, there is a sub-folder with the current date as its name. c) Users can access the current date folder, review the error files within, and download them to examine CSV errors.
2. For the national\_programs API: a) Error files are stored in the "emission\_error" folder within the bucket. b) Inside "emission\_error," a folder is created with today's date, containing the error files.

After identifying and rectifying errors, users should re-upload the entire file. Screenshots illustrating how to access error files in different storage types (Minio, Azure, and AWS) are provided below for reference.

<figure><img src="https://lh6.googleusercontent.com/xmSXg-XIrqrKy16pJoQv18hCGHOGPub3MIxYBd3rbPrvbGK1Bi_O0-GhzRX10FxVOycU-oJofN5n27n8KOSsptuZ7CTl9FrBx1K_UqYpRWnVTZy3UWguff1LKl56lH5kHJXMaDghkal7Vgt5Jigj8DA" alt=""><figcaption></figcaption></figure>

<figure><img src="https://lh6.googleusercontent.com/hs2vi_4NAxA3RvWAe9Uao-AECvVgXCqq3bZOZXlSBxCMB4_dJ6Gx90BRPt9RTjjOY62OFRaFUlBwtT2VFka8fnGaqa-vnOJuMyZzgLOFtacffIvQIZXv_dJqL1wO0W1kNfjlyICWkN3gQU_FYE21A4E" alt=""><figcaption></figcaption></figure>

<figure><img src="https://lh3.googleusercontent.com/Wr24sgCtU1irUNwNB5-TIfbnt4VumnqNqRPfiBjUADAIwcGVnMJ3HiHrjp9NZ5qEfF0YklmTc2DAC557cn5cFOIDx4Ivw0rdAw2RI48a6Mx9eZPJk6XVFOWazw0zRNaiDjgPkTNz3I8-BkR2E85Bqrs" alt=""><figcaption></figcaption></figure>

<figure><img src="https://lh3.googleusercontent.com/OcYgUnBHf4p0UI7FW-Y1EuN5trC-6z_ALZO69YA526OTjljegAlWJoL3LIWBN87QGdiUDo1oxFXBFB32MVicYpgdsvXBYMco1lmemJKEZLW-7c_4zc53GjHE4yZirRqqvH-mdQoDb_RxsntxcsmUxU4" alt=""><figcaption></figcaption></figure>

<figure><img src="https://lh6.googleusercontent.com/Mrx7TcRBV4TqWZqkDv_cRGu9O53ROJ7jIJ3Dyk62WaEWLsawVh9SI8dFgRBlJe7beiPXpkV_w96YfT6Ffr3keXz_zpm3cjLoOntBm9CB3oMZmjTjeOrtSunQndFTk04wcBgNvkoxsccUrYPgASsYab4" alt=""><figcaption></figcaption></figure>

## Accessing error files in AWS

<figure><img src="https://lh6.googleusercontent.com/ImNNOQ3E55gIRphxZer9S8_bGFE7JC3j1LGs1PoSz-ptUuNz8rKJbOGs2cEg6ix_t2EQyjI_p7-Vx_J-O8ekw8xPOLkmFnjfYoKsh1O14jJgUcXQd33pjmmUOKHHNvm6OhRE5km4sZiDaFD5sYlGd5M" alt=""><figcaption></figcaption></figure>

<figure><img src="https://lh5.googleusercontent.com/Zn2im2wsxMDUGt9uqEK1q86dT6zEjAJ88uqSDEGoOZvb3YYwY51LiaMeXRzcctfS_zBPPbcw8VyndDLmj3kPdhMHdXV0aE9CKe7LJwiR0y5fSapf80zedSZTHmN2-m-k4u3nWZHqJHtDQs8XChLEUw8" alt=""><figcaption></figcaption></figure>

<figure><img src="https://lh6.googleusercontent.com/lp0xGtfdgLSECHq_EIpsQ-LjBmJpHdttFCdR3dcZUJzH9CL8-dmAcot_AvplbxZ06k4_UFryWMznrAswIxNXXNTkhNs8QYQJRBazpeyqm1yAiBHOpPQEk4TR9KkemQUwDsKI-ebRi3JfuLZTVv9WqDQ" alt=""><figcaption></figcaption></figure>

<figure><img src="https://lh6.googleusercontent.com/AWD6HWTY-1cgvSinQUZotwzxpZ2RKvqUdrVTNUHwRInByr-5vsybHbYsBAjYBpNNCFpyyvTnhEntB6fbqhwLwp-8yIazgdgin4NE_0A_BUKcNz1D2S70GJxogHIJdzZG2_clw-WejFOKvCowiWbBE4U" alt=""><figcaption></figcaption></figure>

To get the count of processed records and error records GET /ingestion/file-status API can be used.

\

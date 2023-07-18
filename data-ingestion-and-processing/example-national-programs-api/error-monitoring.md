# Error Monitoring

The error file will store all the error records during the ingestion process and will be uploaded to the appropriate cloud storage. The user can login to the respective cloud storage and download the file to take a look at the error records present in the csv. The below mentioned steps will specify on how to access the error file.

For VSK programs the error files are stored in the emission\_error folder and inside the folder there will be folders with \<date> as folder name. If there are any errors in the file which was uploaded in the present day then there will be a folder created with \<current\_date> which stores all the error files containing error data.

For new programs  when data ingestion is done using ingestion API’s the error handling is done as follows:

1. Login to respective cloud storage bucket/container.
2. Inside the bucket there will be multiple folders for different processing stages and the ingestion error files  will be stored in ingestion\_error folder. This folder will in turn contain folders for each program(for new programs), the name of the folder will be same as the \<program\_name> specified while adding schema using spec API’s.
3. The \<program\_name> folder will internally have a folder which will have current date as the folder name.
4. The user can access the current date folder if its present and can see the error files present in it and download the error files to view the errors present in the csv.

<figure><img src="https://lh6.googleusercontent.com/-4eXT12YjYOGRakwPuypA6y-UgkSaePDJHCNX6SLiMeaJZk9xSo3XZBPO0wuUe8Si2KMIdKuM1Adu470P6fDik5wlA2Ij70U3dJrlbzZ8In-hidjSjNOLBEd94Tz2jF7CDjb2e1mTUnw01FayWMdjR8" alt=""><figcaption></figcaption></figure>

<figure><img src="https://lh6.googleusercontent.com/_GsL4nDlIqK7koBGcQ718cYq-tbnYDjXcEcIdyuMzVpc_cZU3Bg9E_On1pifCHNuua8ki0ea5vR9M4F7yMgADxuOGDxIS4bv0WDBwvjj5bgVGVto09MJaMzWL9XXexVGinmUmWX8gxEyIPJbYegR6zU" alt=""><figcaption></figcaption></figure>

<figure><img src="https://lh6.googleusercontent.com/21_dCGYCJ6E9NwoBvehMZxOMt58nl6kj5yMAIq8fb5dhI5T2DesN0DvPXdEQsikx_vVbKoNAhUa-4KuK0suN9V-9Fk1J1ziNG0jYhy-WK7EovdeOCI6oMbgEINpQnTG8AHbHswu6p-lokRFrLwKfZEU" alt=""><figcaption></figcaption></figure>

<figure><img src="https://lh3.googleusercontent.com/g6qgMpCEHOmYQDASsfmK7MCPu_t90ZHlbP8N9YeatBsxrdbWn7axaPFwsgmsLI-zXCWXYmNZiK7kbwczrBPDzA0A1fjGsZV-VTukVERpdi08Pu9notg5sf_5LAF8MZwJNevqNSlB7nJQAYHf__2Kct0" alt=""><figcaption></figcaption></figure>

\

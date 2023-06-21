# Error Monitoring

The error file will store all the error records during the ingestion process and will be uploaded to the appropriate cloud storage. The user can login to the respective cloud storage and download the file to take a look at the error records present in the csv. The below mentioned steps will specify on how to access the error file.

For VSK programs the error files are stored in the emission\_error folder and inside the folder there will be folders with \<date> as folder name. If there are any errors in the file which was uploaded in the present day then there will be a folder created with \<current\_date> which stores all the error files containing error data.

For new programs the when data ingestion is done using ingestion API’s the error handling is done as follows:

1. The cloud storage bucket/container will be named as cQube-edu.
2. Inside the bucket there will be multiple folders for different processing stages and the ingestion error files  will be stored in ingestion\_error folder. This folder will in turn contain folders for each program(for new programs), the name of the folder will be same as the \<program\_name>.
3. The \<program\_name> folder will internally have a folder which will have current date as the name.
4. The user can access the current date folder if its present and can see the error files present in it and download the error files to view the errors present in the csv.

\


<figure><img src="https://lh3.googleusercontent.com/EyoceJIJicQnTVZayH_ZS1MnlyPBJ6E3OTetcP2A6d4vQUVZ75y0-oMe3B4sRB3T-to6CX5NfifjRw1a98Ba15rIdqs_806_zw0671EfzK8zmmut1vou_c0HNJdI9GHWzWiPJd6hKvPWawn6X_Sp4aw" alt=""><figcaption></figcaption></figure>

\


<figure><img src="https://lh6.googleusercontent.com/tW7hqyvu0C4-tsUBDaKoESySBmfH28LRKRn6EuVF8I2duVHnIE0eWtBO1HlB4DEabriU03XS75hWd6aN8Z5bAm9A0ZzgFetUa4X_owk_KhHy7JLaF5ygiyMLb_zu-QYJfrSbImzT_0up9-aaf3S9PJA" alt=""><figcaption></figcaption></figure>

\


<figure><img src="https://lh6.googleusercontent.com/LxOkj0znuGRDq-Yb855aQyjFJWExU7OBJYuaz1FknJgsNe8npFt8e9EKBUUtYr8ULA0aOyvXv9SlKQwY0qnzs3IVdtW7n-cKzV0ckr-3eVhUyiGOD6nTSGj-eC6PjJDVPP3ixvWZlFTeffyM_rMqYjc" alt=""><figcaption></figcaption></figure>

\


<figure><img src="https://lh3.googleusercontent.com/G0Pl4jnTCCgE3WLpRGilwgqCurLv4Or2QT11lxX4KsvwqP5m7awC7oR4mUfC8v-KyJkZhp9XlaFfVxSK_CNMGiUh5my_7vdD-4Vd6s9k_NltDo28XglHdQV57yvaN5X2jkXkdaTPEgMLB1AL0Yh7wds" alt=""><figcaption></figcaption></figure>

\


<figure><img src="https://lh5.googleusercontent.com/LJk0w6M2YL1Tu4-8GwfMP8KEzvqmn6jbzyLPmhPt0hsSkjq2FVEYnDLl4jGpCwRXGGK6j90hdSABFr-pjiyMLyfZ-_teEBa69wLKQDxpreaqrCHU2wUpTdbcuxzFYckBFRb-sssOL2FTsokDJSSFKHg" alt=""><figcaption></figcaption></figure>

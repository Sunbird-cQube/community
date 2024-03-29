# AWS Deployment

&#x20;Here the details for the complete deployment process

**Prerequisites to install cQube on AWS machine**

* Ubuntu 22.04 (supported)&#x20;
* &#x20;16 GB of System RAM (minimum requirement)
* &#x20;4 core CPU (minimum requirement)
* &#x20;Domain name ex: https://cqube-demo-cert.tibilprojects.com
* SSl certificate keys ex: certificate.crt and private.key
* AWS access\_key and secret\_key
* &#x20;250 GB Storage

**Step 1:** Use the following command to connect to the AWS instance

&#x20;              ssh -i \<path\_to\_the\_pem\_file> \<user\_name>@\<public\_ip\_of\_the\_instance>

&#x20;             **Ex: ssh -i poc\_key.pem -o ServerAliveInterval=60 ubuntu@13.200.12.31**&#x20;

**Step 2**: Clone the cqube-devops repository using following command

&#x20;               git clone [https://github.com/Sunbird-cQube/cqube-devops.git](https://github.com/Sunbird-cQube/cqube-devops.git)  &#x20;

<figure><img src="https://lh4.googleusercontent.com/24la-c3z7usSWqXH9eQmv5wTynOWYuUoC35pobDgLzBk2-T08oQdygbOnbKPzsas_9WwUGoo4pIAjjR-BYdt7Kanf4FQek-3PYf5fSUX7UqHZc7LOEbuv9q8HM0ciNDbb1SH2abWQI7VJ0N3jBA-f88" alt=""><figcaption></figcaption></figure>

**Step 3:** Navigate to the directory where cqube is cloned or downloaded and checkout to the desired branch(Release Branch)

&#x20;                                cd cqube-devops/&#x20;

&#x20;                                git checkout release-v5.0.5(latest release branch)

<figure><img src="https://lh5.googleusercontent.com/SNlt2aYh61rk83eTmD-4P2vuSPP_vq-JbgZ9kBmBFRJzbzBFL_XPsE2IdRxICbu90oiWPDvI5lIHYG5un3TH3a5zgFTx0QC6gZd3eHNNU01kxGBEkYDmO0GsRu742Do6DEW58KX4355SO4Nrk0NytpM" alt=""><figcaption></figcaption></figure>

**Step 4:** After checkout of the latest branch, we need to move the SSL keys (.crt and.key) to the mentioned path, as shown in the below screenshot.

&#x20;                       Path: cqube-devops/ansible/ssl\_certificates

**Command for moving ssl keys:**

&#x20;                       cp certificate.crt  private.key /home/ubuntu/cqube-devops/ansible/ssl\_certificates

<figure><img src="https://lh5.googleusercontent.com/JEAnluvA_6GJZu4RdQAm8_hC5kpmXauxfzaqzErltZTc-igVIlhtOFqsSdEsfY_gYR_9aJ9d_Nj3pq1d3p-GGUvvgQQtS8TCG11o1zorFz1f9Nuf4YZyAtMTkVFeRYCytwv0U6uiz1GgrFgvLple-8U" alt=""><figcaption></figcaption></figure>

**Step 5:** After copying the ssl keys similarly, we can move the VSK dimension to (state,district,grade,subject,medium) below the mentioned path, as shown in the screenshot below.

**Command for moving dimensions:**

**(Note: This Step 5  is applicable for pulling the data from NVSK )**

&#x20;                      cp state-dimension.data.csv grade-dimension.data.csv subject-dimension.data.csv etc../home/ubuntu/cqube-devops/ansible.dimension\_files

&#x20;                      Path: cqube-devops/ansible/dimension\_files.

<figure><img src="https://lh5.googleusercontent.com/DhCvqRvrO-7MVBgzcH3sueBGZ6g1Du-af-w-TXQBjcyNNYyllvIr4qBKmV-3DwwZr2CJGNDWsY4LoWmEbeG1PSpUZY_4Wa_XYtpoljiqdGQ7Gy0mEJP_onYlQlg2ZIGyH47EAesWXYDCiPGeV5L1G5o" alt=""><figcaption></figcaption></figure>

**Step 6:** Give the following permissions to the install.sh file

&#x20;                      sudo chmod u+x install.sh

**Step 7:** Install cqube with non root user with sudo privileges

&#x20;                       sudo ./install.sh

<figure><img src="https://lh4.googleusercontent.com/6Ceax5QyiqtNR0guJamDCA_CNpvX587dUQOzgyPKry5dkmVRt3ByNY3O44fPUyesD6Pes0WwtaScw0eYT8-X9jBD3KLtkW82DRAhu8MtKTO8jnhbfBsDjZkv6-qHqOJj6Ut-bS_Fr8W5wL914ogJgLk" alt=""><figcaption></figcaption></figure>

* Access\_type(Enter NVSK or VSK or Others)
* state\_code ( Enter the required state code by referring to the state list provided )
* Do want to enable login screen for cqube instance(Enter true or false)
* Do you want to pull the data from the NVSK server?(Enter true or false)
* Please enter the end point to pull the data (Ex: cqube-demo-nvsk.tibilprojects.com)

**Step 8:** User Input Variables - These are the variables which need to be entered by the user by following the Hint provided

Install.sh file contains a shell script where it will run shell scripts and ansible-playbook to setup the cQube

<figure><img src="https://lh5.googleusercontent.com/Z16--MibQujgoKCEUx1F4DDrcup27nG6AmrQXkKn_chgucEl9g1CEuFnTCtYy09nMvnc0wl9rczZxZ5-eX2azcuDKv4TZPER8YlWOaEuVBidlMdPQOCStq1Xf936xIf0B1sI2i2y0HrrOjZLhqhcgkM" alt=""><figcaption></figcaption></figure>

* Mode of installation: Public
* Storage\_type : aws
* API\_Endpoint(Enter the domain name :  (ex: cqube-demo-cert.tibilprojects.com)
* Please enter the name of cert file: ( ex:certificate.crt)
* Please enter the name of key file:  (ex: private.key)

**Step 9:** Once you enter the above user input it will create one config file.please preview the config file and confirm if everything is correct.if it is correct type “no” and proceed and else type “yes” then correct it.

<figure><img src="https://lh3.googleusercontent.com/Obgxo291qAm0nXG3UZUKvM7mdiVyGhuzZJwydnHcewD3lzv8AiZB3AF7Y-KYPJgRIlefjIMmDJmfmZwAixUwRNX1mSk8VQuhCsZgSjvga8hQfrGrewlXRr9edhMBb5ql_jDrZV15dqSNtwQX2mDVgrY" alt=""><figcaption></figcaption></figure>

* db\_user\_name ( Enter the postgres database username )&#x20;
* db\_name ( Enter the postgres database name )
* db\_password ( Enter the postgres password )
* &#x20;read\_only\_db\_user( Enter the read only db user)
* read\_only\_db\_password( Enter the read only db password)
* keycloak\_adm\_name( Enter the keycloak admin name)
* &#x20;keycloak\_adm\_password( Enter the keycloak password)

**Step 10:** Optional\_variables- Database credentials contain default values. If the user wishes to enter their own credentials then the user should opt for ‘yes’ to enter their credentials otherwise can opt for ‘no’ when the question pops up

<figure><img src="https://lh5.googleusercontent.com/F0AOBp-ue8AvmbIbAfP7957Soc--_5PUwF5Rshc_oeYTj5pgEcV5oseX4TMnqRjK5WSUfQbNzmDqDH3Je_HMS3w3PTOnliPkIYneVVaGAGe-RT4o8K3JArXKvsWW4pZWHSty_jlcNliI0K3uEvfx8xQ" alt=""><figcaption></figcaption></figure>

**Step 11:** Once the config file is generated, A preview of the config file is displayed followed by a question where the user gets an option to re enter the configuration values on choosing yes. If option no is selected then the install.sh moves to the next section.

<figure><img src="https://lh4.googleusercontent.com/Yz1NMCBiU-JR9s8Z3y0A84mcP7HYU32QsK9ZSX_ZHD_zQgGkbzmScWGAWGMFFmrKfPKTn-f43WJ5q3q_5pPqnjQQ3wQPOuify-C_8NAporlQWPeNP9QhINC_lGW8btb_l_f2BbQzhpqfusRjuDf7IGs" alt=""><figcaption></figcaption></figure>

**Step 12:** A preview of the program\_selector.yml file is displayed followed by a question where the user gets an option to enable or disable the programs on choosing ‘yes’. If option ‘no’ is selected then the install.sh moves to the next section.

<figure><img src="https://lh4.googleusercontent.com/L8Wl3Hnptsqa0kYfp4ZqeHxmpQIo29FsQlJbI7P3kXBBLjMamUN2H0iEm3vA6Z538kPC7fqhrKngqc471QWrGZTOfC6jIW1zKKdtifnlOZRAeeAs5N9K-ESI8x7E-wB5b62dCEOjGEBQ7_na6JFTF5M" alt=""><figcaption></figcaption></figure>

**Step 13:** Once the installation is completed, You will be prompted with the following messages and required reference urls.

**cQube Installed Successfully**

cQube ingestion api can be accessible using \<domain\_name>

<figure><img src="https://lh4.googleusercontent.com/oGmKJZ2-5wSwVhQdrhLe5GIShERwX3pK8AKs8G6XjMWnb2-U2ZZbQJcwrS5HCYdAMgaXCkSaSKbpYae0r0YKZdDNxL1ElOoz4YuRzICjEzFAgkyetM7e973WlMhfHQo0Hv_xdW3x68vX9aXUw0PWSZg" alt=""><figcaption></figcaption></figure>

* After installation check the docker containers are up or not
* Sudo docker ps -a

<figure><img src="https://lh7-us.googleusercontent.com/xE38bQFwin4f7fznyjUjUQCUQ550m0fjEnWdRhLTmxwrbtraCfdEGZWS6w63rx7kHuMvQ_wF2vvcO0g0d_HDpPwpvEUZ4u7-iDt-s7pIBGGvSulTIMT7Et5j5sohOrc1pa_JOipYu8i7Wbrv7Mq5SpU" alt=""><figcaption></figcaption></figure>

**Ingestion Flow:**

**Setting up Postman:**

* [Download](https://www.postman.com/downloads/) the postman application and import the collection.
* Select the import option in the postman then select the upload files to import the collection. Please refer to the below screenshot.

<figure><img src="https://lh4.googleusercontent.com/G8g6Ic0gcMJNScE_SdgRwr7APJo7JUEhqWvSlXYdufHhfkQgh1a32IQrESxhgDwGmGmZPoYoLUbH6neyeY9Bj29tASrG43zNx4oNod8TehZdNloDOiq_yrxj0ARuAOUdiNuSqVJdGLnY99OtBmGulIU" alt=""><figcaption></figcaption></figure>

\


* Upload the cQube\_latest.postman\_collection .json file and VSK\_Schema.postman\_collection.json,

[https://drive.google.com/drive/u/0/folders/12Wn7UIHgUhq6U3GzlRN-zdrJMnj1hrPO](https://drive.google.com/drive/u/0/folders/12Wn7UIHgUhq6U3GzlRN-zdrJMnj1hrPO)

* After installations first need to create the jwt token in postman as shown below screenshot.

API\_Endpoint: [https://cqube-ssl-test.tibilprojects.com/api/ingestion/generatejwt](https://cqube-ssl-test.tibilprojects.com/api/ingestion/generatejwt)

<figure><img src="https://lh7-us.googleusercontent.com/vJtPWO34t8f2HAmlYyNpe2kg1_Nnsk4a_uyMV-LFoENJav8r9SddvO2o5KCVOOdG-9aoAgtzSYy2XUrTnfOQLF6k1Byv81hdXP7VbtXNRBST6FIGl94voh_zTKGrn2xmZ4R3eqwxWCZV_4VU9PNNC7Y" alt=""><figcaption></figcaption></figure>



* After creating the JWT token then upload the vsk\_schema and dimension schema as shown below screenshot

&#x20;API Endpoint:[ ](https://cqube-ssl-test.tibilprojects.com/api/ingestion/national\_programs)[htpps://cqube-ssl-test.tibilprojects.com/api/spec/event](https://cqube-apr27-demo.tibilprojects.com/api/spec/event)

<figure><img src="https://lh7-us.googleusercontent.com/qpNEnirkXm7J3tSf9unLHFynC1Cj6ebmqxkjqG5wgG_EyZiE3DbAkMhncRCfamZNcfllxPRgSuiSxNe6KqmkT8wSqy5tdFNXQ8DmdB5LXmAxfKDAOL5yiuik-YEUsHcskiEokviRHvSfN5-wljOHCWw" alt=""><figcaption></figcaption></figure>

Run the both schema at a time (click on 3 dots and select Run collection)

* After uploading the grammar files,Just copy the generate token and add into national\_programs and new programs
* Go to authorization and select Bearer token, then paste the token&#x20;
* Then I need to upload the VSK data(NCERT) as shown in the below screenshot.

&#x20;           API Endpoint:[ ](https://cqube-ssl-test.tibilprojects.com/api/ingestion/national\_programs)[https://cqube-ssl-test.tibilprojects.com/api/ingestion/national\_programs\
](https://cqube-ssl-test.tibilprojects.com/api/ingestion/national\_programs)

<figure><img src="https://lh7-us.googleusercontent.com/yi4ruRGMYzZmwQl3uuHuaR1vDYyoNHTOel2CeYCVAZv0QxD6NJfx-yPQC-FxVFiQ_AO4lPrZBC3CcTzDtsWCjNfISDtyqyebEYhGhveoJlHywqkIOmAdDurYSuVZHH4XZAFFW6WGDLRuhjzb96GrlEE" alt=""><figcaption></figcaption></figure>

* We need to ingest only three programs (pgi,diksha,nishtha)data through API. The other three programs automatically pull the data from the NVSK server.
* For above point we need to upload (PGI, DIKSHA, NISHTHA) three programs schema and ingest the raw files to the aws emission bucket.
* Then we can schedule the below mentioned processor groups one by one by using schedule API as shown in the below screenshot
  * &#x20;Run\_adapters
  * data\_moving\_aws

\


<figure><img src="https://lh7-us.googleusercontent.com/zapTPsHQg6EefoQCqQXBlq_60teMoNJUUVxic0Eid-e0ZyDkiwCEybVxuYxkfGzLcHryQUn_ym-j4luaFtClIt2ltyM-WZg3JHbZYxawTH8IZe5wGFQzbRvhuxoKgfpXG_A_y7cPorHtcMTNw7f_qX8" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

*   After the schedule, the programs should one by one by using schedule API as mentioned in the below screenshot.

    Bbody:

    {

    &#x20;   "processor\_group\_name": "ingest\_data",

    &#x20;   "scheduled\_at": "0 31 14 \* \* ?",

    &#x20;   "program\_name": "nishtha"

    }

<figure><img src="https://lh7-us.googleusercontent.com/Ypr5SVcSJ3AuGVFhCvt_gGT98ocMPawzN8BqbG7VUJ2eamsy4lyTNPJscBz8zIv_fJYB7UpfWEUMxgDpbQRbyosTfT1nyluht3bgkhQ1Zdw0gzAz74-hATVpBIChPVLrGRRzORaVPOri8hXxvooyWhA" alt=""><figcaption></figcaption></figure>

\


* Check the visualization in the UI dashboard. As shown in the below screenshot.

<figure><img src="https://lh4.googleusercontent.com/U6iWqfNUVi6nrnCRoqO0DjUABoeF-RzkFXW5Ytblqvgc8GFkasQ7JqfyDKtkq1NeU8EJmAZRzDgimrRlAG5MS9x0TJqm1hBpQejedmZAIenPnbUBZEnKyvrRO-WqOoaHs_NvC1w-dw1jXtYZDPpugz8" alt=""><figcaption></figcaption></figure>

\
\
\
\
\


\
\
\

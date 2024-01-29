# SDC Deployment

**Prerequisites to install cQube on local machine**

* Ubuntu 22.04 (supported)&#x20;
* &#x20;16 GB of System RAM (minimum requirement)
* &#x20;4 core CPU (minimum requirement)
* &#x20;Domain name (with SSL), ex: https://vsk.scertchd.edu.in/
* &#x20;250 GB Storage



**Step 1:** Use the following command to connect to the On-premise instance

&#x20;            ssh -i \<path\_to\_the\_pem\_file> \<user\_name>@\<public\_ip\_of\_the\_instance>

&#x20;            **Ex: ssh -i poc\_key.pem -o ServerAliveInterval=60 ubuntu@13.200.12.31**&#x20;

**Step 2:** Clone the cqube-devops repository using following command

&#x20;            git clone [https://github.com/Sunbird-cQube/cqube-devops.git](https://github.com/Sunbird-cQube/cqube-devops.git)    &#x20;

<figure><img src="https://lh4.googleusercontent.com/X52JlR-8CHhXM6tS3-6VdVoNvx1kFYrYp1iOH-3BDb1MQet3e52fuaWz73lmq7lTv7VA8S504QtwuRYT2KP9GOli5pBgqg_uybfnB2WXrl0MylbIABtMbA5Rj7m2CInqDrKsESBMFs7k3HMyZj3FZUQ" alt=""><figcaption></figcaption></figure>

**Step 3:** Navigate to the directory where cqube is cloned or downloaded and checkout to the desired branch(Release Branch)

&#x20;             cd cqube-devops/&#x20;

&#x20;            git checkout release-v5.0.5(Latest release branch )

<figure><img src="https://lh6.googleusercontent.com/qrWu_KUQD_INTnbYVwdmkf0wTOp-8JU_Px7HG7mF9L0wXoYSFIV3rLuqUZHOXIXC3szTIeHfWJR78lJ6TJ-7IfeSL3XVprq1iKrXQBoHzSsblc8dyVNheewBHALLrUWNoOcMV9YOh6TMvVpcxjGzdzs" alt=""><figcaption></figcaption></figure>

**Step  4:** After checkout of the latest branch, we need to move the SSL keys (.crt and.key) to the mentioned path, as shown in the below screenshot.

**Command for moving ssl keys:**

&#x20;             cp certificate.crt  private.key /home/ubuntu/cqube-devops/ansible/ssl\_certificates

&#x20;             Path: cqube-devops/ansible/ssl\_certificates

<figure><img src="https://lh7-us.googleusercontent.com/GO-OzWIj5zPLqxHlywifxxtnkSgtmpZN9davkg5eRWRLu-hRPw11o_BU0cDUvpVVH9DaTcd3hLY1Ne5nErMUtlouXq-0M2vkkrChkGexGtO3TJrZujJo_uaIiLu5nR_yS1PT49QnofyAWfwGQdAaM2k" alt=""><figcaption></figcaption></figure>

**Step 5:** After copying the ssl keys similarly, we can move the VSK dimension to (state,district,grade,subject,medium) below the mentioned path, as shown in the screenshot below.

**Command for moving dimensions:**

**(Note: This Step 5  is applicable for pulling the data from NVSK )**

&#x20;                  cp state-dimension.data.csv grade-dimension.data.csv subject-dimension.data.csv etc../home/ubuntu/cqube-devops/ansible.dimension\_files

&#x20;                Path: cqube-devops/ansible/dimension\_files.

<figure><img src="https://lh7-us.googleusercontent.com/b87hfG-Kzb5nfNIYFY_25W17c6P139n8k23IZ6Sq7bWqfLPcjeg_vltTZ6BpZ6oqKS6W9e2fLNWFZ6yr6c5keHFtdv6La1sn_uqraTCj8_qbL0PvFJgM3GloCcS6W4TTQrc6mM0D2m2b6UWqGzVCPNo" alt=""><figcaption></figcaption></figure>

**Step 6:** Give the following permissions to the install.sh file

&#x20;               sudo chmod u+x install.sh

**Step 7:** Install cqube with non root user with sudo privileges

&#x20;              sudo ./install.sh

<figure><img src="https://lh7-us.googleusercontent.com/iQ8cuU7RyZdlyS--G3meu66JvXIHoXfYw0uoH0te1dbXl6QvXc7NRK0VjhHI_opO4gMloybAvGTAq4y_k5fTT7VF9aSzcgc9w5J9lgHE8A3oY1kNlP4Pd4tu3QXDhBCsVTSArihkE5JklMFQuuvd0lA" alt=""><figcaption></figcaption></figure>

Install.sh file contains a shell script where it will run shell scripts and ansible-playbook to setup the cqube

**Step 8:** User Input Variables - These are the variables which need to be entered by the user by following the Hint provided

* Access\_type(Enter NVSK or VSK or Others)
* state\_code ( Enter the required state code by referring to the state list provided )
* Do want to enable login screen for cqube instance(Enter true or false)
* Do you want to pull the data from the NVSK server?(Enter true or false)
* Please enter the end point to pull the data (Ex: cqube-demo-nvsk.tibilprojects.com)

<figure><img src="https://lh7-us.googleusercontent.com/XYWbpWBHCNfPxu7tfp7BdhroPsEOyRNZQ-Skit_18voAAVWXBt3suf5TNaqDOHUT0KIblA4xwLLGynJt4-Z0X8RNPZtSGc4XRelikjxUzN86j4sBPfX7dfQHGlYAZ802lrm8al1HXjXFmZSqOD7wKFM" alt=""><figcaption></figcaption></figure>

**Step 9:** Once you enter the above user input it will create one config file.please preview the config file and confirm if everything is correct.if it is correct type “no” and proceed and else type “yes” then correct it.

* Mode of installation: Public
* Storage\_type : local
* API\_Endpoint(Enter the domain name ex: cqube-demo-cert.tibilprojects.com)
* Please enter the name of cert file( ex:certificate.crt)
* Please enter the name of key file (ex: private.key)

<figure><img src="../.gitbook/assets/image (83).png" alt=""><figcaption></figcaption></figure>

**Step 10:** Optional\_variables- Database credentials contain default values. If the user wishes to enter their own credentials then the user should opt for ‘yes’ to enter their credentials otherwise can opt for ‘no’ when the question pops up

* db\_user\_name ( Enter the postgres database username )&#x20;
* db\_name ( Enter the postgres database name )
* db\_password ( Enter the postgres password )
* &#x20;read\_only\_db\_user( Enter the read only db user)
* read\_only\_db\_password( Enter the read only db password)
* keycloak\_adm\_name( Enter the keycloak admin name)
* &#x20;keycloak\_adm\_password( Enter the keycloak password)

<figure><img src="https://lh7-us.googleusercontent.com/mY6HBXHfzd-lkr3cNvdsiuU5lRY1f8u5CdmS-P8l1_LhcOdZWHbFn4mFQZ6x8q6D3o6W_hL82nQjcOvu3MJRwwMWBRRXswHE7RUMwFRnpjt_xWKVEnjsuxbeqvpLS-fO5NeNeQMaNZwG2nhKOuvO8GU" alt=""><figcaption></figcaption></figure>

**Step 11:** Once the config file is generated, A preview of the config file is displayed followed by a question where the user gets an option to re enter the configuration values on choosing yes. If option no is selected then the install.sh moves to the next section.

<figure><img src="https://lh7-us.googleusercontent.com/ZxNFPaMU0SAWxonVDO6cTBYHbHnjxxHT2uMKyWUyB6d7jGXGny46GUfZMu1f_h8F55pmBmKeeN8iZE0fCLn_Ok8TNpSouPvMM9DsMzdworouWhd81d-xk_XFb5qpPtvipgysSOENhKvWkwAPI3x94Qg" alt=""><figcaption></figcaption></figure>



**Step 12:**  A preview of the program\_selector.yml file is displayed followed by a question where the user gets an option to enable or disable the programs on choosing ‘yes’. If option ‘no’ is selected then the install.sh moves to the next section.

<figure><img src="https://lh7-us.googleusercontent.com/tSEjvNGTkIC4gZ3wVLe_qu7KQG3F93M1-PZOI_S6XKjn2LwKAhAkmUxh50AtqpGPpfObMSMNs3GQ980jAEXAozhPMkTEIEJWMmlXjFZ8Xovetv72RA1rPQ1cEbqDEsbxw9YKS7x3L1q3FTHbBHWkTNA" alt=""><figcaption></figcaption></figure>

**Step 13:** Once the installation is completed, You will be prompted with the following messages and required reference urls.

**cQube Installed Successfully**

cQube ingestion api can be accessible using \<domain\_name>

<figure><img src="https://lh7-us.googleusercontent.com/d4R92pktsFD2vGBLKBFzF0MI3NhcG3xv20iKlZ-d3gSIgne77QlHTclJPKfIalSRgYB_qIW1BC5mjdhOInjvKr_X2GlMEG2zUzp-m1r1iwz8nhlJ2knhXKtYtDyUmWsHwZU86DCePg2V0PDd5lrfWUg" alt=""><figcaption></figcaption></figure>

* After installation check the docker containers are up or not
* Sudo docker ps -a

<figure><img src="https://lh7-us.googleusercontent.com/xE38bQFwin4f7fznyjUjUQCUQ550m0fjEnWdRhLTmxwrbtraCfdEGZWS6w63rx7kHuMvQ_wF2vvcO0g0d_HDpPwpvEUZ4u7-iDt-s7pIBGGvSulTIMT7Et5j5sohOrc1pa_JOipYu8i7Wbrv7Mq5SpU" alt=""><figcaption></figcaption></figure>

\


**Ingestion Flow:**

Setting up Postman:

* [Download](https://www.postman.com/downloads/) the postman application and import the collection.
* Select the import option in the postman then select the upload files to import the collection. Please refer to the below screenshot.

<figure><img src="https://lh7-us.googleusercontent.com/fEgzfIPm9GTUFu7G-FXvM26084n2WZpZpLqKqIkCiG0OqGkFadHjCHoe5gpI7zMd1fg6uCz2s3MYQuX-v6qTY9M250rCQCxGAtANDJtdfWZWYQXfKK7qKwDmzF9mCny4brszZG464DVG-OgqrheJYEc" alt=""><figcaption></figcaption></figure>

\


* Upload the cQube\_latest.postman\_collection .json file and VSK\_Schema.postman\_collection.json,

[https://drive.google.com/drive/u/0/folders/12Wn7UIHgUhq6U3GzlRN-zdrJMnj1hrPO](https://drive.google.com/drive/u/0/folders/12Wn7UIHgUhq6U3GzlRN-zdrJMnj1hrPO)

* After installations first need to create the jwt token in postman as shown below screenshot.

API\_Endpoint: [https://cqube-ssl-test.tibilprojects.com/api/ingestion/generatejwt](http://vsk.ap.gov.in/api/ingestion/generatejwt)

<figure><img src="https://lh7-us.googleusercontent.com/vJtPWO34t8f2HAmlYyNpe2kg1_Nnsk4a_uyMV-LFoENJav8r9SddvO2o5KCVOOdG-9aoAgtzSYy2XUrTnfOQLF6k1Byv81hdXP7VbtXNRBST6FIGl94voh_zTKGrn2xmZ4R3eqwxWCZV_4VU9PNNC7Y" alt=""><figcaption></figcaption></figure>

* After creating the JWT token then upload the vsk\_chema and dimension schema as shown below screenshot

&#x20;API Endpoint: [htpps://cqube-ssl-test.tibilprojects.com/api/spec/event](https://cqube-apr27-demo.tibilprojects.com/api/spec/event)

\


<figure><img src="https://lh7-us.googleusercontent.com/qpNEnirkXm7J3tSf9unLHFynC1Cj6ebmqxkjqG5wgG_EyZiE3DbAkMhncRCfamZNcfllxPRgSuiSxNe6KqmkT8wSqy5tdFNXQ8DmdB5LXmAxfKDAOL5yiuik-YEUsHcskiEokviRHvSfN5-wljOHCWw" alt=""><figcaption></figcaption></figure>

Run the both schema at a time (click on 3 dots and select Run collection)

* After uploading the grammar files,Just copy the generate token and add into national\_programs and new programs api
* Go to authorization and select Bearer token, then paste the token&#x20;
* Then I need to upload the VSK data(NCERT) as shown in the below screenshot.ii

&#x20;           API Endpoint: [https://cqube-ssl-test.tibilprojects.com/api/ingestion/national\_programs](https://ap.vsk.gov.in/api/ingestion/national\_programs)

<figure><img src="https://lh7-us.googleusercontent.com/yi4ruRGMYzZmwQl3uuHuaR1vDYyoNHTOel2CeYCVAZv0QxD6NJfx-yPQC-FxVFiQ_AO4lPrZBC3CcTzDtsWCjNfISDtyqyebEYhGhveoJlHywqkIOmAdDurYSuVZHH4XZAFFW6WGDLRuhjzb96GrlEE" alt=""><figcaption></figcaption></figure>



* We need to ingest only three programs (pgi,diksha,nishtha)data through API. The other three programs automatically pull the data from the NVSK server.
* For above point we need to upload (PGI, DIKSHA, NISHTHA) three programs schema and ingest the raw files to the aws emission bucket.
* Then we can schedule the below mentioned processor groups one by one by using schedule API as shown in the below screenshot
  * &#x20;Run\_adapters
  * data\_moving\_local

<figure><img src="https://lh7-us.googleusercontent.com/zapTPsHQg6EefoQCqQXBlq_60teMoNJUUVxic0Eid-e0ZyDkiwCEybVxuYxkfGzLcHryQUn_ym-j4luaFtClIt2ltyM-WZg3JHbZYxawTH8IZe5wGFQzbRvhuxoKgfpXG_A_y7cPorHtcMTNw7f_qX8" alt=""><figcaption></figcaption></figure>

\


<figure><img src="https://lh7-us.googleusercontent.com/yt1gP3Hth9oGdUXh5axcg4O7eADAa8QawRoOSkqWrZOL_ABqZrdD4rPUlVjYOae8CfJfHear74qVIglwBIDkgUYTRMDyvM3UOnf79p5DfTFlTubYzlloCtKsVSbwkWVK4ORGv2cDFDawUgm6n7lggQQ" alt=""><figcaption></figcaption></figure>

* After that you can schedule the one by one program by using schedule API as mentioned in the below screenshot.

&#x20;      Body:

&#x20;             {

&#x20;                "processor\_group\_name": "ingest\_data",

&#x20;                 "scheduled\_at": "0 31 14 \* \* ?",

&#x20;                 "program\_name": "nishtha"

&#x20;              }

\


<figure><img src="https://lh7-us.googleusercontent.com/Ypr5SVcSJ3AuGVFhCvt_gGT98ocMPawzN8BqbG7VUJ2eamsy4lyTNPJscBz8zIv_fJYB7UpfWEUMxgDpbQRbyosTfT1nyluht3bgkhQ1Zdw0gzAz74-hATVpBIChPVLrGRRzORaVPOri8hXxvooyWhA" alt=""><figcaption></figcaption></figure>

* Check the visualization in the UI dashboard. As shown in the below screenshot.

<figure><img src="https://lh7-us.googleusercontent.com/HeOpzhfh3wX3H-ptYtWDKTD3HzY3DIRmZMCxJLts9eSFCBdYsOeaeqYcnLwd3OgGodMXxb4xJA-r-FsqpDdP3bOtf2IJpnNqoy40zOthR8j5FJPNkRZ4V122_8HO7tJnu6kOKogETyhB7NHrA57cbMs" alt=""><figcaption></figcaption></figure>

\

# AWS Installation

IAM user and Role creation for S3 connectivity (AWS)

An AWS Identity and Access Management (IAM) user is an entity that is created in AWS to represent the person or application that uses it to interact with AWS. A user in AWS contains a name and credentials. An IAM user with administrator permissions is different from the AWS account root user. One has to create an IAM user with a supported role to provide the connectivity between EC2 and S3. The role should have list, read, and write permissions.

**Primary Steps:**

**Step  1:** A SSL certificate must be uploaded if you are opting for the public mode of installation where you want to access cQube using a public API endpoint.&#x20;

**Note :** You can ignore the above step if you are opting for localhost installation (single desktop).



**Step 2:** Clone the cqube-devops repository using following command

&#x20;                **git clone** [**https://github.com/Sunbird-cQube/cqube-devops.git**](https://github.com/Sunbird-cQube/cqube-devops.git)    &#x20;

<figure><img src="https://lh5.googleusercontent.com/UjoUhbupTuK24BEdYb_SXBRsE-rLCtD5f7uk9dg33z-REsD-teRvFTK--lV-UVnM_YtHhnFqEljUAhfC2fH2Htx6u213g_mcnV6X0HcXm_UapobOFOwwgOPj1BLDfAO_ugB0JGd3n1vxGfkjvpIwgmc" alt=""><figcaption></figcaption></figure>

**Step 3:** Navigate to the directory where cQube is cloned or downloaded and checkout to the desired branch

&#x20;                       **cd cqube-devops/**&#x20;

&#x20;                        **git checkout release-v5.0.5(latest release branch)**

<figure><img src="https://lh5.googleusercontent.com/E_OgyUFO8XlcHce_ewm--W_fs3kEi8pACeSncu30SlO09NG7G3yrfU8LiGjMieVCHsQAUuRDxtrPlrXXyocoJ4hwNBYKYX3U1Zwr994d6znC2rOt6neOX3VicuFB16R21NKSG7s2iBQBloiYTqF4MWo" alt=""><figcaption></figcaption></figure>

**Step 4:** Navigate to the directory cqube-devops/ansible/ssl\_certificates.

&#x20;                     **Copy the certificate and private key inside this cqube-                   devops/ansible/ssl\_certificates folder.**

<figure><img src="https://lh4.googleusercontent.com/Wr-sri7bGZATnpBooUYO6vDQJdLZQh8pi3mDhhm9lQzAkacsn_FLBwAa1_8oiVG0BRq81msG3QsBRa79l_KL7BN-Vs8S-JgKItFAcTN4H7_V9rdieto5B4AQPXdtqdtInbZ212f7uyNS_7TBQYUo5Ss" alt=""><figcaption></figcaption></figure>

<figure><img src="https://lh3.googleusercontent.com/EVMpEfmKC-N3SyOIP-F0-HkJaoo2an1hA-8Nq-UKguuR5C19k-dwqz8WdFE3YwGVjvDI6WvhZmS25O0vE1XxLjTiIJheMVL3LhXePgLmalVQWViV6Nfp6tdT85-33K3NzIV0sQngPp1-GDLgqV19044" alt=""><figcaption></figcaption></figure>

**Step 5 :** If you are opting to pull the data from the NVSK instance, then make sure to upload the dimension files. If you do not want to pull the data, then you can ignore this step. (Applicable if you choose access type VSK).

If you are opting to pull data from an NVSK instance, then make sure to copy the dimension files inside cqube-devops/ansible/dimension\_files

<figure><img src="https://lh5.googleusercontent.com/ZCuFEZA2V1fU9pdBSa2-6tLaGYTpebXzmepl3yYMOtOKLnYDXAYX6bGa0bkrTrZQacyc9Ir8QDd6gZ7-RE6tf_4cYdiLDavdskNfYZK4mXJPV69Z51hQ-68mNUqVo87L4kvjQ--QNryFwRpmAGJX8qQ" alt=""><figcaption></figcaption></figure>

<figure><img src="https://lh6.googleusercontent.com/TiNfl0zmceZ2BXtfHPo1KqZPcwaNjo_4aIqZjoOuZkFRoIO-DlAUnFrKGWosGtoFLLI9gd0U_aSPs16JbGUBkymm0keQKORBnL3GHrkeVOzEOhRg8JIm9QcMUh_3Gign_g6G4ojoI-3eCj8bIvW4N64" alt=""><figcaption></figcaption></figure>

Once all the primary steps of uploading SSL certificates and dimensions are done, we can check prerequisites using the script.

**Navigate back to cqube-devops directory**

**Step 6**: Give the following permissions to the pre\_requisites.sh file

&#x20;          **sudo chmod u+x shell\_scripts/pre\_requisites.sh**

**Step 7:** Run the pre\_requisites script with non root user with sudo privileges

&#x20;                 **sudo ./shell\_scripts/pre\_requisites.sh**

<figure><img src="https://lh6.googleusercontent.com/UZrSv7qjKeHyKyH9c3q6qB-LhvQ_FhlV2um3kzPLwsRYF_-UHbSRdqHtJHNf77BWIYad5nI2pDiv2-_96aGv6EjXDHFkUWW-dy7y4BVCcTnPO_k6bm_XqBCdRNOpMGoVSICk7t5TTbNleobiPsPqDTQ" alt=""><figcaption></figcaption></figure>

**Step 8 :** When steps 6 and 7 are done, you will see the feedback from status checks.

**Step 9:** Go through the feedback provided, and if you find any issues in red resolve them by following the hints provided. If everything is good then proceed with cqube deployment.

#### Deployment Process

**Step 1:** Connect to the cqube AWS ec2 instance

**For linux and macOS:**

* Download the .pem file which is generated while creating the EC2 instance
* Open the terminal and navigate to the folder where .pem file has been downloaded
* Then give the read permission to the .pem file using following command

&#x20;                       **sudo chmod 400 \<aws.pem>**

* Use the following command to connect to the instance

**ssh -i \<path\_to\_the\_pem\_file>  \<user\_name>@\<public\_ip\_of\_the\_instance>**

**For windows:**

* Download the .pem file which is generated while creating the EC2 instance
* Use puttygen to connect to the instance.
*   Refer following link to use puttyGen for connecting.

    [https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/putty.html](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/putty.html)

**Step 2:** Refer to the prerequisites checklist section before starting the cqube deployment.-[ Link ](https://app.gitbook.com/o/-Mi9QwJlsfb7xuxTBc0J/s/-Miy6UN-HyTKGo2Sjcky/\~/changes/326/get-started-on-cqube/prerequisites-checklist)

**Step 3:** Navigate to cqube-devops directory and give the executable permissions to the install.sh file

&#x20;                         **sudo chmod u+x install.sh**

**Step 4:** Install cQube with non root user with sudo privileges

&#x20;                     **sudo ./install.sh**

<figure><img src="https://lh3.googleusercontent.com/vooad-dKteZvHc2BAzhdpUKpbtQPVwhSkwsM44nkMQo8eb13orfphwl1NCQ87lG1ojxKjBclOlLQA9qjQUHhBFMyEYRGK96XdGnkniIvbz6SticcwZAM7M_f1wfHZ7luA7C0OYKn3zCQdFWwNdHF6P8" alt=""><figcaption></figcaption></figure>

Install.sh file contains a shell script where it will run shell scripts and ansible-playbook to setup the cQube

**Step 5:** Generation of domain specific configuration file - Please refer to the Hints provided and enter the values accordingly.

* access\_type: Enter VSK, NVSK, or others.

&#x20;           a) VSK: To set up VSK for a state

&#x20;            b) NVSK: To setup a cQube for the nation

&#x20;            c) Others: To set up cQube for other purposes.

* state\_name: Enter the required state code by referring to the state list provided (this variable needs to be filled if you are opting for access\_type as VSK; otherwise, it will get filled as NA by default).
* loginpage\_status: Enter true if you want to enable the login screen for the CQUBE instance. Otherwise, enter false.
* data\_pull\_status: Enter true if you want to pull data from an NVSK instance, or else enter false. (You need to fill this variable if you have selected access\_type as VSK; otherwise,  it will get auto-filled with NA.)
* nvsk\_api\_endpoint: Enter the NVSK instance api endpoint if you selected true for data\_pull\_status; otherwise,  it will get autofilled with NA.

Once all the above variables are filled, you get prompted with a preview of the domain-specific config file. Review the entered variables. If everything is correct, then type ‘no’ and proceed further, or else enter ‘yes’ and re-enter the variables correctly.

<figure><img src="https://lh5.googleusercontent.com/pryTY65YLkTnovHGmfeSD-R7kI9iJ1i_HR-nsOlhNXbT0JGYB8jmcn4Xj-kyddvK0jj3xBV0Ydie8HVkzzuyGgxAxOI2g8MRzgRRBTwrDeHod45HSW_HpYGsurANuYOkrJ56gbJjRI4Uvn-oTgYtMqU" alt=""><figcaption></figcaption></figure>

**Step 6**: Generation of a generic config file: refer to the hints provided and enter the config file accordingly.

* mode\_of\_installation: Enter public as you have opted for setting up cqube in AWS. (Possible values are public and localhost.)
* storage\_type: Enter storage type as AWS. (Possible values are aws, azure, oracle, and local.)
* api\_end\_point: Enter the url in which the clock is to be configured.
* nginx\_cert\_file: Enter the name of the SSL certificate file that you uploaded in the SSL\_certificates folder.
* nginx\_key\_file: Enter the name of the private key file that you uploaded in the ssl\_certificates folder.
* Db\_credentials: You will be prompted with default database credentials. If you want to continue with the same, enter no; otherwise, enter yes and proceed to enter your database credentials.
  * db\_user\_name ( Enter the postgres database username )&#x20;
  * db\_name ( Enter the postgres database name )
  * db\_password ( Enter the postgres password )

<figure><img src="https://lh3.googleusercontent.com/dzP6FFmWaLIz8QwOHtXZy9LYg7ZR7afq33HJIQq7wLJDoRiScABiV8IvKX4Ewih_X3X_iLBrUYCle62zEW-D2pN23Fvj3nSaHX83D-5f-cqKjrJ-geV_4jNxGNqozNrGxNXkPVIa2A0cLB46_KX91Rk" alt=""><figcaption></figcaption></figure>

* Readonly\_db\_credentials: You will be prompted with default read-only database credentials. If you want to continue with the same, enter no; otherwise, enter yes and proceed to enter your read-only database credentials.

1. read\_only\_db\_user\_name ( Enter the postgres database username )&#x20;
2. read\_only\_db\_password ( Enter the postgres password )

<figure><img src="https://lh6.googleusercontent.com/bSMlVxvQRvTqsw2UbFRIOb28Ckk4eTN1_eMgqcXW-asrT5ChbL3Gy61PYQqEWYumIHv0mbkK-ERe-TxpivLHJeH_-2VIsy_dMa2goGWUTqr1f6fd8oUZWxnjefAY9cw5FrQH4e1lBt5AWbRzOlyKEkA" alt=""><figcaption></figcaption></figure>

* Keycloak\_credentials: You will be prompted with the default keycloak admin dashboard credentials. If you want to continue with the same, enter no; otherwise, enter yes and proceed to enter your keycloak credentials.

1. Keycloak\_adm\_name (Enter the keycloak admin name eg: admin)
2. Keycloak\_adm\_password (enter the keycloak admin password eg: Admin@123)

<figure><img src="https://lh5.googleusercontent.com/-XIpmDt1ddcx42pw-uQFjkPhJBlWW-GJfxRAmnwAtNK1-PNuHW3_hPbUDz_2LPdLzXk5-2gDAFD5uZhQejSKJTfg3rnG9l99UZecMvmFZx4JYZfNTtC5sYWME3XwhmY52r1NvWS5z043ILqwOK5BUHo" alt=""><figcaption></figcaption></figure>

**Step 7:** Once the config file is generated, a preview of the config file is displayed, followed by a question where the user gets the option to re-enter the configuration values by choosing ‘yes’. If option ‘no’ is selected, then the install.sh moves to the next section.

<figure><img src="https://lh6.googleusercontent.com/0FhGW3sUZR1vXIx9wjz5bCislTL6J8nHe0q9v8oVeLFXs_ppZEwmAo7ABlwyCI7mcsOCMvZnjJQNsfIH4C8Y_psT-ZGuCM904kQT4U16vBIwQjkTRP9QdLQ-Mc-ERXmozrcZA_573dkCQPOLSUQw7W4" alt=""><figcaption></figcaption></figure>

**Step 8:** Generation of storage config file: Refer to the hints provided below and enter the config file accordingly.

* aws\_access\_key: Enter the aws s3 access key to access the s3 bucket.
* aws\_secret\_key: Enter the aws s3 secret key to access the s3 bucket.
* s3\_bucket: By default, an s3 bucket is selected. If you get an error because the bucket already exists, type a unique bucket name and proceed further.

**Step 9:**  A preview of the program\_selector.yml file is displayed, followed by a question where the user gets an option to enable or disable the programs by choosing 'yes'. If option 'no' is selected, then the install.sh moves to the next section.

1. &#x20;If access\_type is selected as VSK, the following programs will be displayed: by default, all programs are selected, and the programs are publicly visible.

<figure><img src="https://lh3.googleusercontent.com/-zZmhvyhBxS-jAPpN14zsnMsSsdWsz-6aBIO1Tfr3lu-QIVy4pTbCo-b6Bt4CJ77r8JpY4XERl2glridREEto6FUyT5RgJO381SVrUQ-bLnYuXNWfykALSrGbwfWavyNLSWQquWnMa0oisuurynepN4" alt=""><figcaption></figcaption></figure>

**Note:** If you are willing to select the programs, type yes, select the programs you want, and enter public or private for each program to enable or disable the login screen for programs (follow the hints provided).

2. If access\_type is selected as NVSK, the following programs will be displayed: By default, all programs are selected, and the programs are publicly visible.

<figure><img src="https://lh3.googleusercontent.com/7vvQny2i_KaBOYET4imE9Xjuclhbg_ckqFiX7zY3soM9SmvWmMahSaIV5CyiLlD-AcIIwPWu4aojqkBeRt9pMiQL8i0_jb5-FgzwYIHK8DrbU8SdWfJQwMm3EbO5Ujq0rLq7xuaRHmUUKSostQ5tRUA" alt=""><figcaption></figcaption></figure>

**Note:** If you are willing to select the programs, type yes, select the programs you want, and enter public or private for each program to enable or disable the login screen for programs (follow the hints provided).

**Step 10:** Once all the configuration files are generated, the script moves further to clone the cQube microservice repositories and deploy cQube

**Step 11:** If you selected data\_pull\_status as true, then you will see the data pulling APIs where the data gets pulled from the NVSK instance and processed in the VSK cQube Once installation is done, we need to wait 20 minutes to visualize the data on the CQUBE dashboard.

**Step 12:** Once the installation is completed, you will be prompted with the following messages and required reference urls:

\


**cQube Installed Successfully**

<figure><img src="https://lh6.googleusercontent.com/LCFZH9xuBbl55esbiqJXn-uvnFec2JcAobp3lzAezKHaJzgTxkP2zDgnd8iDysdqO1Z5aog7kCD14B4uOpFo3bSW9OxLDFsa2Dl0BiZyOuT-16tEW3GEHIpsYAIrprC_6hDQwfe1Ci1eVjPQT57faKU" alt=""><figcaption></figcaption></figure>

\


\
\

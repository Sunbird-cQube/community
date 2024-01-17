# Azure  Installation

IAM user and Role creation for AZURE Storage Blob Container connectivity

An AZURE Identity and Access Management (IAM) user is an entity that is created in AZURE to represent the person or application that uses it to interact with AZURE. A user in Azure contains a name and credentials. An IAM user with administrator permissions is different from the AWS account root user. One has to create an IAM user with a supported role to provide the connectivity between azure VM and blob container. The role should have list, read and write permissions.

**Primary Steps:**

**Step  1:** A SSL certificate must be uploaded if you are opting for the public mode of installation where you want to access cQube using a public API endpoint.&#x20;

**Note :** You can ignore the above step if you are opting for localhost installation (single desktop).

**Step 2:** Clone the cqube-devops repository using following command

&#x20;                **git clone** [**https://github.com/Sunbird-cQube/cqube-devops.git**](https://github.com/Sunbird-cQube/cqube-devops.git)    &#x20;

<figure><img src="../../.gitbook/assets/image (49).png" alt=""><figcaption></figcaption></figure>

**Step 3:** Navigate to the directory where cQube is cloned or downloaded and checkout to the desired branch

&#x20;                       **cd cqube-devops/**&#x20;

&#x20;                        **git checkout release-v5.0.5(latest release branch)**

<figure><img src="../../.gitbook/assets/image (51).png" alt=""><figcaption></figcaption></figure>

**Step 4:** Navigate to the directory cqube-devops/ansible/ssl\_certificates.

&#x20;                     **Copy the certificate and private key inside this cqube-                   devops/ansible/ssl\_certificates folder.**

<figure><img src="../../.gitbook/assets/image (52).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (53).png" alt=""><figcaption></figcaption></figure>

**Step 5 :** If you are opting to pull the data from the NVSK instance, then make sure to upload the dimension files. If you do not want to pull the data, then you can ignore this step. (Applicable if you choose access type VSK).

If you are opting to pull data from an NVSK instance, then make sure to copy the dimension files inside cqube-devops/ansible/dimension\_files

<figure><img src="../../.gitbook/assets/image (54).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (55).png" alt=""><figcaption></figcaption></figure>

Once all the primary steps of uploading SSL certificates and dimensions are done, we can check prerequisites using the script.

**Navigate back to cqube-devops directory**

**Step 6**: Give the following permissions to the pre\_requisites.sh file

&#x20;          **sudo chmod u+x shell\_scripts/pre\_requisites.sh**

**Step 7:** Run the pre\_requisites script with non root user with sudo privileges

&#x20;                 **sudo ./shell\_scripts/pre\_requisites.sh**

<figure><img src="../../.gitbook/assets/image (57).png" alt=""><figcaption></figcaption></figure>

**Step 8 :** When steps 6 and 7 are done, you will see the feedback from status checks.

**Step 9:** Go through the feedback provided, and if you find any issues in red resolve them by following the hints provided. If everything is good then proceed with cqube deployment.

#### Deployment Process

**Step 1:** Connect to the cqube Azure ec2 instance

**For linux and macOS:**

* Download the .pem file which is generated while creating the EC2 instance
* Open the terminal and navigate to the folder where .pem file has been downloaded
* Then give the read permission to the .pem file using following command

&#x20;                       **sudo chmod 400 \<aws.pem>**

* Use the following command to connect to the instance

**ssh -i \<path\_to\_the\_pem\_file>  \<user\_name>@\<public\_ip\_of\_the\_instance>**

**Ex:** ssh -i poc\_key.pem -o ServerAliveInterval=60 ubuntu@13.200.12.31

**For windows:**

* Download the .pem file which is generated while creating the EC2 instance
* Use puttygen to connect to the instance.
*   Refer following link to use puttyGen for connecting.



**Step 2:** Refer to the prerequisites checklist section before starting the cqube deployment.-[ Link ](https://app.gitbook.com/o/-Mi9QwJlsfb7xuxTBc0J/s/-Miy6UN-HyTKGo2Sjcky/\~/changes/326/get-started-on-cqube/prerequisites-checklist)

**Step 3:** Navigate to cqube-devops directory and give the executable permissions to the install.sh file

&#x20;                      **sudo chmod u+x install.sh**

**Step 4:** Install cQube with non root user with sudo privileges

&#x20;                     **sudo ./install.sh**

<figure><img src="https://lh7-us.googleusercontent.com/B5xQFKfEHA_Qk0tXqgJRS7aRd0CJPo24wIf64SLosEEX8l_TDkjEEGJzgLThOxJ4JuZynMZNiNJUvYXzkTKApwg8AfcKWiJD-NK0jhkh4RrRN0UrornptmmOW8h7mlA10gyFe9Vq6EWbn0CdHdZh5yA" alt=""><figcaption></figcaption></figure>

Install.sh file contains a shell script where it will run shell scripts and ansible-playbook to setup the cQube

**Step 5:** Generation of domain specific configuration file - Please refer to the Hints provided and enter the values accordingly.

* access\_type: Enter VSK, NVSK, or others.

&#x20;           a) VSK: To set up VSK for a state

&#x20;            b) NVSK: To establish a nationwide cQube deployment

&#x20;            c) Others: To set up cQube for other purposes.

* state\_name: Enter the required state code by referring to the state list provided (this variable needs to be filled if you are opting for access\_type as VSK; otherwise, it will get filled as NA by default).
* loginpage\_status: Enter true if you want to enable the login screen for the CQUBE instance. Otherwise, enter false.
* data\_pull\_status: Enter true if you want to pull data from an NVSK instance, or else enter false. (You need to fill this variable if you have selected access\_type as VSK; otherwise,  it will get auto-filled with NA.)
* nvsk\_api\_endpoint: Enter the NVSK instance api endpoint if you selected true for data\_pull\_status; otherwise,  it will get autofilled with NA.

Once all the above variables are filled, you get prompted with a preview of the domain-specific config file. Review the entered variables. If everything is correct, then type ‘no’ and proceed further, or else enter ‘yes’ and re-enter the variables correctly.

<figure><img src="../../.gitbook/assets/image (58).png" alt=""><figcaption></figcaption></figure>

**Step 6**: Generation of a generic config file: refer to the hints provided and enter the config file accordingly.

* mode\_of\_installation: Enter public as you have opted for setting up cqube in AWS. (Possible values are public and localhost.)
* storage\_type: Enter storage type as AWS. (Possible values are aws, azure, oracle, and local.)
* api\_end\_point: Enter the url in which the clock is to be configured.
* nginx\_cert\_file: Enter the name of the SSL certificate file that you uploaded in the SSL\_certificates folder.
* nginx\_key\_file: Enter the name of the private key file that you uploaded in the ssl\_certificates folder.

<figure><img src="https://lh7-us.googleusercontent.com/PZ2SYsWY8Q3SxJsGdExR5yC2sT3hqGy74XKylutJzEFGx1o6OKhQ4Z8ut1wvRnBIzt0RiOMSwp3fy2P3GrEG2vpD6JpokMu6UrkBB9rmpeDLRi0qSUBab812KDlVxvhoK4HPK9Lvm9Hcfn-fgfeBdqw" alt=""><figcaption></figcaption></figure>

* Db\_credentials: You will be prompted with default database credentials. If you want to continue with the same, enter no; otherwise, enter yes and proceed to enter your database credentials.
  * db\_user\_name ( Enter the postgres database username )&#x20;
  * db\_name ( Enter the postgres database name )
  * db\_password ( Enter the postgres password )

<figure><img src="https://lh3.googleusercontent.com/dzP6FFmWaLIz8QwOHtXZy9LYg7ZR7afq33HJIQq7wLJDoRiScABiV8IvKX4Ewih_X3X_iLBrUYCle62zEW-D2pN23Fvj3nSaHX83D-5f-cqKjrJ-geV_4jNxGNqozNrGxNXkPVIa2A0cLB46_KX91Rk" alt=""><figcaption></figcaption></figure>

* &#x20;Readonly\_db\_credentials: You will be prompted with default read-only database credentials. If you want to continue with the same, enter no; otherwise, enter yes and proceed to enter your read-only database credentials.

1. read\_only\_db\_user\_name ( Enter the postgres database username )&#x20;
2. read\_only\_db\_password ( Enter the postgres password )

<figure><img src="../../.gitbook/assets/image (59).png" alt=""><figcaption></figcaption></figure>

* Keycloak\_credentials: You will be prompted with the default keycloak admin dashboard credentials. If you want to continue with the same, enter no; otherwise, enter yes and proceed to enter your keycloak credentials.

1. Keycloak\_adm\_name (Enter the keycloak admin name eg: admin)
2. Keycloak\_adm\_password (enter the keycloak admin password eg: Admin@123)

<figure><img src="../../.gitbook/assets/image (60).png" alt=""><figcaption></figcaption></figure>

**Step 7:** Once the config file is generated, a preview of the config file is displayed, followed by a question where the user gets the option to re-enter the configuration values by choosing ‘yes’. If option ‘no’ is selected, then the install.sh moves to the next section.

**Step 8:** Generation of storage config file: Refer to the hints provided below and enter the config file accordingly.

* Azure Container String: Enter the container string&#x20;
* azure\_account\_key: Enter the azure account key to access the bucket.
* aws\_account-name: Enter the azure account name to access the bucket.
* azure blob container name : Enter unique azure blob container name.

**Step 9:**  A preview of the program\_selector.yml file is displayed, followed by a question where the user gets an option to enable or disable the programs by choosing 'yes'. If option 'no' is selected, then the install.sh moves to the next section.

1. &#x20;If access\_type is selected as VSK, the following programs will be displayed: by default, all programs are selected, and the programs are publicly visible.

<figure><img src="../../.gitbook/assets/image (64).png" alt=""><figcaption></figcaption></figure>

**Note:** If you are willing to select the programs, type yes, select the programs you want, and enter public or private for each program to enable or disable the login screen for programs (follow the hints provided).

2. If access\_type is selected as NVSK, the following programs will be displayed: By default, all programs are selected, and the programs are publicly visible.

<figure><img src="../../.gitbook/assets/image (65).png" alt=""><figcaption></figcaption></figure>

**Note:** If you are willing to select the programs, type yes, select the programs you want, and enter public or private for each program to enable or disable the login screen for programs (follow the hints provided).

**Step 10:** Once all the configuration files are generated, the script moves further to clone the cQube microservice repositories and deploy cQube

**Step 11:** If you selected data\_pull\_status as true, then you will see the data pulling APIs where the data gets pulled from the NVSK instance and processed in the VSK cQube. Once installation is done, we need to wait 20 minutes to visualize the data on the cQube dashboard.

**Step 12:** Once the installation is completed, you will be prompted with the following messages and required reference urls:

**(Note: The installation process is expected to take approximately 30-40 minutes.)**

**cQube Installed Successfully**

<figure><img src="../../.gitbook/assets/image (66).png" alt=""><figcaption></figcaption></figure>




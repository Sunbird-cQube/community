# Oracle Installation

Instance Setup in Oracle Cloud:

**Step 1:** Create an instance with Ubuntu 22.04(Oracle Linux ) image, 2 core OCPU, and 16GB RAM

<figure><img src="https://lh7-us.googleusercontent.com/txzf_6TL9dajtvyVB_ctLclivrhHamVdVtR--XUqSy34FR8Pjgi9261dPSVMuSSudFJs7el5KRnf49Oi6TPEJr-CnBOCCS3NtzC2NLgfXCAVslSPFTFfVicCTLL3VOB-nqf2kzqnmqUrdeyX2MXHa9s" alt=""><figcaption></figcaption></figure>

**Step 2:** Download the private key file associated with the instance.

<figure><img src="https://lh7-us.googleusercontent.com/rumaDQ75o8ycg8M-7MZx9QGIjKe2UDzUhKOblKWKbgBjV9NUbnJiq_YtBf9VgYxVN1Yb1pnhc6_fRVg82I0JLGmCkuqFZYClAWgYT2gTvSwPv5EWMxrO6yRSlsX7-8P2O2IFUHK193KzE3TwGqyGwWg" alt=""><figcaption></figcaption></figure>

**Step 3:** Create a Storage Bucket

Go to the Oracle Cloud console and create a bucket with default configurations.

<figure><img src="https://lh7-us.googleusercontent.com/NNIOHuVaRTkKwK3aIju19DK6e_W6iTM14-9vUogiuLn0i3fq1jnBLjqGyBizl84Q0S429bon7WHHcH7WyZZ6M617tLm-FT_Z4fcxjDU24DzRtVoERNEybsDJcd6uT2znUUDNZrKRu-7q5GU-DceRsTQ" alt=""><figcaption></figcaption></figure>

**Step 4:** Generate Config File in Oracle Cloud

Login to the Oracle Cloud account and navigate to the profile section

<figure><img src="https://lh7-us.googleusercontent.com/t69xbC99kuUkrTGbCeFzFu8-HDKbos0wqnLaA-mR6q_5P4D2OsT3h2IWlK70tAMETTsCWb5X6ern8tdgFUTofuGHubXh5ibsV7CGaKjxPIuAG3wpHgEmy6_g9PUCipbb_jPfibHgaQXiqUxb-0vDIN8" alt=""><figcaption></figcaption></figure>

Generate a new key pair in the API keys section and download the private key file

<figure><img src="https://lh7-us.googleusercontent.com/czRkrDc0W3jXJwLMTJrHa9O_68ajQJxb0F5eRP4tHC2e0sqV1-brMOjDyyFCVxUd2WGehfGqJb5vOvgNCCV4uAVOE638HyW4S-8Qp-g3Wcaccgm9TnFx1YGGJp86m9l7p2mVdgOQ34abutwxEobOioI" alt=""><figcaption></figcaption></figure>

Copy the content of the configuration file for future use\


<figure><img src="https://lh7-us.googleusercontent.com/mMxrmYwcg15Q7ho7u2ouN4MBfSY11B8cAv0rWOzuMulfgFnxy2OFIMR4zMyu0kgvzQSfMzXcXpoj2s4UdZ97WA_XDqyqCa9yu6NTp8HreYs_KYmXhFHjcCBDp3mMVlu7IWjQJkaWH0VjzFSt0dILkd8" alt=""><figcaption></figcaption></figure>

**Upload the API Key File to the cQube Server:**

* Connect to the cQube server using SSH.
* Copy the Oracle API private key file to the server using the command:

&#x20;                    scp -i \<pem\_file\_of\_server> \<private\_key\_of\_oracle\_api> ubuntu@\<ip>:\~/

* Switch to the root user:

&#x20;                     sudo su

* Move the private key file to the .oci directory:

&#x20;                     mkdir /root/.oci && cd /root/.oci&#x20;

&#x20;                     mv /home/\<system\_user\_name>/\<private\_key\_of\_oracle\_api> .

* Verify the presence of the file in the current directory:

&#x20;                      ls -ltr

* Exit from the root user and continue with the cQube installation.



**Instructions to fill the Oracle config variables during installation:**

* Copy the config file to the desired location (/root/.oci/config).
* Open the config file and replace the following placeholders with actual values from the API key config file:

&#x20;                   User OCID

&#x20;                   Tenancy OCID

&#x20;                   Region (by index or name)

* Decide whether to generate a new API Signing RSA key pair.

&#x20;                 If declining, provide the path to an existing key.

* Specify the location for the API Signing private key file               (/root/.oci/\<private\_key\_of\_oracle\_api>).

**Primary Steps:**

**Step  1:** A SSL certificate must be uploaded if you are opting for the public mode of installation where you want to access cQube using a public API endpoint.&#x20;

**Note :** You can ignore the above step if you are opting for localhost installation (single desktop).

Connect to the cqube Oracle instance

&#x20;       ssh -i \<path\_to\_the\_pem\_file> \<user\_name>@\<public\_ip\_of\_the\_instance>

&#x20;       Ex: ssh -i poc\_key.pem -o ServerAliveInterval=60 ubuntu@13.200.12.31&#x20;



**Step 2:** Clone the cqube-devops repository using following command

&#x20;                **git clone** [**https://github.com/Sunbird-cQube/cqube-devops.git**](https://github.com/Sunbird-cQube/cqube-devops.git)    &#x20;

\


<figure><img src="../../.gitbook/assets/image (68).png" alt=""><figcaption></figcaption></figure>

**Step 3:** Navigate to the directory where cQube is cloned or downloaded and checkout to the desired branch

&#x20;                       **cd cqube-devops/**&#x20;

&#x20;                        **git checkout release-v5.0.5(latest release branch)**

<figure><img src="../../.gitbook/assets/image (69).png" alt=""><figcaption></figcaption></figure>

**Step 4:** Navigate to the directory cqube-devops/ansible/ssl\_certificates.

&#x20;                     **Copy the certificate and private key inside this cqube-                   devops/ansible/ssl\_certificates folder.**

<figure><img src="../../.gitbook/assets/image (70).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (71).png" alt=""><figcaption></figcaption></figure>

**Step 5 :** If you are opting to pull the data from the NVSK instance, then make sure to upload the dimension files. If you do not want to pull the data, then you can ignore this step. (Applicable if you choose access type VSK).

If you are opting to pull data from an NVSK instance, then make sure to copy the dimension files inside cqube-devops/ansible/dimension\_files

<figure><img src="../../.gitbook/assets/image (72).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (73).png" alt=""><figcaption></figcaption></figure>

Once all the primary steps of uploading SSL certificates and dimensions are done, we can check prerequisites using the script.

**Navigate back to cqube-devops directory**

**Step 6**: Give the following permissions to the pre\_requisites.sh file

&#x20;          **sudo chmod u+x shell\_scripts/pre\_requisites.sh**

**Step 7:** Run the pre\_requisites script with non root user with sudo privileges

&#x20;                 **sudo ./shell\_scripts/pre\_requisites.sh**

<figure><img src="../../.gitbook/assets/image (74).png" alt=""><figcaption></figcaption></figure>

**Step 8 :** When steps 6 and 7 are done, you will see the feedback from status checks.

**Step 9:** Go through the feedback provided, and if you find any issues in red resolve them by following the hints provided. If everything is good then proceed with cqube deployment.

**Deployment  Process:**&#x20;

**Step 1:**Refer to the prerequisites checklist section before starting the cqube deployment.-[ Link ](https://app.gitbook.com/o/-Mi9QwJlsfb7xuxTBc0J/s/-Miy6UN-HyTKGo2Sjcky/\~/changes/326/get-started-on-cqube/prerequisites-checklist)

**Step 2:** Navigate to cqube-devops directory and give the executable permissions to the install.sh file

&#x20;                         **sudo chmod u+x install.sh**

**Step 3:** Install cQube with non root user with sudo privileges

&#x20;                     **sudo ./install.sh**

<figure><img src="../../.gitbook/assets/image (75).png" alt=""><figcaption></figcaption></figure>

Install.sh file contains a shell script where it will run shell scripts and ansible-playbook to setup the cQube

**Step 4:** Generation of domain specific configuration file - Please refer to the Hints provided and enter the values accordingly.

* access\_type: Enter VSK, NVSK, or others.

&#x20;           a) VSK: To set up VSK for a state

&#x20;            b) NVSK: To establish a nationwide cQube deployment

&#x20;                   c) Others: To set up cQube for other purposes.

* state\_name: Enter the required state code by referring to the state list provided (this variable needs to be filled if you are opting for access\_type as VSK; otherwise, it will get filled as NA by default).
* loginpage\_status: Enter true if you want to enable the login screen for the CQUBE instance. Otherwise, enter false.
* data\_pull\_status: Enter true if you want to pull data from an NVSK instance, or else enter false. (You need to fill this variable if you have selected access\_type as VSK; otherwise,  it will get auto-filled with NA.)
* nvsk\_api\_endpoint: Enter the NVSK instance api endpoint if you selected true for data\_pull\_status; otherwise,  it will get autofilled with NA.

Once all the above variables are filled, you get prompted with a preview of the domain-specific config file. Review the entered variables. If everything is correct, then type ‘no’ and proceed further, or else enter ‘yes’ and re-enter the variables correctly.

<figure><img src="https://lh7-us.googleusercontent.com/MDlCBoqU-lr2GHTIzCZ1xVfcTgDFgE7JUhyQcnZXofCDeawg2c0sW9dhLDj-AU_v3-P1hYYykt1UzggBu5Fahksjq61Fc6jptbmodTxPqy-70Xtyy5vTbkY_yj5LAdTCQ8RXqsXESc6n_zd0aq8mTLM" alt=""><figcaption></figcaption></figure>

**Step 5:** Generation of a generic config file: refer to the hints provided and enter the config file accordingly.

* mode\_of\_installation: Enter public as you have opted for setting up cqube in AWS. (Possible values are public and localhost.)
* storage\_type: Enter storage type as oracle. (Possible values are aws, azure, oracle, and local.)
* api\_end\_point: Enter the url in which the clock is to be configured.
* nginx\_cert\_file: Enter the name of the SSL certificate file that you uploaded in the SSL\_certificates folder.
*   nginx\_key\_file: Enter the name of the private key file that you uploaded in the ssl\_certificates folder.

    *   Db\_credentials: You will be prompted with default database credentials. If you want to continue with the same, enter no; otherwise, enter yes and proceed to enter your database credentials.

        db\_user\_name ( Enter the postgres database username )&#x20;

        db\_name ( Enter the postgres database name )

        db\_password ( Enter the postgres password )



        <figure><img src="https://lh7-us.googleusercontent.com/RHH2JTaOxXFWkSxPeqCHe25m5LjrdZd6otIttzZQNC97yA90ayMhDfEZLI-hvH9H2LueYbRSrnzM0s9EaSs4SZmvFERw8yufdYyP8KKvIWkEkE0wD7X0LTY0XM4Ku29P_VMq9AjBGgHH5Qgkz8wsl14" alt=""><figcaption></figcaption></figure>

        <figure><img src="../../.gitbook/assets/image (77).png" alt=""><figcaption></figcaption></figure>



        *   Readonly\_db\_credentials: You will be prompted with default read-only database credentials. If you want to continue with the same, enter no; otherwise, enter yes and proceed to enter your read-only database credentials.

            &#x20;      read\_only\_db\_user\_name ( Enter the postgres database username )&#x20;

            &#x20;      read\_only\_db\_password ( Enter the postgres password )

        <figure><img src="../../.gitbook/assets/image (78).png" alt=""><figcaption></figcaption></figure>



        * Keycloak\_credentials: You will be prompted with the default keycloak admin dashboard credentials. If you want to continue with the same, enter no; otherwise, enter yes and proceed to enter your keycloak credentials.

        &#x20;          Keycloak\_adm\_name (Enter the keycloak admin name eg: admin)

        &#x20;          Keycloak\_adm\_password (enter the keycloak admin password eg: Admin@123)

    <figure><img src="../../.gitbook/assets/image (79).png" alt=""><figcaption></figcaption></figure>

    **Step 6:** Once the config file is generated, a preview of the config file is displayed, followed by a question where the user gets the option to re-enter the configuration values by choosing ‘yes’. If option ‘no’ is selected, then the install.sh moves to the next section.

<figure><img src="https://lh7-us.googleusercontent.com/qPp5Y-L2b-bkFSUVBWkODbMlOdlz2k0dhHjZ7EcqLccLqcnG0tuuJYrwLNbzZNA0pl03or2zGU5_opJuEAq8rdvtDdTBvQVXYcQgES8NZ0ZChNKs4kWy4AP04yjbzj1gHiDSQtiX24Br7CqtfJhRysA" alt=""><figcaption></figcaption></figure>

* Enter a location for your config \[/home/basha/.oci/config]: /root/.oci/config (enter)
* Enter a user OCID
* Enter a tenancy OCID
* Enter a region by index or name: ap-mumbai-1
* Do you want to generate a new API Signing RSA key pair? (If you decline you will be asked to supply the path to an existing key.) \[Y/n] : \<Click n> n
* Enter the location of your API Signing private key file

Ex: /root/.oci/itadmin@tibilsolutions.com\_2023-04-18T10\_08\_35.916Z.pem

<figure><img src="https://lh7-us.googleusercontent.com/BzRt1ckZGYT2PYW0URtRGPHD1yyiXmb4HG6xwlA7-DiTHnm3sYvmLCvsEI4E4Qq5sgBc5ztb4efERKJd2Jjw5aIbhGwptfOcv_tm2iF9jiGDPr_bNMu8PQY3bQf2pxTmZKvoj4iHIuTrOLhpCjuP14U" alt=""><figcaption></figcaption></figure>

**Step 7:**  A preview of the program\_selector.yml file is displayed, followed by a question where the user gets an option to enable or disable the programs by choosing 'yes'. If option 'no' is selected, then the install.sh moves to the next section.

&#x20;1\.   If access\_type is selected as VSK, the following programs will be displayed: by default, all programs are selected, and the programs are publicly visible.

<figure><img src="../../.gitbook/assets/image (80).png" alt=""><figcaption></figcaption></figure>

**Note:** If you are willing to select the programs, type yes, select the programs you want, and enter public or private for each program to enable or disable the login screen for programs (follow the hints provided).

2. If access\_type is selected as NVSK, the following programs will be displayed: By default, all programs are selected, and the programs are publicly visible.

<figure><img src="../../.gitbook/assets/image (81).png" alt=""><figcaption></figcaption></figure>

**Note:** If you are willing to select the programs, type yes, select the programs you want, and enter public or private for each program to enable or disable the login screen for programs (follow the hints provided).

**Step 8:** Once all the configuration files are generated, the script moves further to clone the cQube microservice repositories and deploy cQube

**Step 9:** If you selected data\_pull\_status as true, then you will see the data pulling APIs where the data gets pulled from the NVSK instance and processed in the VSK cQube Once installation is done, we need to wait 20 minutes to visualize the data on the cQube dashboard.

**Step 10:** Once the installation is completed, you will be prompted with the following messages and required reference urls:

**(Note: The installation process is expected to take approximately 30-40 minutes.)**

**cQube Installed Successfully**

<figure><img src="../../.gitbook/assets/image (82).png" alt=""><figcaption></figcaption></figure>

\


\

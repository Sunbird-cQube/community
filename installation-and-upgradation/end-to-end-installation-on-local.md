---
description: Localhost Deployment Document
---

# End to End Installation on Local Setup

## Prerequisites

### Hardware Requirements

* Ubuntu 22.04 (supported)&#x20;
* 16 GB of System RAM (minimum requirement)
* 250GB HDD

### Softwares to be installed:

* Git - Can be installed using the command sudo apt-get install git
* Postman - Can be installed using ubuntu software center

### Checking pre existing ports:

Make sure the following ports are not running. If running please stop the service or kill the port

* 8080 ( keycloak is configured in cqube )
* 8096 ( nifi is configured in cqube )
* 4200 ( dashboard is configured in cqube )
* 3000 ( ingestion is configured in cqube )
* 3001 ( spec is configured in cqube )
* 3002 ( queryBuilder is configured in cqube )
* 3003 ( generator ms is configured in cqube )
* 5432 ( postgres is configured in cqube )
* 9000 ( minio is configured in cqube )

Note: we can check for the ports using the command sudo netstat -ntlp and can kill the particular port using its port id by command sudo kill -15 \<PID>

\


## cQube Deployment Process for localhost

Step1: Open the terminal by using the command ctrl+alt+t and install git by using following command\
&#x20;                    sudo apt-get install git

Step2: Clone the repository using the following command\
&#x20;             git clone [https://github.com/Sunbird-cQube/cqube-devops.git](https://github.com/Sunbird-cQube/cqube-devops.git)

<figure><img src="https://lh4.googleusercontent.com/uHSD-RoZoVOF9A_v163j2uV8Ace_jc9SgkxZz-sXs8lRIUAxSjDaYAQbjeeVRhV3ZSAz5q6r6cag0CGBsvoSXGX4ziS-wppuTfPV0qWs5IVBDdmtUyo07yL4yRlZq8XL61bUEqHnjTQbW0rxoLDLlIA" alt=""><figcaption></figcaption></figure>

Step - 3: Navigate to the directory where cqube is cloned or downloaded and checkout to the latest branch **( currently the release is v5.0.3, please check the latest branch before you run the command)**

cd cqube-devops/ && git checkout release-v5.0.3

<figure><img src="https://lh4.googleusercontent.com/9v6NOwSy-RNObxD364WaEGJLv9LkCxC-LxfHdTvxi9gOayK8rQeGVz9jOkWM6edCEH4Z0GIUsV4q7D2WMamUmdfdTWl9x-Bvd5HF7GPurhZySifsJGMBfknfpL0IQGf56UWjER07PtuuW7Ou1joTLLc" alt=""><figcaption></figcaption></figure>

Step - 4: Give the following permissions to the install.sh file

sudo chmod u+x install.sh

Step - 5: Install cqube with non root user with sudo privileges

sudo ./install.sh

<figure><img src="https://lh4.googleusercontent.com/WAN1p0w429NXwnzSNWM-TlnTdb3B9cAjBAZtkWchVmbcCm1tQuM3nxRGYLRGJ6-L_Kb3bihNSz89eGeqsKUYt-Gq7lMq7H8QAddO1XTjts8o2bSYPTLlELeksEw18-STmEmXPKa2rQpYGDjZ8Ep-P1g" alt=""><figcaption></figcaption></figure>

Basic software Installation:  Wait till the basic required softwares gets installed. Following packages gets installed\
&#x20;               Python3, pip, ansible, docker.io, docker compose

<figure><img src="https://lh3.googleusercontent.com/iZmNN6v79li6gMNlwhx1taaW02eGbo-3M7JBBhQ0QSw_QXvpcnnkrBpxLniZeOPGl5EfJiYtAv_tWJkXZIz7s60z14vF6cAYctjJuLTz4iPnx7KEMYE0gLZdgM5_u0ZC_NiEW1ykkD5fPuHDednmeEw" alt=""><figcaption></figcaption></figure>

Step - 6: Config file generation process

&#x20;     We will go through a process of generating a configuration file. Please follow the hints provided and answer the questions accordingly

**access\_type:** enter VSK as we are going to choose state programs

**state\_name:** enter the state code for which you want to setup cqube

**mode\_of\_installation**: enter localhost as you are installing in a local laptop

**storage\_type:** enter local as its a localhost installation&#x20;

**api\_endpoint:** enter localhost as its a local laptop installation

**Google Analytics ID:** Enter NA as we are not opting for analytics as of now

**db\_user:** can use default user or enter your own username for db

**db\_name:** can use default db or enter your own db name for db

**db\_password:** can use default password or enter your own password for db

**keycloak\_adm\_user:** enter keycloak admin username that you want to set

**keycloak\_adm\_password:** enter admin password that you want to set

<figure><img src="https://lh6.googleusercontent.com/6g0rXL0FrwdLb3EgRfa2RTRlIVxQ_QEIrnYRNxyz5GWdkHjUSzhBVw1t73k3ypzyGaO8Ne4ZKx1gB2DHLnyJtIDIK7Vsiqi_NEpj3duARB5ToYfjl-7L91SpxulAZ4lWzwJnri5aA9jQf1_vPVHIcZQ" alt=""><figcaption></figcaption></figure>

Note: you will get an option to change the default credentials of postgres. If you want to give your own credentials type yes otherwise type no.

Once you complete answering the prompted questions a preview of the generated config file is generated and if you find any value as wrong you can select to re-edit the config file by typing yes. If all the entered values are correct then type no

<figure><img src="https://lh4.googleusercontent.com/-azOeGf0rFosrNlVDRW7bNd-ElgISi8wwbt9lQE_Jx9tmhQEfw9od8BaMd8AEkt9Pz5eSZYCGVca_6y74PPbi05Xx2mkw1JDftyTbE5BDvG_-QrUFujq7R669jeboDVuQI8Do_kMXXafVPylBM0Lh1Q" alt=""><figcaption></figcaption></figure>

**Minio bucket setup:** As we are using a storage type as local. A minio setup will be auto deployed as shown in the below figure.

<figure><img src="https://lh5.googleusercontent.com/aCMR7clsmtCEiu_cT-jNsWP86JeiQz-bIqULwq8OIjeEEIyh5urVlUtCe5XSFqVTU1z-M_-kj91cg0rtBtk27-qYOMb0C5qpxqCG8Wvfkpl-b_OIPJDXSwninuYiSxeboyv9gScmKFPe50sjrECK8QQ" alt=""><figcaption></figcaption></figure>

**Step - 7:** A preview of the program\_selector.yml file is displayed followed by a question where the user gets an option to enable or disable the programs on choosing yes. If option no is selected then program\_selector.yml file gets generated by default selected programs.

<figure><img src="https://lh5.googleusercontent.com/yaGdX7J23pnYCkjwFgD6a3dMMjvvolZndXz3SuBAcGK5k8h7-72zuakL3JM2UFVGhxInYtHRfqXm3xvfIaYZ_nLHEmGo4ONftETqlZJwCu8vfA70EtkxNQ6j3U80lOgcky0vo_0VDE8mLWrNRdPqHm8" alt=""><figcaption></figcaption></figure>

**Cloning of repos:** script automatically clones all the other microservices repositories and check out to the branch same as cqube-devops branch

<figure><img src="https://lh3.googleusercontent.com/sA8RnZAKef9564FifkTve78-Yum8YkJL9NEe4XnZFxtEpdUt9PmRGFiAU_1-RCy6e0CFfnrXgS7j3IHHAnIawhZqvH0BRIDOZ-pdnHpqoUoaAwYV_xLRU1UpTtpvTlnpB39jg_eUKVwU6AD1Pb9_Bso" alt=""><figcaption></figcaption></figure>

\
Building the docker images: Ansible scripts will get triggered which is used to configure the microservices with the variables in config files and then build the docker images

<figure><img src="https://lh5.googleusercontent.com/hzxtG6O4WamMPrUwpd68i3QeyW0bVTf--Hwl3VmephIli_sp0bnWzPjP9ZVdNqdqhiXT4iaIe_gwZ9XbdnKAeyzALBhqPqzxic1OHgaGtrA-ZrEWodHmIdX7aHXG3i5DJ8W7DDm6r00ZRLMZ4g6aizg" alt=""><figcaption></figcaption></figure>

Running the microservices: Ansible module to run the docker compose file gets triggered and all the microservices will be up with the desired network and volumes

<figure><img src="https://lh3.googleusercontent.com/DqU-SpJeOuocIc4kk-5rGQbkx8vppbapnqYkAsigU0FMb7kCec_9IOkcY_jWWMSD_DEOc8wTLeX8DarYIIjkcrAzGGos9pFVeaY2RiNBFaKEyoDmJSA_WdRjCCp4vLFUGbKo-OlgPZICaDFk6G-J9_Y" alt=""><figcaption></figcaption></figure>

Instantiating the nifi template and creating schemas: Required templates gets instantiated into the nifi and it clones processing-ms within the nifi container and creates the required schemas in the postgres database

<figure><img src="https://lh3.googleusercontent.com/7V5aSuimtG-Y1K5MWNFraao7ahbrwgQkGYC-b0osXBd_KbPYBMYua73B5XLBIR9CMtmdJAFECzL1XDxKvxIavncanr6DWnI5u8H_umMjN_u2qJH9hR41ysZ8zJNezfJ87rIkVBHuaF95bC8fCWiUoNw" alt=""><figcaption></figcaption></figure>

<figure><img src="https://lh3.googleusercontent.com/AncmxOkcVyygrFfCIyf0IhZhWrXbtc7__hRKb5lVyGer_KJfJ3JB9sq-Mf-HlITuHsCms4sz3BCwY9OZvebAZGVVw41-G70ayPlCVNDEc9Z9cdxTG2uZDeFOk8n7BlOrAhk5k6SfG4MX2UvgwtVRlUs" alt=""><figcaption></figcaption></figure>

Keycloak creation of realm:  A real with the name cQube gets created inside the keycloak

<figure><img src="https://lh3.googleusercontent.com/6vKpSiIT_9_ITYKjhbE3KYP-Z022SpRxmt-WlLnGhgzlXJQYar7EZbMCEvWhQjJjfts5H8nXycWsIBB2A2gH1mZKKe8ZSoVRd01SlvTZp8_w-O1CkThJRLLdPjWOGwynuVtkPDLXQ5YAjDmGBx7T2vk" alt=""><figcaption></figcaption></figure>

<figure><img src="https://lh6.googleusercontent.com/XX39-_nAaHtsTlfDbTaJxNtg4PkH9DQcRWXsPMNIyya4ABtwDPJ__i1QMnYHFt0hhAICXj2rmUZgwbuWLOKpZgnau4ZuS_6RqMuB7cjAHORWCsHv1Q442GygpqaULBrp4skkCT7fZdQP--SpZgS0zJM" alt=""><figcaption></figcaption></figure>

**Step - 8:** Once the installation is completed, we will see the message like “ cQube insallated successfully “  Once the  cQube successfully installed, It prompts with some useful links i.e cqube schema documentation and cqube usage documentation.

&#x20;

<figure><img src="https://lh4.googleusercontent.com/7Tf0P2MUYogaDmDXV8k-C0XmdcmlIqpNZlK6YbxGYudHZkbeqQqtQlX7o4NPGdcIwrxlpfSdH-O03y1Wpp08s3zG7Uz53V6PFCWQ1lMprTLpgb1VrRcutydoSAb-6D0XAES6sr8JhAC4dM06j7ntebM" alt=""><figcaption></figcaption></figure>

This completes the deployment of cqube in the local machine.

—----------------------------------------------------------------------------------------------------------------------------------------

\


## Keycloak configuration:

\
Step-1: Open the browser and hit the below link to open keycloak admin panel

&#x20;                                [http://localhost:8080](http://lovalhost:8080)

<figure><img src="https://lh5.googleusercontent.com/t3W3mLvtG1AhS8DmisK6TzJhjThfQNacax9YgRfJbifz-EuxJFvhMvzuZnSSYW2wmOH3RO_QbvQ3foft4ebEQUZ1ZyIUALIXTWHPknKIMlBO0NRrEWZ14gCjF_f6lH3osuKeX08TvEMR0ZQGJPIJz04" alt=""><figcaption></figcaption></figure>

Step-2: Click on Administration console

<figure><img src="https://lh4.googleusercontent.com/ZKNjnkbSRtmdLo7Mk7R90rV7A75t-3ZRTJSI-aXUSyGGvcV2Ad79uZuf-Ui-9pizv5PHdaqthG_RqWwMWcHE-HZ-DgVdoRHA3Ka6JXGO9ykLrYKWQ3ZQrixab4xY9oAyY8_MiL3UU_xdVSWXXcia7hg" alt=""><figcaption></figcaption></figure>

Step-3: Provide the keycloak admin username and password which you have given while generating the config file then click sign in option/ tab .

<figure><img src="https://lh5.googleusercontent.com/dwLyWF4MjdPFG5LXQe7etZVQTMNa1DiOlj_WeOL2MOLkGGloOBXyjRzgMViEZ5GznRE5nUNpry25yYQ2Gub-fNKOvlHdaO9ZeXjnpLRo1EFswH1qUs-SoBPD2lSt87pkeekHd9GGmFb_BjHEFuhE1E0" alt=""><figcaption></figcaption></figure>

Step-4: Click on clients tab  on the left hand side menu

<figure><img src="https://lh3.googleusercontent.com/IzbWELlsmYOHgWETXypeI2EbmPqvvp4E6CQz6mdcpraJOv9rS_8f-qe_wCLvhQBiWINOffG7Rgwd4Wm-EvBfvodffHvCWj3m0OH15zedWvckzpm4NV4O0qh-W8e1pqTQ9wceBxbHka0jeDSEeI5GCng" alt=""><figcaption></figcaption></figure>

Step-5: Click on the client cqube-5.0&#x20;

<figure><img src="https://lh6.googleusercontent.com/WSPLRCVycQTR2Y3MbZrVT_5J2to7ZGo54rIUK36IPdq1WaH0pPqQuUx_IpL9CZpZnstjxju6o6Xic5wa02qM9mUhmx0AmsseMItHr_3jqtSfHWXBqaWW_og9LbLWXQiOV1nD7kJn0VwJ6f4e51etvA8" alt=""><figcaption></figcaption></figure>

Step-6: Do the following configurations as explained below.

1. Direct access grant enabled&#x20;
2. Valid redirect URIs: [http://localhost:4200/\*](http://localhost:4200/\*)
3. Web Origins: [http://localhost:4200](http://localhost:4200/\*)

<figure><img src="https://lh3.googleusercontent.com/G-Yjo9hIs8cKZOHXVs0vgXlaR7CcHGRpweAe6_934OstRUUGdRoDcHCfWgYPoflHbyAMVEeUkITZrzYuL23P4MwIXy9wtxySgQ0P4Ft-QYFGB2vZrTYnGrXPzNbrN-46j_qKj7No4b65w6CN5BnAXm8" alt=""><figcaption></figcaption></figure>

Step-7: Once the configuration is done click save button

<figure><img src="https://lh6.googleusercontent.com/TTLuvudssBxC6sSsDqsC5q1iOpbApgUccdC2bShWhleGdW4zmo7bq5qX3wOJG4U9_KFyq32AviyFdZqa4SjsBXtjAjvVVmvdpxoEQeG7NRaPza1YZjIEbfQvoP-XhDzJoBaTWc7Z3dh80DuAcTSxz7U" alt=""><figcaption></figcaption></figure>

Step-8: Click on users on the left side of the keycloak admin panel

1. Click on add user
2. Enter the username and save the button

<figure><img src="https://lh3.googleusercontent.com/Qy9h18oVw1PAkskW3xxZdnM2xpOeQPp6ssGS9nLAaBPDUpkIWuVXXpFt-gi0vX-B4yxVaKGeRlE5WDu43ZmFXtVeLbkfKTvXSK7azdz4qda4Lehzx8F4hpH2R-sjG4o8oUyyFHHFfeZZ1SaerneCIDI" alt=""><figcaption></figcaption></figure>

Step-9: Create a password for the user

&#x20; Click the  credentials tab and then enter the following values&#x20;

1. Enter the password
2. Re enter the password
3. Disable Temporary
4. Click on set password

<figure><img src="https://lh6.googleusercontent.com/Zoy3XwoJ4KfLJ9h8nbEYFLD1dKLU1UowdaYHcoyjJCwyh96Rsgfnjmrfr7jBOFiVBNAdAEWKKPpMoxlsBjkaRn_7xDUsb-ncvFBzMQJRJWav_fVnl59BsKBUf8xUlNIacZ1IYCo3OI5W_I-ujfYVVdY" alt=""><figcaption></figcaption></figure>

Step-10: Once the keycloak configuration is done then you will be able to login to the dashboard using the link [http://localhost:4200](http://localhost:4200) in your browser.

Provide the credentials which you have added as a user in keycloak.

<figure><img src="https://lh3.googleusercontent.com/jwHg6rDs8KSvvtoMzRldkhMDXKl9C2QeTgfwnreSvBTFA5j9YDpsDRwvCCpQ2seKf1Khbfq6SussrY_Rm3R4wTe34fTsLho6XNH9kvMEz9DLXnxvEMDPt33XBLJSjqbPKp0UG7pp2QZUgA_J-V9kRw0" alt=""><figcaption></figcaption></figure>

<figure><img src="https://lh3.googleusercontent.com/KTo_nujrBvwW3nwIh7yWzjk6NMKwire-j9nfURcufanAD1jCGPoO6V9hSqD0EOjUDXWLkjeFetxtAam5KNw-fh4Hc_0A6UhdvFYyTdc0C4bBLJNjfhJEVksIRTvdiagI4y5VguE2eChmMZppojNbD3o" alt=""><figcaption></figcaption></figure>

\


—----------------------------------------------------------------------------------------------------------------------------------------\
Deployment video Link:\
If you need a deployment video please refer to the below url

[https://drive.google.com/file/d/1GdHQbX-PYJT9bI9BCew35J4F8Ma-aJH2/view?usp=sharing](https://drive.google.com/file/d/1GdHQbX-PYJT9bI9BCew35J4F8Ma-aJH2/view?usp=sharing)

—----------------------------------------------------------------------------------------------------------------------------------------

\
Important links and credentials:

### Minio Bucket:

Url: [http://localhost:9000](http://localhost:9000)

Username: minioadmin

Password: minioadmin

### Keycloak:

Url: [http://localhost:8080](http://localhost:8080)

Username: \<enter the username set while generating config file>\
Password: \<enter the username set while generating config file>\
Note: keycloak creds can be found in your cloned cqube-devops repository in the following path

Cat cqube-devops/config\_files/config.yml

### Dashboard:

Url: [http://localhost:4200](http://localhost:4200)

Username: \<enter username which is added in keycloak>\
Password: \<enter password of the user which is set in keycloak>

### API Calls:

| API Name          | Localhost Deployment api call                                          |
| ----------------- | ---------------------------------------------------------------------- |
| Schedule API      | http://localhost:3001/schedule                                         |
| National programs | http://localhost:3000/national\_programs                               |
| New Programs      | http://localhost:3000/new\_programs                                    |
| VSK schema        | http://localhost:3001/event                                            |
| Dimension Schema  | http://localhost:3001/dimension                                        |
| Generate Token    | [http://localhost:3000/generatejwt](http://localhost:3000/generatejwt) |

\
\
\
\
\

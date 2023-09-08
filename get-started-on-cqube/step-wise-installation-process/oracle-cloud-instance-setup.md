# Oracle Cloud Instance Setup

Create an instance with Ubuntu 22.04 image, 2 core OCPU, and 16GB RAM.

<figure><img src="https://lh6.googleusercontent.com/1tCanubBK2RIB3q2TBd7lxPeICi2l4X7CB-DYPV74j8L9qjDHQ1YzbubhsbXefYNlEWezfu864OWTnZCPBKfLxAfM3JnTc5iQ-4cBlfQFC6Kb3MiUT7jkIw2BYx5Y7NnqZt48hxBQFMGVjYqUsLLlPY" alt=""><figcaption></figcaption></figure>

* Download the private key file associated with the instance.

<figure><img src="https://lh4.googleusercontent.com/wWDQODHvwXUkXuPGlyHi1-NespJKRgSVu-Q_fy4rnMlB-Zdq2xFjLOj3SwJm9b3r4VeIQemEoLENiEXsZTbeXf46AYYhaLuh_kwy9iUIEKMIOQdfXVIz4ucDKedVJmcXKr1xya5juBwBD_kRpUyDm6Y" alt=""><figcaption></figcaption></figure>

Create a Storage Bucket:

* Go to the Oracle Cloud console and create a bucket with default configurations.

<figure><img src="https://lh4.googleusercontent.com/uHwlqOB_EZvDv1Om8oyoEod8UErp4ZgWYewJJowkVGnb4BVVwlBBzefwI_ZlMgnu_gIUOb8lUIzu49DLWslsQj1tqgvZHEeYePlLuW5CK5nqufdT9VmjGvfk0PCjMheDQAmAcB4KeyN1-vZOxCHjqH8" alt=""><figcaption></figcaption></figure>

**Generate Config File in Oracle Cloud:**

* Login to the Oracle Cloud account and navigate to the profile section

<figure><img src="https://lh5.googleusercontent.com/xF1r8tKofAXbvgJDOwD4F7BeyRKlM1CV-9PsYHcvqH2h1wHNpDz4X_uNoQvcm9hwDdmyvGJDM_na59O2mYL5NIp9kpLWsTMdGy1egvjFxXeducbN30v1KB21Eatk8iLNH8uugn5uDpIoLfYXH_Eq5T8" alt=""><figcaption></figcaption></figure>

* Generate a new key pair in the API keys section and download the private key file.

<figure><img src="https://lh5.googleusercontent.com/KRbkWrSaQseTyYKNeG8MB5f8pRs4pA6gJcZjM7Q27FiWbAh-wsNexPfuLtSE9cYsB1IXL7oWmndYKKnBVg6jENNUzzJ6HF1ZjuCgcAUKxZVA7zZ_qlISPcSOMGi_feGfOX28tTdFGxxsHHa0BM6Yzfs" alt=""><figcaption></figcaption></figure>

* Copy the content of the configuration file for future use.

<figure><img src="https://lh5.googleusercontent.com/ZmSITU1tGA1mfJemLmupYGovw3r92A5ljsOLx8wMYpSO1_6S3n5qztaHhTPCNdki3lEGRtyxEtZHZ95RHO5ZdihzIsUM3c8xIjxuEw6sRMpx1hnFkbP6w2QVMPIIRge40URGwEL2Cxv9pc1Ko8ou5Ac" alt=""><figcaption></figcaption></figure>

Upload the API Key File to the cQube Server:

* Connect to the cQube server using SSH.
* Copy the Oracle API private key file to the server using the command:

`scp -i <pem_file_of_server> <private_key_of_oracle_api> ubuntu@<ip>:~/`

* Switch to the root user: `sudo su`
* Move the private key file to the .oci directory:

`mkdir /root/.oci && cd /root/.oci`&#x20;

`mv /home/<system_user_name>/<private_key_of_oracle_api>`

* Verify the presence of the file in the current directory:

`ls -ltr`

* Exit from the root user and continue with the cQube installation.

### &#x20;Instructions to fill the Oracle config variables during installation:

* Copy the config file to the desired location (/root/.oci/config).
*   Open the config file and replace the following placeholders with actual values from the API key config file:

    * User OCID
    * Tenancy OCID
    * Region (by index or name)


* Decide whether to generate a new API Signing RSA key pair.
  * If declining, provide the path to an existing key.
* Specify the location for the API Signing private key file (/root/.oci/\<private\_key\_of\_oracle\_api>).

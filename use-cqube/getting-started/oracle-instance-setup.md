# Oracle Instance Setup

Instance Setup in Oracle Cloud:

**Step 1:** Create an instance with Ubuntu 22.04 image, 2 core OCPU, and 16GB RAM

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

\

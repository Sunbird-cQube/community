---
description: Explains the steps to install cQube V 5.0 on Oracle Server
---

# For Oracle Server

### Instance Setup in Oracle Cloud:

* Create an instance with Ubuntu 22.04 image, 2 core OCPU, and 16GB RAM.

![](https://lh3.googleusercontent.com/9bPutFaTGKbDw4Hn2xdymuuS-t\_Q3tuNOzM6jkaGMzRhqgx0psYMj6ZqDHlTEXymOQHJPNw-9QMpEHVJwnehlvbGIhJSoeTH8kJY1mmTwT52gKXnyQBIdShQHmw47rsJDVg4lv3uwo1t-2dknS0uRfs)

* Download the private key file associated with the instance.

![](https://lh5.googleusercontent.com/t2sQfNTbtezsnI1mhEEbpEMQye2Er5d2FBaD64EYH8w\_NBB4KZprrvEzI5CsZVq5\_S7WkGmFznYwMVnevEvdkAgRcszVO2kEu2JDK\_aJEuHJBgyRfdAexWSdvzlaL7djVoFSFfgMLR3JbkRxCSrfAtg)

### &#x20;Create a Storage Bucket:

* Go to the Oracle Cloud console and create a bucket with default configurations.

![](https://lh4.googleusercontent.com/B-XFN\_NB60bZI3U6D9puczncmNKidZEWVzZGjCHFp5ryq8j1E3NIxLWmybkn9tMhpo2SZwT5vZZsvUYeqraqIcDNzrLo6Cm48QRtL8jjCWdSeNsoW\_CWCF6gP\_pY0KtRW6bJ9RnSohmp2FjVh4KqiMQ)

### Generate Config File in Oracle Cloud:

* Login to the Oracle Cloud account and navigate to the profile section

![](https://lh6.googleusercontent.com/\_pRtRhCAzpprkOkcciwXQ9AT3fwH4s7wqp6s45utKYrjrBazu1kEgthKwtCrP7pKhQS1IKlJSYL8v7Ba-lWhIlmHNG1MurAGltHAUxFCODyIwI4c6V-QKXoawY6A4NXZy1b\_gCM6oFVyabopfeuB04k).

* Generate a new key pair in the API keys section and download the private key file.

![](https://lh6.googleusercontent.com/qg9LPF3qH60-NIr9USUbS1OSk8IYKKuOo61V9arHJFxOoVnr8WwBH6WfKuw-OPg7l6-MGdnWeGpAC2kmxVYgbBNJoHHOTF\_YMCUclgDU5y7k9VS57ZnxUK4jzjkTKJCeo8gQyRwp3B-g9uyY7cpyQ1k)

* Copy the content of the configuration file for future use.

![](https://lh3.googleusercontent.com/q4Js\_Fzgorn7B8GGKyjSrn-8y9B9pRiPiUXwCcxm-Ic7WmaSatC6C0HTPCRo140FZRZu2-cjEc2HnU4wZi3ZyCQa9lQqU\_kmeXYeatfZw2LImadau8C27A-2\_fX9A\_uGiFusoQass8HFM1OZSf9JRQk)

### Upload the API Key File to the cQube Server:

* Connect to the cQube server using SSH
*   Copy the Oracle API private key file to the server using the command:

    scp -i \<pem\_file\_of\_server> \<private\_key\_of\_oracle\_api> ubuntu@\<ip>:\~/
* Switch to the root user: sudo su
*   Move the private key file to the .oci directory:

    mkdir /root/.oci && cd /root/.oci&#x20;

    mv /home/\<system\_user\_name>/\<private\_key\_of\_oracle\_api>&#x20;
*   Verify the presence of the file in the current directory:

    ls -ltr
* Exit from the root user and continue with the cQube installation
* Instructions to fill the Oracle config variables during installation
  * Copy the config file to the desired location (/root/.oci/config).
  * Open the config file and replace the following placeholders with actual values from the API key config file:
  * User OCID
  * Tenancy OCID
  * Region (by index or name)
  * Decide whether to generate a new API Signing RSA key pair.
  * If declining, provide the path to an existing key.
  * Specify the location for the API Signing private key file (/root/.oci/\<private\_key\_of\_oracle\_api>).



\

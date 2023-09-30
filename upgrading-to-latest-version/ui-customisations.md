# How can I upgrade cQube to the latest release

**AWS**

Connect to the cQube AWS EC2 Instance

For Linux and macOS:

1. Download the .pem file generated during EC2 instance creation.
2. Open the terminal and navigate to the folder where the .pem file is downloaded.
3. Provide read permission to the .pem file: sudo chmod 400 \<aws.pem>

Connect to the instance using the following command:

4. ssh -i \<path\_to\_the\_pem\_file> \<user\_name>@\<public\_ip\_of\_the\_instance>

For Windows:

1. Download the .pem file generated during EC2 instance creation.

Use Puttygen to connect to the instance. Refer to this link for instructions:[ PuttyGen Instructions](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/putty.html)

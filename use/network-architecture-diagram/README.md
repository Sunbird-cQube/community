# AWS - Network Architecture

The following steps define the cQube setup and workflow completion process in AWS. cQube mainly comprises of the areas mentioned below:

1. Private Subnet
2. Public Subnet
3. AWS Load Balancer
4. IAM user and Role creation for S3 connectivity.

The cQube network setup process is described in the block diagram below:

![AWS - cQube network setup diagram](https://github.com/Sunbird-cQube/community/blob/master/.gitbook/assets/cQube%20AWS%20-Network%20%20architecture.png)

* The Yellow arrows in the network diagram indicate the connectivity through the load balancer, for those users who upload the files.
* The Green arrow in the network diagram indicates the end user's connectivity through the load balancer.
* The purple colored arrow in the network diagram indicates the developer's connectivity through the VPN.

## **Private Subnet**

Private subnet is used to secure the cQube server from unauthenticated users and public access. The instance will not have the public IP. An EC2 instance will be created in a private subnet and all cQube components will be installed in this.

The steps involved to create EC2 instance in private subnet

* Create a virtual private cloud \(VPC\) in AWS 
* Create a subnet in the created VPC with no Routing Table attached to Internet gateway
* Create an EC2 instance to install all the cQube software components.

**EC2**: cQube server

    - Create an ec2 instance with configuration mentioned below:

    - 8 core CPU, 32 GB RAM and 1 TB storage

**Security group:**

 ****     - port 4200, 3000, 8000 inbound from Nginx 

      - port 4201, 3001, 9000, 8080, 8096, 22 inbound from OpenVPN server

**Load Balancer:**

    - Create a load balancer 

    - Configure it to connect to Nginx on port 80, 443

**Domain Name:** 

      - Create a domain name

      - Configure CNAME of load balancer to domain name

**SSL:**

      - Create a certificate from AWS Certificate Manager

      - Attach it to the load balancer

**Security Group:**

   ****   - port 80, 443 inbound from 0.0.0.0/0

**Note:** For the concurrent users  between 100 to1000, the recommended Nginx machine is the type with a 'm' or 'c' series 2 core machine. The machine size has to be increased according based on the concurrent user's traffic.

## **User Actions in the creation of Nginx**

**Addition of G zipping to the UI -** User has to enable the compression in the proxy server for the content type 'application/JavaScript' and 'text/CSS'.

The sample configuration for reference to add in Nginx conf. is shown in the figure below: 

```text
server {
        gzip on;
        gzip_types      application/javascript text/css;
        gzip_min_length 1000;
        gzip_static on;
        }
```

The sample configuration for reference to add in Nginx conf. is shown in the figure below:

```text
location /api {
          proxy_cache my_cache;
          proxy_buffering on;
          proxy_cache_methods POST;
          proxy_cache_key "$request_uri|$request_body";
          proxy_ignore_headers Expires Cache-Control X-Accel-Expires;
          proxy_cache_valid any 30m;
          proxy_ignore_headers "Set-Cookie";
         proxy_cache_use_stale error timeout updating http_500 http_502 http_503 http_504;
         add_header X-Proxy-Cache $upstream_cache_status;
    }
```

## **Public Subnet**

Public subnet will contain two EC2 instances, one is for OpenVPN and another is for Nginx, which will act as a reverse proxy. It is used to provide connectivity with the private subnet.

The following are the steps involved to create the public subnet:

* Create a subnet in that same VPC where the private subnet has been created, with a Routing Table attached to the Internet Gateway.
* Create the first EC2 instance with OpenVPN AWS AMI and configure it to connect with the private subnet. 
* Create the second EC2 instance with Ubuntu 18.04 AWS AMI and install Nginx to connect to the cQube server which is present in the private subnet.

**EC2**: OpenVPN server

    - Create an ec2 instance with OpenVPN ami 

    - Create users to access the instances and for cQube admin pages 

    Security group:

      - port 22 inbound to 1 public IP \(admin's\)

**EC2:** Nginx server

    - Create an ec2 instance with ubuntu 18.04 ami

    - Configure Nginx to connect the Load balancer and the cQube server

    - The configuration file will be provided

    Security group:

      - port 80, 443 inbound to Load balancer

      - port 22 inbound to OpenVPN server

**NAT Gateway**:

    - Create a Nat gateway / Nat instance

    - Configure the connection to the cQube server

    Security group:

      - port 80, 443 inbound from private subnet

## **AWS Load Balancer** 

AWS load balancer is used in cQube to avoid any security risks and also to control traffic among the servers. It is used to improve up-time and to make cQube easily scalable, by adding or removing servers, with minimal disruption to cQube traffic flows. cQube is using the Application Load Balancer.

**Steps involved in creating the load balancer:**

1. Open the Amazon EC2 console at [https://console.aws.amazon.com/ec2/v2/home](https://console.aws.amazon.com/ec2/v2/home)
2. On the navigation bar, choose a region for the load balancer. Select the same region that has been selected for the EC2 instances.
3. On the navigation pane, under LOAD BALANCING, choose Load Balancers.
4. Choose the option "Create Load Balancer".
5. For Application Load Balancer, choose "Create".

**Steps involved in configuring the load balancer with EC2 instance**

* On the Configure Health Check page, set the Ping Protocol to HTTP and Ping Port to 80.
* Replace the default value with a single forward slash \("/"\) for ping path. This sends a message to the Elastic Load Balancing to send health check queries to the default home page for the web server, for example: index.html.
* Select the Nginx instance to register with the load balancer on the Add EC2 Instances page,.

## **IAM user and Role creation for S3 connectivity**

An AWS Identity and Access Management \(IAM\) user is an entity that is created in AWS to represent the person or application that uses it to interact with AWS. A user in AWS contains a name and credentials. An IAM user with administrator permissions is different from the AWS account root user. ****One has to create an IAM user with a supported role to provide the connectivity between EC2 and S3 . The role should have list, read and write permissions

There are multiple ways to create the IAM user account, but in cQube the IAM user has been created from the AWS GUI by following the steps mentioned below:

**AWS S3:**

    ****- Create 3 buckets for input, output and emission

    **IAM User:**

   ****   - Create an IAM user

      - Assign IAM policy to user 

      - Download the AWS access key and secret key

    **IAM Policy:**

      - Create a policy from AWS IAM 

      - Provide access to list, read and write the object to s3 buckets

  
**Note:** The data transmission between ec2 and s3 happens within the AWS network by adding VPC endpoint to connect to s3 buckets. This helps increase the network speed by 15%.  



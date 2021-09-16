# Network Architecture diagram

The following steps define how the cQube setup and workflow is completed in AWS. cQube mainly consists of the areas mentioned below:  


1. Private Subnet
2. Public Subnet
3. AWS Load Balancer
4. IAM user and Role creation for S3 connectivity.

The cQube network setup process is described in the block diagram below:  


![cQube network setup diagram ](.gitbook/assets/image%20%282%29.png)



* The Yellow arrows in the network diagram indicate the file upload users’ connectivity through the load balancer.
* The Green arrow in the network diagram indicates the end user's connectivity through the load balancer.
* The purple color arrow in the network diagram indicates the developers connectivity through the VPN.

## **Private Subnet**

Private subnet is used to secure the cQube server from public access. The instance will not be having the public ip. An EC2 instance will be created in a private subnet and all cQube components will be installed in this.  
****

**Note:** For the concurrent users  between 100 to1000, The recommended Nginx machine type  would be 'm' or 'c' series 2 core machine to use. And need to increase the machine size according to the concurrent users traffic.  
****

The steps involved to create EC2 instance in private subnet

* Create a virtual private cloud\(VPC\) in AWS 
* Create a subnet in the created VPC with no Routing Table attached to Internet gateway
* Create an EC2 instance to install all the cQube software components.

**EC2**: cQube server

    - create an ec2 instance with below mentioned configuration

    - 8 core cpu, 32 gb ram and 1 tb storage

**Security\_group:**

 ****     - port 4200, 3000, 8000 inbound from nginx 

      - port 4201, 3001, 9000, 8080, 8096, 22 inbound from openvpn server

**Load Balancer:**

    - create a load balancer 

    - configure it to connect to nginx on port 80, 443

**Domain Name:** 

      - create a domain name

      - configure CNAME of load balancer to domain name

**SSL:**

      - create a certificate from AWS Certificate Manager

      - attach it to load balancer

**Security Group:**

   ****   - port 80, 443 inbound from 0.0.0.0/0  


## **User Actions in creation of Nginx**

**Addition of Gzipping to the UI -** Have to enable the compression in the proxy server for the content type 'application/javascript' and 'text/css'.  
****

Below is the sample configuration \[for reference\] to add in nginx conf. 

`server {`

               `gzip on;`

              `gzip_types      application/javascript text/css;`

             `gzip_min_length 1000;`

              `gzip_static on;`

            `}`  
  
**Cache implementation -** Have to enable caching in the proxy server for /api location directive.  
****

Below is the sample configuration \[for reference\] to add in nginx conf.  
`location /api {`

          `proxy_cache my_cache;`

          `proxy_buffering on;`

          `proxy_cache_methods POST;`

          `proxy_cache_key "$request_uri|$request_body";`

          `proxy_ignore_headers Expires Cache-Control X-Accel-Expires;`

          `proxy_cache_valid any 30m;`

          `proxy_ignore_headers "Set-Cookie";`

         `proxy_cache_use_stale error timeout updating http_500 http_502 http_503 http_504;`

         `add_header X-Proxy-Cache $upstream_cache_status;`

    `}`  



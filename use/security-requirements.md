# Security Implementations

* cQube product security is  provided by implementing the private subnet with AWS load balancer as described in the [AWS - Network Architecture](https://cqube.sunbird.org/use-getting-started/network-architecture-diagram).    
* All the ports can be accessed by Nginx server only, none of these ports can be accessed directly from the internet.
* Kong API Gateway will secure, manage, and extend API Endpoints.
* Keycloak Identity Server is being used for securing web applications. Keycloak uses open protocol standards like [OpenID Connect](https://openid.net/connect/) or [SAML 2.0](http://saml.xml.org/saml-specifications) to secure the applications. Google OAuth can be enabled for the two-factor authentication.
* Users entries need to be configured in PostgreSQL database configuration files along with the IP address. Ad-hoc analysts only can connect using OpenVPN in read only mode.

**EC2**: A pair of public and private keys are generated, and the public key is stored in the EC2 server. The client with the private key gets authenticated with the server during login only if the keys match.

* S3 Emission, Input & Output buckets: A pair of access keys and secret keys are generated to access the data files from S3. 
* Apache NIFI: NIFI Dashboard is restricted in production. The confidential keys such as username and password will be encrypted using **PBEWITHMD5AND256BITAES-CBC-OPENSSL** algorithm in NIFI.
* Angular: Role based authentication will be provided to prevent access to unauthorized users.  
* Role based authentication: Will be provided to admin users and can access admin console only using OpenVPN.
* Normal/ regular users can access public reports with keycloak authentication.
* A reverse proxy server has been used that usually stays behind the firewall of a private network. Reverse proxies are also used as a means of caching common content and compressing inbound and outbound data, resulting in a faster and smoother flow of traffic between the clients and servers.


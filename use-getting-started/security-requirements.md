# Security Implementations

* cQube product security will be provided by implementing the private subnet with AWS load balancer as described in the Section 2 of this document.    
* All the ports will be accessed by Nginx server only, So those ports will not be accessed directly from the internet.    
* Kong API Gateway is used to safeguard authentication & authorisation for API endpoints
* Keycloak Identity Server is used for user authentication. Google OAuth can  be enabled for the two factor authentication.
* PostgreSQL will be secured by the following ways  
  \(The database security will be implemented in the future versions of cQube\)

  * User and Role Management: the user roles will be granted with one or more cQube database will have three different types or roles: 1. role role \(identified by prefix r_\) 2. group role \(identified by prefix g_\) 3. user role \(generally personal or application names\)



  **EC2** : A pair of public and private keys are generated, and the public key is stored in the EC2 server. The client with the private key gets authenticated with the server during login only if the keys match.

  **S3 emission data bucket** : cQube provides a data-ingestion API to emit the data. The API will have different secured endpoints like:

  1. API call to emit the data files using the https protocol into cQube.
  2. API takes the data file as a parameter.
  3. The API will provide acknowledgement on successful emission.



  * S3 buckets will be secured by the default AWS security. 
  * S3 Input & Output buckets: A pair of access keys and secret keys are generated to secure the S3 location. 
  * NIFI: NIFI Dashboard is restricted in production. The confidential keys such as username and password will be encrypted.
  * Angular: Role based authentication will be provided to prevent access to unauthorised users. A reverse proxy server has been used that usually stays behind the firewall of a private network. Reverse proxies are also used as a means of caching common content and compressing inbound and outbound data, resulting in a faster and smoother flow of traffic between the clients and servers. 
  * Role based authentication: Will be provided to admin users, and based on the user roles, relevant access will be provided to users at district levels, block levels, cluster levels and school levels.
  * Normal/ regular users can access public reports with keycloak authentication.


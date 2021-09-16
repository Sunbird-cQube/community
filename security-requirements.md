# Security requirements



* cQube product security will be provided by implementing the private subnet with AWS load balancer as described in the Section 2 of this document.    
* All the ports will be accessed by Nginx server only, So those ports will not be accessed directly from the internet.    
* S3 buckets will be secured by the default AWS security.    
* Kong API Gateway is used to safeguard authentication & authorisation for API endpoints
* Keycloak Identity Server is used for user authentication. Google OAuth can  be enabled for the two factor authentication.
* PostgreSQL will be secured by the following ways \(The database security will be implemented in the future versions of cQube\)
  * User and Role Management: the user roles will be granted with one or more cQube database will have three different types or roles: 1. role role \(identified by prefix r_\) 2. group role \(identified by prefix g_\) 3. user role \(generally personal or application names\)


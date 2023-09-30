# Checking pre existing ports

Make sure the following ports are not running. If running please stop the service or kill the port

Security Group Configuration:

* Port 80 inbound from 0.0.0.0/0
* Port 443 inbound from 0.0.0.0/0
* Port 3005 inbound from 0.0.0.0/0
* 5432 inbound to the particular ip which needs access

Kong Configurations: ( already configured using one step deployment )

* 3000 will get routed to /api/ingestion
* 3001 will get routed to /api/spec
* 3002 will get routed to /api/queryBuilder
* 3003 will get routed to /api/generator
* 443 ( nginx is configured in cqube )

**Note:** we can check for the ports using the command **sudo netstat -ntlp** and can kill the particular port using its port id by command **sudo kill -15 \<PID>**

\

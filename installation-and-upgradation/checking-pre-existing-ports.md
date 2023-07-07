# Checking pre existing ports

Make sure the following ports are **NOT** running. If running please stop the service or kill the port

* 8080 ( keycloak is configured in cqube )
* 8096 ( nifi is configured in cqube )
* 4200 ( dashboard is configured in cqube )
* 3000 ( ingestion is configured in cqube )
* 3001 ( spec is configured in cqube )
* 3002 ( queryBuilder is configured in cqube )
* 3003 ( generator ms is configured in cqube )
* 5432 ( postgres is configured in cqube )
* 9000 ( minio is configured in cqube )
* 80  ( nginx is configured in cqube )
* 443 ( nginx is configured in cqube )

**Note: we can check for the ports using the command sudo netstat -ntlp and can kill the particular port using its port id by command sudo kill -15 \<PID>**

\

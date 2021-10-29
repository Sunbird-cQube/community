# Hardware requirements

The table below describes the Infrastructure prerequisites for successful installation of the cQube Base in the AWS environment:

|Infrastructure used for cQube Base installation |Required Skills |
| :--- | :--- |
| AWS account 1. cQube Server \(CPU - 8 Core RAM - 32 GB Storage - 500 GB\) 2. S3 Buckets \(S3 emission 100GB S3 input - 750 GB S3 Output - 250 GB\) | AWS Basic Operation Skills -EC2 -S3 -Load -Balancer -IAM -VPC -Route53 -Certificate Manager \(SSL\) |
| [OpenVPN](https://aws.amazon.com/blogs/awsmarketplace/setting-up-openvpn-access-server-in-amazon-vpc/) Access Server \( EC2 instance CPU - 1 Core RAM - 2 GB, Storage - 10 GB\) | VPN admin Operations |
| NGINX Reverse proxy \(EC2 instance CPU - 2 Core RAM - 4 GB Storage - 30 GB\) | NGINX configuration skills |
| NAT gateway | AWS NAT gateway |
| Ubuntu 18.04 server | To be taken care while creating EC2 instance |
| Java JDK 1.8 | To be installed through One-Step cQube Base Installation |
| Python 3 | To be installed through One-Step cQube Base Installation |
| NIFI 1.12.1 | To be installed through One-Step cQube Base Installation |
| Angular 9.1.6, Chart.JS 2.9.3, Leaflet 1.6.0 | To be installed through One-Step cQube Base Installation |
| PostgreSQL 10.12 | To be installed through One-Step cQube Base Installation |


# Prerequisites for Installation process

#### Prerequisites to install cQube:

* ubuntu 18.04 \(supported\)
* 32GB of System RAM \(minimum requirement\)
* 8 core CPU \(minimum requirement\)
* Domain name \(with SSL\)
* 1 TB Storage


#### Reverse proxy rules (public routing):

* Port 4200 should be proxied to the '/'
* Port 8080 should be proxied to the '/auth'
* Port 3000 should be proxied to the '/api'
* Port 8000 should be proxied to the '/data'

#### Nginx - cQube server firewall configuration

* Port 4200 should be open from Nginx to the cQube server
* Port 8080 should be open from Nginx to the cQube server
* Port 3000 should be open from Nginx to the cQube server
* Port 8000 should be open from Nginx to the cQube server

#### OpenVPN - cQube server firewall configuration

- Port 9000 should be open from OpenVPN to the cQube server   

![cQube Nginx Routes](../.gitbook/assets/cqube_nginx_routes.png)

#### Reverse proxy rules (internal routing):
The following ports have to be configured in the Nginix server with reverse proxy:

- Port 4201 should be proxied to the '/'
- Port 3001 should be proxied to the '/api'

#### Nginx - cQube server firewall configuration

- Port 4201 should be open from Nginx to the cQube server
- Port 3001 should be open from Nginx to the cQube server 

#### Openvpn - cQube server firewall configuration

- Port 80 should be open from openvpn to the Nginx


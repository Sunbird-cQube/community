<h1>Installation:</h1>

- Open Terminal
- Navigate to the directory where cQube has been downloaded or cloned 
```
cd cQube/ansible/installation_scripts/
git checkout release-2.0
```
- Copy the config.yml.template to config.yml 
`cp config.yml.template config.yml`
- Edit using `nano config.yml`
- Fill the configuration details for the below mentioned list in `config.yml` (* all the values are mandatory)
- cQube installation process installs the components in a sequence as mentioned below:
  - Installs Ansible
  - Installs Openjdk
  - Installs Python, pip and flask
  - Installs Postgresql
  - Installs NodeJS
  - Installs Angular and Chart JS
  - Installs Apache Nifi
  - Installs Keycloak
  - Installs Grafana
  - Installs Prometheus and node exporter

- Save and Close the file

- Give the following permission to the install.sh file
```
chmod u+x install.sh
```
- Install cQube using the non-root user with sudo privilege
- Configuration filled in `config.yml` will be validated first. If there is any error during validation, you will be prompted with the appropriate error message and the installation will be aborted. Refer the error message and solve the errors appropriately, then re-run the installation script `sudo ./install.sh`
- Start the installation by running install.sh shell script file as mentioned below:
```
sudo ./install.sh
```
Once installation is completed without any errors, you will be prompted the following message. 
```CQube installed successfully!!```

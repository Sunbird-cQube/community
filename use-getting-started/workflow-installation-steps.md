# Workflow Installation steps

## Steps cQube\_Workflow Installation:

* Open Terminal
* Navigate to the directory where cQube\_Workflow has been downloaded or cloned 

  ```text
  cd cQube_Workflow/work_deploy/
  git checkout release-3.1
  ```

**Usecases folder structure**

* educational\_new\_theme
* educational\_old\_theme

  \*\*\*\*

**If user opting for educational\_new\_theme open the educational\_new\_theme folder**

* Copy the config.yml.template to config.yml `cp config.yml.template config.yml`
* Edit using `nano config.yml`
* Enable datasources as true or false in datasource.yml and datasource\_validation.sh, in datasource\_validation.sh  An array of mandatory values should be same as datasource.yml file values. 

  **If user opting for educational\_old\_theme open the educational\_old\_theme folder**

* Copy the config.yml.template to config.yml `cp config.yml.template config.yml`
* Edit using \`nano config.yml\`
* Enable datasources as true or false in datasource\_config.yml and datasource\_validation.sh, in datasource\_validation.sh  An array of mandatory values should be same as datasource\_config.yml file values.
* if the user opting for new datasource.  should add new datasource name inside the datasource\_config.yml file and datasource\_validation.sh array list.
* Fill the configuration details for the below mentioned list in config.yml \(\* all the values are mandatory\)
* cQube\_Workflow installation process configuring the components in a sequence as mentioned below:
  * Configures Ansible
  * Configures Openjdk
  * Configures Python, pip and flask
  * Configures Postgresql
  * Configures NodeJS
  * Configures Angular and Chart JS
  * Configures Apache Nifi
  * Configures Keycloak
  * Configures Grafana
  * Configures Prometheus and node exporter
* Give the following permission to the install.sh file

  ```text
  chmod u+x install.sh
  ```

* Install cQube using the non-root user with sudo privilege
* Configuration filled in config.yml will be validated first. If there is any error during validation, you will be prompted with the appropriate error message and the installation will be aborted. Refer the error message and solve the errors appropriately, then re-run the installation script `sudo ./install.sh`
* Start the installation by running install.sh shell script file as mentioned below:

  ```text
  sudo ./install.sh
  ```

* Once installation is completed without any errors, you will be prompted the following message.  **cQube installed successfully!!** 


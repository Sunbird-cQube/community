# Workflow Installation steps

## Steps cQube\_Workflow Installation:

- Open Terminal

- Navigate to the directory where cQube_Workflow has been downloaded or cloned

  ```
    cd cQube_Workflow/work_deploy/
    git checkout release-3.1
  ```
## Usecases folder structure
  - education_usecase
  - education_usecase_theme2
### if user opting for education_usecase open the education_usecase folder 
- Copy the config.yml.template to config.yml 
  ```
  cp config.yml.template config.yml
  ```
- Edit using ```nano config.yml```
- Enable datasources as true or false in datasource.yml and datasource_validation.sh, in datasource_validation.sh  an array of mandatory values should be same as datasource.yml file values. 
### if user opting for educational_usecase open the educational_usecase_theme2 folder
- Copy the config.yml.template to config.yml 
  ```
  cp config.yml.template config.yml
  ```
- Edit using ```nano config.yml```
- Enable datasources as true or false in datasource_config.yml and datasource_validation.sh, in datasource_validation.sh  an array of mandatory values should be same as datasource_config.yml file values.
- If the user opting for new datasource.  should add new datasource name inside the datasource_config.yml file and datasource_validation.sh array list.
- Fill the configuration details for the below mentioned list in config.yml (* all the values are mandatory)

- cQube_Workflow installation process configuring the components in a sequence as mentioned below:

  - Configures Ansible
  - Configures Openjdk
  - Configures Python, pip and flask
  - Configures Postgresql
  - Configures NodeJS
  - Configures Angular and Chart JS
  - Configures Apache Nifi
  - Configures Keycloak
  - Configures Grafana
  - Configures Prometheus and node exporter


- Give the following permission to the install.sh file

  ```chmod u+x install.sh```

- Install cQube using the non-root user with sudo privilege

- Configuration filled in config.yml will be validated first. If there is any error during validation, you will be prompted with the appropriate error message and the installation will be aborted. Refer the error message and solve the errors appropriately, then re-run the installation script ```sudo ./install.sh```

- Start the installation by running install.sh shell script file as mentioned below:

  ```
  sudo ./install.sh
  ```

- Once installation is completed without any errors, you will be prompted the following message. **CQube installed successfully!!**

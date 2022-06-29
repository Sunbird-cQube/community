# Workflow Installation steps

## Steps cQube\_Workflow Installation:

* Open Terminal
* Navigate to the directory where cQube\_Workflow has been downloaded or cloned

  ```text
    cd cQube_Workflow/work_deploy/education_usecase
    git checkout release-3.6
  ```

* Copy the config.yml.template to config.yml

  ```text
  cp config.yml.template config.yml
  ```

* Edit using `nano config.yml`
* Enable data sources as true or false in datasource_config.yml 
* Edit using `nano datasource_config.yml`

* If infrastructure and udise is set to true in datasource_config.yml, follow the below steps to configure infrastructure and udise, Else skip the Configuration.

    #### Configuration of infrastructure attributes and UDISE data indices, metrics:

    - Based on the number of infrastructure attributes required by the state, configure the infrastructure report by filling the required fields in the  infrastructure_master.csv file under cQube_Workflow/development/datasource/infra/postgres/ directory
    - To edit below mentioned infrastructure details

      ```text
      nano infrastructure_master.csv
      ```

    - Based on the configured columns  in infrastructure_master.csv, update the infra_parameters.txt file with the configured columns
    under development/datasource/infra/nifi/ directory.
    
      ```text
      nano infra_parameters.txt
      ```
      change the value of **infra_normalize** under infra_parameters.txt
    
    
    - Save and Close the file
    - Based on the number of UDISE attributes required by the state, configure the udise\_config.csv file by filling the required fields in the  udise\_config.csv file under cQube_Workflow/development/datasource/udise/postgres/ directory
    - To edit below mentioned UDISE details

      ```text
      nano udise_config.csv
      ```

    - Save and Close the file
    - For more information to configure the weights & columns for UDISE/infrastructure, please refer operational document.
* Update the diksha parameters\(api\_url, token, encryption key, dataset name,channel\_id, org\_id\) in the diksha_parameters.txt file under       cQube_Workflow/development/datasource/diksha/nifi/



* cQube\_Workflow installation process configuring the components in a sequence as mentioned below:
  * Configures Ansible
  * Configures OpenJDK
  * Configures Python, pip and flask
  * Configures PostgreSQL
  * Configures NodeJS
  * Configures Angular and Chart JS
  * Configures Apache NIFI
  * Configures Keycloak
  * Configures Grafana
  * Configures Prometheus and node exporter
* Give the following permission to the install.sh file

  `chmod u+x install.sh`

* Install cQube using the non-root user with sudo privilege
* Configuration filled in config.yml will be validated first. If there is any error during validation, you will be prompted with the appropriate error message and the installation will be aborted. Refer the error message and solve the errors appropriately, then re-run the installation script `sudo ./install.sh`
* Start the installation by running install.sh shell script file as mentioned below:

  ```text
  sudo ./install.sh
  ```

* Once installation is completed without any errors, you will be prompted the following message. **CQube installed successfully!!**


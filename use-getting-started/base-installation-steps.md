# Base Installation steps

# cQube_Base Installation:
- open Terminal
- Navigate to the directory where cQube_Base has been downloaded or cloned 
  ```
  cd cQube_Base/
  git checkout release-3.1
  ```
- Copy the config.yml.template to config.yml 
  ```
  cp config.yml.template config.yml
  ```
- Edit using ```nano config.yml```
- If you are opting for storage_type as s3. Copy the aws_s3_config.yml.template to aws_s3_config.yml 
  ```
  cp aws_s3_config.yml.template aws_s3_config.yml
  ```
- Edit using ```nano aws_s3_config.yml```
- If you are opting for storage_type as local. Copy the local_storage_config.yml.template to local_storage_config.yml 
  ```
  cp local_storage_config.yml.template local_storage_config.yml
  ```
- Fill the configuration details for the below mentioned list in config.yml (* all the values are mandatory)
- cQube_Base installation process installs the components in a sequence as mentioned below:
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

### Configuration of infrastructure attributes and udise data indices, metrics:

- Based on the number of infrastructure attributes required by the state, configure the infrastructure report by filling the required fields in the file infrastructure_master.csv:

- To edit below mentioned infrastructure details 
  ```
  nano infrastructure_master.csv
  ```

- Save and Close the file

- Based on the number of udise attributes required by the state, configure the udise_config.csv file by filling the required fields in the file udise_config.csv:

- To edit below mentioned UDISE details 
  ```
  nano udise_config.csv
  ```

- Save and Close the file

- For more information to configure the weights & columns for udise/infrastucture, please refer operational document.

- Update the diksha parameters(api_url,token,encryption key,dataset name channel_id,org_id) in the development/python/cQube-raw-data-fetch-parameters.txt

- Give the following permission to the install.sh file

  ```
  chmod u+x install.sh
  ```

- Install cQube using the non-root user with sudo privilege

- Configuration filled in config.yml will be validated first. If there is any error during validation, you will be prompted with the appropriate error message and the installation will be aborted. Refer the error message and solve the errors appropriately, then re-run the installation script sudo ./install.sh

- Start the installation by running install.sh shell script file as mentioned below:

  ``` 
  sudo ./install.sh
  ```

Once installation is completed without any errors, you will be prompted the following message. CQube installed successfully!!

# Base Installation steps

## Base Installation steps

## cQube\_Base Installation:

* open Terminal
* Navigate to the directory where cQube\_Base has been downloaded or cloned

  ```text
  cd cQube_Base/
  git checkout release-3.1
  ```

* Copy the config.yml.template to config.yml

  ```text
  cp config.yml.template config.yml
  ```

* Edit using `nano config.yml`
* If you are opting for storage\_type as s3. Copy the aws\_s3\_config.yml.template to aws\_s3\_config.yml

  ```text
  cp aws_s3_config.yml.template aws_s3_config.yml
  ```

* Edit using `nano aws_s3_config.yml`
* If you are opting for storage\_type as local. Copy the local\_storage\_config.yml.template to local\_storage\_config.yml

  ```text
  cp local_storage_config.yml.template local_storage_config.yml
  ```

* Fill the configuration details for the below mentioned list in config.yml \(\* all the values are mandatory\)
* cQube\_Base installation process installs the components in a sequence as mentioned below:
  * Installs Ansible
  * Installs Openjdk
  * Installs Python, pip and flask
  * Installs PostgreSQL
  * Installs NodeJS
  * Installs Angular and Chart JS
  * Installs Apache Nifi
  * Installs Keycloak
  * Installs Grafana
  * Installs Prometheus and node exporter
* Save and Close the file

### Configuration of infrastructure attributes and UDISE data indices, metrics:

* Based on the number of infrastructure attributes required by the state, configure the infrastructure report by filling the required fields in the file infrastructure\_master.csv:
* To edit below mentioned infrastructure details

  ```text
  nano infrastructure_master.csv
  ```

* Save and Close the file
* Based on the number of UDISE attributes required by the state, configure the udise\_config.csv file by filling the required fields in the file udise\_config.csv:
* To edit below mentioned UDISE details

  ```text
  nano udise_config.csv
  ```

* Save and Close the file
* For more information to configure the weights & columns for udise/infrastucture, please refer operational document.
* Update the diksha parameters\(api\_url,token,encryption key,dataset name channel\_id,org\_id\) in the development/python/cQube-raw-data-fetch-parameters.txt
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

Once installation is completed without any errors, you will be prompted the following message. **CQube installed successfully!!**


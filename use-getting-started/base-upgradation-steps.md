# Base Upgradation steps

### cQube\_Base Upgradation:

* Open Terminal
* Navigate to the directory where cQube has been downloaded or cloned

  ```text
  cd cQube_Base/
  git checkout release-3.1
  ```

* Copy the config.yml.template to config.yml cp config.yml.template config.yml
* If you are opting for storage\_type as s3. Copy the aws\_s3\_upgradation\_config.yml.template to aws\_s3\_upgradationconfig.yml 

  ```text
  cp aws_s3_upgradation_config.yml.template aws_s3_upgradation_config.yml 

  ```

* If you are opting for storage\_type as local. Copy the local\_storage\_upgradation\_config.yml.template to local\_storage\_upgradation\_config.yml 

  ```text
  cp local_storage_upgradation_upgradation_config.yml.template local_storage_upgradation_config.yml
  ```

* This script will update the below cQube components:
  * Creates & Updates table,sequence,index in postgresql database
  * Updates NodeJS server side code
  * Updates Angular and Chart JS client side code
  * Updates & configure Apache Nifi template
  * Updates & configure Keycloak
* Fill the configuration details in upgradation\_config.yml \(\* all the values are mandatory, make sure to fill the same configuration details which were used during installation\)
* Edit using nano upgradation\_config.yml
* Save and Close the file
* Give the following permission to the upgrade.sh file

  chmod u+x upgrade.sh

* Run the script to update cQube using the non-root user with sudo privilege

  Start the upgradation by running upgrade.sh shell script file as mentioned below:

  ```text
  sudo ./upgrade.sh
  ```

Configuration filled in upgradation\_config.yml will be validated first. If there is any error during validation, you will be prompted with the appropriate error message and the upgradation will be aborted. Refer the error message and solve the errors appropriately. Restart the upgradation process `sudo ./upgrade.sh`

Once upgradation is completed without any errors, you will be prompted the following message.  **CQube upgraded successfully!!** 


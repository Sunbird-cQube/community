# Workflow Upgradation steps

* Open Terminal
* Navigate to the directory where cQube has been downloaded or cloned

  ```text
  cd cQube_Workflow/work_deploy
  git checkout release-3.6
  ```

  **Use cases folder structure**

  * education\_usecase
  * education\_usecase\_theme2

    **If user opting for education\_usecase open the education\_useacse folder**

* Copy the config.yml.template to config.yml 

  ```text
  cp config.yml.template config.yml
  ```

* Edit using `nano config.yml`
* Enable data sources as true or false in datasource\_config.yml and datasource\_validation.sh, in datasource\_validation.sh  an array of mandatory values should be same as datasource\_config.yml file values. 

  **If user opting for education\_usecase\_theme2 open the education\_usecase\_theme2 folder**

* Copy the config.yml.template to config.yml 

  ```text
  cp config.yml.template config.yml
  ```

* Edit using `nano config.yml`
* Enable data sources as true or false in datasource\_config.yml and datasource\_validation.sh, in datasource\_validation.sh  an array of mandatory values should be same as datasource\_config.yml file values.
* If the user opting for new data source.  should add new data source name inside the datasource\_config.yml file and datasource\_validation.sh array list.
* Fill the configuration details for the below mentioned list in config.yml \(\* all the values are mandatory\)
* This script will update the below cQube components:
  * Creates & Updates table, sequence, index in PostgreSQL database
  * Updates NodeJS server side code
  * Updates Angular and Chart JS client side code
  * Updates & configure Apache NIFI template
  * Updates & configure Keycloak
* Fill the configuration details in config.yml \(\* all the values are mandatory, make sure to fill the same configuration details which were used during installation\)
* Edit using `nano config.yml`
* Save and Close the file
* Give the following permission to the upgrade.sh file

  ```text
  chmod u+x upgrade.sh
  ```

* Run the script to update cQube using the non-root user with sudo privilege

  Start the upgradation by running upgrade.sh shell script file as mentioned below:

  ```text
  sudo ./upgrade.sh
  ```

Configuration filled in config.yml will be validated first. If there is any error during validation, you will be prompted with the appropriate error message and the upgradation will be aborted. Refer the error message and solve the errors appropriately. Restart the upgradation process `sudo ./upgrade.sh`

Once upgradation is completed without any errors, you will be prompted the following message. **CQube upgraded successfully!!**


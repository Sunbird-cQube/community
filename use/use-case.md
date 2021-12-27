### Process Document for adding new use case to cQUBE

##### **Objective:** 
###### To provide high level view on adding new data source to cQube and maintenance
##### 1. **Prerequisite:** All the cQube prerequisites remains same 
      1.1 3 VMs
      1.2 Domain Name
      1.3 VPN service
      1.4 The team which is creating the use case should know the following
          1.4.1 Ansible (Shell scripting)
          1.4.2 Postgresql
          1.4.3 NIFI
          1.4.4 NodeJs
          1.4.5 AngularJs
##### 2. **Design for new use case:**
      2.1 Create folders in git development environment (PUT URL)
          2.1.1 NIFI processors
          2.1.2 Postgres queries
          2.1.3 Ansible
          2.1.4 NodeJS
          2.1.5 Angular
          2.1.6 APIs
##### 3. **Steps for development of new use case**
      3.1 Completely new use case
          3.1.1 Create git structure
          3.1.2 Create required files (scripts)
          3.1.3 Place into git
          3.1.4 Merge it with main cQube branch
      3.2 Hybrid use case (existing + new data sources)
          3.2.1 Create git structure
          3.2.2 Create required files (scripts)
          3.2.3 Create new data source metrics
          3.2.4 Create new data source UIs
          3.2.5 Place into git
          3.2.6 Merge it with main cQube branch
      3.3 Copy of current cQube in case of UI changes
          3.3.1 Create git structure
          3.3.2 Create required files (scripts)
          3.3 3 Create new data source UIs
          3.3.4 Place into git
          3.3.5 Merge it with main cQube branch
##### 4. **Integration with cQube**
      4.1 Scenario 1 - Contribute to cQube
      4.2 Scenario 2 - Maintain standalone repository(separate use case)
##### 5. **Upgradation** 
      5.1 S1
      5.2 S2
##### 6. **Risk and Challenges**

##### **Creating new use case in cQube - cQube base is installed and we have to create new use case**

- Understand the data sources
- Create metrics 
  -  Define visualizations
- Create new use case in cQube
  -  Create required folders
  -  Create required NIFI processors 
  -  Create required Postgres Tables
  -  Create required UIs
  -  Create required NODE & Angular scripts
  -  Update ansible for installation and upgradation of cQube
- Integrate with cQube
  -  How to integrate?
- Install new use case
- Create new  use case folder(test1_usecase) 
- Inside the use case folder create required below files
- validation_scripts

##### 1. backup_postgre.sh 
This script is used for taking backup of postgre     database for future validation
      1.1 Please find the below steps for develop backup_postgre.sh:
        step1: Need base directory where the cQube base is installed
        step2: Database details
      1.2 Backup command: 
        pg_dump -h localhost -U $db_user -F t $db_name >    $base_dir/cqube/postgres/backups/date +%Y%m%d%H%M$bk_db_name.tar
##### 2. Install_aws.sh
This script is used for AWS Command Line Interface with   the common features and calling patterns. Learn how to install the AWS CLI on your Windows, Linux. 
      2.1 please find the below steps for develop Install_aws.sh
	  step1: https://s3.amazonaws.com/aws-cli/awscli-bundle.zip 
	  step2: "Configuring aws cli ..."
       ./awscli-bundle/install -i /usr/local/aws -b /usr/local/bin/aws  > /dev/null 2>&1
      ./awscli-bundle/install -b ~/bin/aws  > /dev/null 2>&1
      ./awscli-bundle/install -h  > /dev/null 2>&1
##### 3. state_codes
state code is used to differentiate between the states
      example: gujarat, OD etc
##### 4. validate_static_datasource.sh
This script is used for datasource status in postgre
     4.1 please find the below steps for develop validate_static_datasource.sh
     step1: Need to validate static date sources, current data sources and data source config
	 step2: Need to compare current data source with data source config
##### 5 .version - it used for manage the versions
      5.1 please find the below steps for .version
	  step1: which version need to be installed that version installed 
      ex: cqube_workflow_version: "3.1"
##### 6. config.yml.template
This script is used for cQube configuration parameters
      6.1 please find the below steps for develop config.yml.template
      step1: first need to fill the all the necessary parameters
      Ex: base_dir: /opt
      State_code:
      Static_datasource
##### 7. Datasource_config.yml
This script is used for datasource enabling and disabling
      7.1 please find the below steps for develop datasource_config.yml
      step1: use case necessary data sources should be enabled
      step2: user needed data sources can able to add  
##### 8. Datasource_Validation.sh
This script is used for validating the data sources
      8.1 please find the below steps for develop datasource_validation.sh
      step1: need to validate needed data sources which all are added in datasource_config.yml
##### 9. Install.sh
This script is used for running installation of ansible script
      9.1 please find the below steps for develop install.sh
	  step1: Installing the ansible tool
	  step2: checking the existence of config.yml
	  step3: calling validate.sh and datasource_validation.sh
	  step4: checking the existence ansible.cfg file
      step5: calling the ansible playbook to install the cQube workflow  
##### 10. Install_ui.sh
This script is used for running installation of angular related ansible code
      10.1 please find the below steps for develop install_ui.sh
	  step1:calling angular related installation ansible playbooks
##### 11. Memory_config.yml
This script is used for memory configuration parameters
##### 12. Requirement.txt -
This requirements.txt file is used for specifying what python packages are required to run the project you are looking at. Typically the requirements.txt file is located in the root directory of your project
##### 13. State_List:
This is used for listing the state names
##### 14. Update_ui.sh - This is script is used for upgradation of angular related ansible code
       14.1 please find the below step for develop update_ui.sh
       step1:calling angular related upgradation ansible playbook
##### 15. Upgradation_config.yml.template - This script is used for upgradation of cQube configuration parameters
       15.1 please find the below step for develop upgradation_config.yml.template
      step1:first need to fill the all the necessary parameters
      Ex: base_dir: /opt
      State_code:
      Static_datasource
##### 16. Upgaradation_Validate.sh- This script is used for validating the upgradation of cQube configuration variables
       16.1 please find the below step for develop upgaradation_validate.sh
       step1:validating the variables which are all added in upgradation_config.yml
##### 17. Upgrade.sh - This script is used for upgrading the ansible code
       17.1 please find the below step for develop upgrade.sh
	   step1:checking the existence of upgradtion_config.yml
	   step2:calling the upgradation of validation scripts
       step3: calling the upgradation ansible playbooks to upgrade cQube workflow 
##### 18. Validate.sh - This script is used for validating the installation of cQube configuration variables
       18.1 please find the below step for develop validate.sh
       step1: validating the variables which all are added in config.yml.template to install the cQube workflow.
    



      
      
      
      
      
      
      
      
	 
      
        
    


      
      
          
      
          
          
          
          
          

## New Use-Case Creation

#### New use case creation flow:
- Install cQube base and workflow
- Create the nifi flow, modify the postgres db and ui pages.
- Keep those code changes in new use case directory
- Modify the ansible and shell scripts to deploy the newly created use case.

First install the cQube Base and Workflow by following the installation steps. 

### Development:

#### NIFI and Postgres common setup:

`Note: ./development/datasource/ is a common directory for all usecases.` 
- For any usecase, under development/datasource new datasource has to be created
`cd cQube_Workflow/development/datasource`
- Create a directory for new datasource
 `mkdir <new_datasource_name> && cd <new_datasource_name>`

#### Nifi: 
- For new usecase, create a dataflow according to the requirement. After creating the dataflow create a template of it and download it. 
- Create a nifi directory.
`mkdir nifi`
- Note: nifi directory is used inside ansible. Make sure to create the same name else ansible script has to be changed accordingly.
- Keep the new_data_source_transformer.xml (template file) under nifi directory.
- Create the parameters file with .txt extension (Eg.new_data_source_parameters.txt ) which contains the parameters and its values required by the dataflow. Place the txt file under nifi directory.  

#### Postgres: 
- For new usecase depends on the requirement new tables can be created in cqube database. Create the postgres queries to calculate the metrics as required. 
- Create a postgres directory.
`mkdir postgres`
- `Note: postgres directory is used inside ansible. Make sure to create the same name else ansible script has to be changed accordingly.`
- Write a sql file new_data_source_table.sql which should contain all the DDL statements  and new_data_source_queries.sql file to create metrics which should contain all the DML statements.
- Create a new_data_source_queries.json file which should contain the output/report queries. This file should placed under nifi directory which is parallel to postgres directory as mentioned in below example.
Eg: 
```
./development
    /datasource
        /attendance
            /nifi
                /attendance_parameters.txt
                /attendance_transformer.xml
                /attendance_queries.json
            /postgres
                /attendance.sql
                /attendance_queries.sql
        /new_data_source
            /nifi
                /new_data_source_parameters.txt
                /new_data_source_transformer.xml
                /new_data_source_queries.json
            /postgres
                /new_data_source_table.sql
                /new_data_source_queries.sql
```
#### Angular:
- All angular related code will be located in cQube_Workflow/development/ui
`cd cQube_Workflow/development/ui`
- admin_ui
- dashboard_ui
- admin_ui directory contains all admin related ui code and it is common for all usecases.
- dashboard_ui directory contains usecase directories with all reports related ui code inside it. 
`cd dashboard_ui` 

##### education_usecase:
- Copy the existing usecase directory as a new usecase name.
Eg. `cp -R education_usecase <new_demo_usecase>`
    - Note: for documentation purpose new use case is named as new_demo_usecase. In real scenario, please change it.
```
    development
        /ui
            /admin_ui
            /dasboard_ui
                /education_usecase
                    /client_side
                /new_demo_usecase
                    /client_side
```
##### New_demo_usecase:

###### To create new sub menu:
 ```
 demo_usecase
    /client_side
         /src/app/container/home/home-container.html
```    
                                                 
###### To create cards under Sub menu:
 ```
 demo_usecase
    /client_side        
        /src/app/dashboard/group-dashboard
```
###### To create routes for cards:
```
demo_usecase
    /client_side        
        /src/app/dashboard/dashboard-module.module.ts
```
###### To create new report:
```
demo_usecase
    /client_side        
        /src/app/reports
```
###### To add new api service:
```
 demo_usecase
    /client_side        
        /src/app/service
```        

###### To add new state coordinate:
```
 development
    /ui
        /dasboard_ui
            /maps
```            
Include the newly added state code in below file
```
demo_usecase
    /client_side
      /src/assets/config.json
```      
      
#### Nodejs: 
- Nodejs is used to read the json file  path and send it to clientside(angular) through apis    
- All nodejs related code will be located in cQube_Workflow/development/node_api
`cd cQube_Workflow/development/node_api`
admin_api
dashboard_api
```
development
    /node_api
        /admin_api
            /dashboard_api
```
- admin_api directory contains all admin related server code and it is common for all usecases.
- dashboard_api directory contains all reports related server code inside it. 
`cd dashboard_api`
 

- To read new data path for new report:-    
```
dashboard_api
    /server_side/src/api/controller
```
- To add routes for newly added controller:-
```
 dashboard_api
    /server_side/src/api/router.js
```
### Workflow_deploy:

To create the new usecase deployment section, go to `cd cQube_Workflow/workflow_deploy directory.`
- Ansible
- education_usecase

#### Ansible:
This directory contains all ansible playbooks to deploy the cQube workflow. Main files and directories to consider while creating the new use case are below.
- ./roles
- ./install.yml
- ./upgrade.yml

##### roles:
This directory contains all the cQube components’ and datasources’ configurations for the usecase.<br>
For new datasource:<br>
If any new data source added, create a role in the ansible directory with the new data source name. Create playbooks inside it to run the newly created nifi and postgres datasource related scripts and queries.
```  
cQube_Workflow/workflow_deploy/ansible/roles/new_demo_datasource
/tasks
	/nifi_new_demo_datasource.yml
	/postgre_new_demo_datasource.yml
	/main.yml
          /templates  
          /vars
```


##### Install.yml & upgrade.yml:
- These are the ansible playbooks used to call the ansible roles while installation and upgradation of cQube. If any new ansible roles are added make sure its been called inside install.yml and upgrade.yml. 

#### education_usecase:
- Copy the existing usecase directory as a new usecase name.
Eg. `cp -R education_usecase <new_demo_usecase>`
    Note: for documentation purpose new use case is named as new_demo_usecase. In real scenario, please change it.
#### New_demo_usecase:

 Inside the new_demo_usecase main files and directories to consider while creating the new use case.
- datasource_config.yml
- datasource_validate.sh
- config.yml.template
- validate.sh
- Upgradation_validate.sh
- Install.sh
- Upgrade.sh
- Install_ui.sh
- update_ui.sh

Note: `for every *config.yml file there will be validation scripts to validate the values which are entered in config files.` 
    
##### datasource_config.yml:
- This file contains all datasources list and will be used to enable/disable the datasources. We can add or remove the required datasources for the new use-case.

##### datasource_valiate.sh: 
- This script will validate the values entered in datasource_config.yml file. Add or remove the  required datasources. Below are the steps to add a new validation for newly added variable in datasource_config.yml
Add the newly declared variable name in `declare -a arr`
Create the new function to validate the user provided value
Create a case statement for the variable and call the function inside it. 

##### Config.yml(.template):
- This is a template of config.yml. This file will be copied as config.yml while installation or upgradation. It contains the configuration variables for the usecase. Add or remove the required configuration variables and required comments. Make sure to add the new variables in validate.sh and upgradation_validate.sh to validate the user entered values .

##### Validate.sh:
- This script is used to validate all the values filled in config.yml file while doing the installation of cQube. Add or remove the required variable validations. Below are the steps to add a new validation for newly added variable in config.yml.template.
- Add the newly declared variable name in `declare -a arr`
Create the new function to validate the user provided value
Create a case statement for the variable and call the function inside it. 

##### Upgradation_validate.sh:
- This script is used to validate all the values filled in config.yml file. Add or remove the required variable validations. Below are the steps to add a new validation for newly added variable in config.yml.template.
- Add the newly declared variable name in `declare -a arr`
Create the new function to validate the user provided value
Create a case statement for the variable and call the function inside it. 

##### Install.sh:
- This script will install cQube workflow by running the validation scripts to validate the given config values and ansible playbooks and roles. Ansible will run only the tasks which is tagged as ‘install’ tag for installation. 
- Make sure to replace the old use case name with the new use case name in extra-vars parameter as shown in example below.
Eg: `--extra-vars "usecase_name=new_demo_usecase"` 

##### Upgrade.sh:
- This script will update the cQube workflow by running the validation scripts to validate the given config values and ansible playbooks and roles. Ansible will run only the tasks which is tagged as ‘update’ tag for upgradation. 

- Make sure to replace the old use case name with the new use case name in extra-vars parameter as shown in example below.
    Eg: `--extra-vars "usecase_name=new_demo_usecase"`

##### Install_ui.sh:
- This script will install the UI part code and it is being called inside install.sh script. Make sure to replace the old use case name with the new use case name in extra-vars parameter as shown in example below.
    Eg: `--extra-vars "usecase_name=new_demo_usecase"`

##### Update_ui.sh:
- This script will update the UI part code and it is being called inside upgrade.sh. Make sure to replace the old use case name with the new use case name in extra-vars parameter as shown in example below.
    Eg: `--extra-vars "usecase_name=new_demo_usecase"`



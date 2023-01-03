# Workflow Installation

* Open Terminal
* Navigate to the directory where cQube\_Workflow has been downloaded or cloned

```
  - cd cQube_Workflow/work_deploy/
  - git checkout release-3.3
```

* Configuration of infrastructure attributes, indices and metrics
  * Based on the number of infrastructure attributes required by the state, configure the infrastructure report by filling the required fields in the infrastructure\_master.csv file
  * Edit the file in the below mentioned location

```
  - cd cQube_Workflow/development/datasource/infra/postgres/
  - nano infrastructure_master.csv
  - save and close the file
```

* Based on the modification of infrastructure\_master.csv modify the infra\_parameters.txt file also.
* Edit the file in the below mentioned location

```
  - cd /cQube_Workflow/development/datasource/infra/nifi/
  - nano infra_parameters.txt
  - save and close the file
```

* Configuration of UDISE attributes, indices and metrics
  * Based on the number of udise attributes required by the state, configure the udise\_config.csv file by filling the required fields in the file udise\_config.csv:
  * Edit the file in the below mentioned location

```
   - cd cQube_Workflow/development/datasource/udise/postgres/
   - nano udise_config.csv
   - save and close the file
```

* For more information to configure the weights & columns for udise/infrastructure, please refer to the operational document.
*   **Configuration of diksha\_parameters.txt**

    **Update the diksha parameters**(diksha\_api\_progress\_exhaust\_api\_token, diksha\_api\_progress\_exhaust\_batch\_id\_list, diksha\_api\_progress\_exhaust\_dataset, diksha\_api\_progress\_exhaust\_encryption\_key, diksha\_api\_progress\_exhaust\_x\_channel\_id, diksha\_api\_summary\_roll\_up\_api\_token, diksha\_api\_summary\_roll\_up\_x\_channel\_id,diksha\_api\_url\_progress\_exhaust, diksha\_api\_url\_summary\_roll\_up, diksha\_tpd\_encryption)

    **File directory:**

```
   - cd cQube_Workflow/development/datasource/diksha/nifi/
   - nano diksha_parameters.txt
   - save and close the file
```

* Copy the config.yml.template to config.yml in the cQube\_Workflow/work\_deploy/education\_usecase/

```
  - cd cQube_Workflow/work_deploy/education_usecase/
  - cp config.yml.template config.yml
```

* Edit the config.yml file using the below command

```
  - nano config.yml
```

* Fill the below details in the config.yml file

```
# cQube Installation configuration parameters
# ALL VARIABLES ARE MANDATORY.
# PLEASE FILL THOSE BEFORE RUNNING CORRESPONDING STEPS.
#NOTE: Please fill the value with a space between ":" and the value. 
#Example-   `system_user_name: ubuntu`
base_dir: /opt  # provide the absolute path where cqube needs to be installed and served. Eg. /opt  ( in this case cqube will be installed under /opt/cqube)
state_code:        # Enter the 2 character (upper case) state code for which cQube is being deployed. Please refer to the state_list file. 
# Diksha Columns
#Enter the value as `true`,  if content_gradelevel & collection_gradelevel columns are available.
#Enter the value as `false`, if content_gradelevel & collection_gradelevel columns are not available.
diksha_columns: false                    # Enter true or false. 
static_datasource:                       # Enter udise or state
management:                              # Enter the management
session_timeout: 7D      # enter the value between 30 Minutes to 3650 Days. Eg. For minutes `60M`  Eg. For days `15D`. Make sure M and D should be mentioned upper case.
map_name: leafletmap              # Enter the map_name ( mapmyindia or googlemap or leafletmap )
google_api_key: remove_this_key_value     # Enter the google_api_key  here (if you selected map_name as googlemap replace `remove_this_key_value` with the actual googlemaps api key )
theme:                     # Enter the theme ( theme1 or theme2 or theme3 )
slab1:                  #Enter slab1 value between 1-100 ( eg: slab1: 33  )
slab2:                  #Enter slab2 value range is greater than slab1 and between 1-100 ( eg: slab2: 33-60 ) 
slab3:             #Enter slab3 value range is greater than slab2 and between 1-100 ( eg: slab3: 60-75 ) 
slab4:           #Enter slab4 value is greater than or equal to slab3 last value between 1-100 ( eg: slab4 75 ) 
```

* Give the following permission to the install.sh file and Start the installation by running install.sh shell script file as mentioned below

```
  - chmod u+x install.sh
  - sudo ./install.sh
```

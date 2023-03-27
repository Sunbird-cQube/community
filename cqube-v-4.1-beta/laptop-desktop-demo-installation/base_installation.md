### Steps for Base Installation at Laptop/Desktop
- Open Terminal
- Navigate to the directory where cQube_Base has been downloaded or cloned
```text
  - cd cQube_Base/
  - git checkout release-3.3
```
- Copy the config.yml.template to config.yml
```text
  - cp config.yml.template config.yml
``` 
- Edit using the command
```text
  - nano config.yml
``` 
- Fill the below details in the config.yml file
```text
# cQube Installation configuration parameters
# ALL VARIABLES ARE MANDATORY.
# PLEASE FILL THOSE BEFORE RUNNING CORRESPONDING STEPS.
#NOTE: Please fill the value with a space between ":" and the value. 
#Example-   `system_user_name: ubuntu`
system_user_name:          # Non-root username with sudo privileges. To find the username run `whoami` in the same server terminal.
base_dir: /opt             # provide the absolute path where cqube needs to be installed and served. Eg. /opt  ( in this case cqube will be installed under /opt/cqube)
#Database variables naming convention, the variable length should be between [3-63] characters and should contain upper/lower characters, it should start with _ or lower or upper characters.
# Database Parameters
db_user: cqube_db_user   # Create your own username for the cQube database
db_name: cqube_db     # Enter your own database name for the cQube database
db_password:         # Create your own password for the cQube database, password should contain at least 1 lower,upper,number,special character (only @!%^*? allowed) and minimum 8 characters
read_only_db_user:      # Create your own username for the read only access of cQube database
read_only_db_password:     # Create your own password for the read only user, password should contain at least 1 lower,upper,number,special character (only @!%^*? allowed) and minimum 8 characters
storage_type: local              # enter `s3` or `local`
# Please fill api_endpoint where the node server will be accessible.
# Node server will be running on 3000 ports using local ip.
# If you are using a reverse proxy and using an SSL certificate, please enter the right api endpoint url.
mode_of_installation: localhost         # enter `localhost` for demo installation in a single local machine, or `public` for installation in a server
api_endpoint: localhost          # enter domain name if mode_of_installation is `public` ( Example: cqubeprojects.com ), if mode_of_installation is `localhost` then api_endpoint should be `localhost`
local_ipv4_address:         # enter the private ip of this server. To find the ip address. Use `ip addr` or `ifconfig`
vpn_local_ipv4_address:      # enter the private ip of the vpn server. To find the ip address. Use `ip addr` or `ifconfig`
keycloak_adm_user:      # enter the keycloak admin user to be created 
keycloak_adm_passwd:      # enter the keycloak admin password. password should contain at least 1 lower,upper,number,special character (only @!%^*? allowed)  and minimum 8 characters
report_viewer_config_otp:  # enter true or false to enable OTP authentication for all users 
```
- Copy the local_storage_config.yml.template to local_storage_config.yml
```text
  - cp local_storage_config.yml template local_storage_config.yml
```
- Edit the local_storage_config.yml file using the below command
```text
  - nano local_storage_config.yml
```
- Fill the below details in the nano local_storage_config.yml file
```text
# cQube Installation configuration parameters
# ALL VARIABLES ARE MANDATORY.
# PLEASE FILL THOSE BEFORE RUNNING CORRESPONDING STEPS.
#NOTE: Please fill the value with a space between ":" and the value. 
# local_storage_directories
# User need to create three directory for input, output and emission
input_directory: /tmp/           # Enter the input directory path followed by "/". Example: /home/ubuntu/input/
output_directory: /tmp/           #Enter the output directory path followed by "/". Example: /home/ubuntu/output/
emission_directory: /tmp/       #Enter the emission directory path followed by "/". Example: /home/ubuntu/emission/
```
- Give the following permission to the install.sh file
```text
  - sudo chmod u+x install.sh
```
- Start the cQube base installation
```text
  - sudo ./install.sh
```

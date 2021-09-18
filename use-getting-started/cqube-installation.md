# cQube Installation

The cQube product can be installed in a two-step installation process. cQube installation package is divided into below 2 components 

* cQube base installation
* cQube workflow Installation

**cQube base installation:** The cQube base installation installs the complete cQube stack, which includes Ansible automation scripts to install Java, Python, NIFI, Angular, ChartJS, Leaflet and PostgreSQL installations. All the softwares will be installed without any data or data processing units. S3 emission data, S3 input bucket, S3 output bucket and the remaining S/W configurations will be taken care by cQube base installation.   


**cQube Workflow installation:** The cQube Workflow installation is the top-up layer of the cQube base installation. Once the cQube base installation is completed, Admin has to start the cQube workflow installation. 

Based on the data source configuration the following are setup

* Database tables will be created at PostgreSQL from the relevant data source sql files. 
* NIFI data processor groups will be created by using the relevant data source nifi  templates and the parameters will be updated based on the configurations set. 
* The reports will be shown for the enabled data source in angular dashboard. 


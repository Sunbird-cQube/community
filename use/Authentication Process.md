# Login Process

![User Login flow ](../../.gitbook/assets/User%20Authentication%20Flow%20Chart.png)

cQube supports two types of Login mechanisms

* cQube Login
* State Login

**cQube Login**

cQube uses internal (Keycloak) APIs for authentication and authorizaion of  users

   **Types of Users**

    - Admin
    - report_viewer
    - emission_user

**Description of the Admin**
- User with Admin role, User can access all the reports and admin features like creating users,viewing the data from storage layer etc..
for detailed admin feature refere this (https://cqube.sunbird.org/use/admin-features)


**Description of the report_viewer**
- User with report_viewer role, can access all the reports.

**Description of the emission_user**
- User with emission_user role, can upload the files to cQube via Emission API.




**State Login**

cQube uses state Login API for authentication and authorizaion of users

**Types of Users**
- Admin
- report_viewer 
- report_viewer with level based access



**Description of the report_viewer**
- User with report_viewer role, can access all the reports.


**Description of the Level based access Feature**
- cQube state login users can  access the reports as per the user levels. 
- On click of pat report  user can be able to see their respective level of data.
- The Blocks, Clusters and Schools buttons would be disabled for the all the users accept the state level users.
- A button would be provided as "Access Your location'. When the user clicks on the button then the user may able to see their particular location and the lower levels of their locations.
- The upper level select options will be disabled for the users. The user may get only the lower level location selection which are belongs to the user location.

The current Access levels we have in cQube are,
State level users,
District level users,
Block level users,
cluster level users,
school level users

For example, If the user belongs to a district then the user can be able to access only their district information as well as the lower levels of their districts.
If the user belongs to a Block level then the user may be able to see their block level information as well as the lower levels of their block.



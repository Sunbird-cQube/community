---
description: 'Release Version 1.0,  June 2020'
---

# cQube - Release Notes V1.0

1. **Objectives of the cQube release 1.0**

cQube V 1.0 release, as a single step installable product, provides the capability of predefined actionable visualizations and downloadable reports along with basic admin functionalities.

In the V1.0 release, cQube can ingest data related to student attendance, assessment and school inspection. cQube processes these datasets to produce predefined student attendance and assessment along with school inspection visualizations. Along with the visualizations, downloadable reports are available for further analysis and focused action.

1. **Scope**

cQube product release features and issues are described in this version 1.0 of the document​.

1. **Summary of the Product Features**

This document contains information on the following features of the cQube product:

1. One step Installation
2. Data emission API
3. Role based login for Admin, Report viewer and Emission users
4. Change Password
5. Create New User
6. Student Attendance Report
7. CRC App data Report
8. Semester Assessment Report
9. **Compatibility:**

* cQube version 1.0 works on ubuntu 18 as of now and will be made compatible with the ubuntu version 20 in the next release.
* cQube 1.0 works on Firefox and google chrome.
* cQube works on android mobile devices, all functions work on the mobile devices except hovering on the dots \(district, blocks and clusters, in the reports.

1. **Description of the Product Features**

**One step Installation**

[CQB-155](https://project-sunbird.atlassian.net/browse/CQB-155)

| Sl No. | Feature | Description | Roles Impacted |
| :--- | :--- | :--- | :--- |
| 1 | cQube single command installation | All the cQube software will be downloaded and installed using a single command. | Admin users |
| 2 | cQube auto configuration | The cQube configuration will be provided automatically after the installation | Admin users |
| 3 | Workflow | Data flow process will initiate once the data emits to S3 emission bucket | Admin, Emission users |

**Data emission API Creation**

[CQB-170](https://project-sunbird.atlassian.net/browse/CQB-170)

<table>
  <thead>
    <tr>
      <th style="text-align:left">Sl No.</th>
      <th style="text-align:left">Feature</th>
      <th style="text-align:left">Description</th>
      <th style="text-align:left">Roles Impacted</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">1</td>
      <td style="text-align:left">API Access</td>
      <td style="text-align:left">Calling of the cQube&#x2019;s data emission API to connect with cQube</td>
      <td
      style="text-align:left">Emission users</td>
    </tr>
    <tr>
      <td style="text-align:left">2</td>
      <td style="text-align:left">One-time URL &amp; Data emission</td>
      <td style="text-align:left">
        <p>One-time URL will be created,</p>
        <p>data will be emitted through the one-time URL</p>
      </td>
      <td style="text-align:left">Emission users</td>
    </tr>
    <tr>
      <td style="text-align:left">3.</td>
      <td style="text-align:left">Data</td>
      <td style="text-align:left">Data will be emitted in the sequential process for the first time there
        after being emitted in parallel.</td>
      <td style="text-align:left">Emission users</td>
    </tr>
  </tbody>
</table>

**Role based Login**

[CQB-192](https://project-sunbird.atlassian.net/browse/CQB-192)

<table>
  <thead>
    <tr>
      <th style="text-align:left">Sl No.</th>
      <th style="text-align:left">Feature</th>
      <th style="text-align:left">Description</th>
      <th style="text-align:left">Roles Impacted</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">1</td>
      <td style="text-align:left">Role based login functionality</td>
      <td style="text-align:left">
        <p>After User authentication, users can access the menus and functionalities
          according to his/her role.</p>
        <p>Admin, Report viewer and Emission user roles have been covered for this
          release</p>
      </td>
      <td style="text-align:left">All users</td>
    </tr>
    <tr>
      <td style="text-align:left">2</td>
      <td style="text-align:left">Admin user role functionality</td>
      <td style="text-align:left">
        <p>Admin users can access the Reports</p>
        <p>Admin Users can create new users.</p>
      </td>
      <td style="text-align:left">Admin users</td>
    </tr>
    <tr>
      <td style="text-align:left">3</td>
      <td style="text-align:left">Report viewer role</td>
      <td style="text-align:left">Report viewer users can access Student attendance report, Semester report
        and CRC report</td>
      <td style="text-align:left">Report viewer users</td>
    </tr>
    <tr>
      <td style="text-align:left">4</td>
      <td style="text-align:left">Emission users</td>
      <td style="text-align:left">Emission users will access the emission API</td>
      <td style="text-align:left">Emission users</td>
    </tr>
  </tbody>
</table>

**Change Password**

[CQB-216](https://project-sunbird.atlassian.net/browse/CQB-216)

<table>
  <thead>
    <tr>
      <th style="text-align:left">Sl No.</th>
      <th style="text-align:left">Feature</th>
      <th style="text-align:left">Description</th>
      <th style="text-align:left">Roles Impacted</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">1</td>
      <td style="text-align:left">Changing of password</td>
      <td style="text-align:left">
        <p>Users will be able to change his/her password using this functionality.</p>
        <p>Post login user has access to the user interface where the current password
          can be changed and a new password can be created</p>
      </td>
      <td style="text-align:left">All users</td>
    </tr>
  </tbody>
</table>

**Create New User**

[CQB-218](https://project-sunbird.atlassian.net/browse/CQB-218)

| Sl No. | Feature | Description | Roles Impacted |
| :--- | :--- | :--- | :--- |
| 1 | Creation of new cQube user | Admin users can create a new cQube user. With the user interface provided, a single user can be created at a time in this release. | Admin users |

**Student Attendance Report**

[CQB-47](https://project-sunbird.atlassian.net/browse/CQB-47), [CQB-57](https://project-sunbird.atlassian.net/browse/CQB-57), [CQB-60](https://project-sunbird.atlassian.net/browse/CQB-60), [CQB-67](https://project-sunbird.atlassian.net/browse/CQB-67), [CQB-58](https://project-sunbird.atlassian.net/browse/CQB-58), [CQB-72,](https://project-sunbird.atlassian.net/browse/CQB-72) [CQB-123](https://project-sunbird.atlassian.net/browse/CQB-123), [CQB-59](https://project-sunbird.atlassian.net/browse/CQB-59)

| Sl No. | Feature | Description | Roles Impacted |
| :--- | :--- | :--- | :--- |
| 1 | Map Report | State, District, Block, Cluster, and school level Student attendance percentages are displayed in the Maps based on the user’s selection. | Admin, Report viewer users |
| 2 | Color Gradient | The color gradient on the map shows the attendance percentage levels of the students. Red shows lowest attendance and green shows highest attendance. | Admin, Report viewer users |
| 3 | Drill Down Functionality | A hierarchical drill down functionality from state level to school level is available and can be accessed by clicking on the individual dots in the map. | Admin, Report viewer users |
| 4 | User selection functionality | District-wise, Block-wise and Cluster-wise reports are displayed based on the user’s selection. | Admin, Report viewer users |
| 5 | Download metrics data | Download functionality for the report metrics is available at various levels like the district, block and cluster levels. | Admin, Report viewer users |
| 6 | Time series Functionality | Reports will be generated based on the selected month and the year | Admin, Report viewer users |
| 7 | Workflow | Student attendance data reports have been covered for 3 months of historical data, i.e data from august 2019 to december 2019 |  |

**CRC App Data Report**

[CQB-178](https://project-sunbird.atlassian.net/browse/CQB-178), [CQB-179](https://project-sunbird.atlassian.net/browse/CQB-179), [CQB-180](https://project-sunbird.atlassian.net/browse/CQB-180), [CQB-181](https://project-sunbird.atlassian.net/browse/CQB-181), [CQB-182](https://project-sunbird.atlassian.net/browse/CQB-182), [CQB-184](https://project-sunbird.atlassian.net/browse/CQB-184), [CQB-185](https://project-sunbird.atlassian.net/browse/CQB-185)

| No. | Feature | Description | Roles Impacted |
| :--- | :--- | :--- | :--- |
| 1 | Bubble Chart |  | Admin, Report viewer users |
| 2 | x-y Axis Data |  | Admin, Report viewer users |
| 3 | Table data |  |  |
| 4 | Geo selection | Display of the reports based on the district, block and cluster, as selected by the user. | Admin, Report viewer users |
| 5 | Download metrics data | Download functionality for the report metrics is available at various levels like the district, block and cluster levels. | Admin, Report viewer users |
| 6 | Time series Functionality | Reports will be generated based on the selected month and the year | Admin, Report viewer users |
| 7 | Workflow | CRC reports have been developed using the latest one month’s data. |  |

**Student Assessment Report**

[CQB-206](https://project-sunbird.atlassian.net/browse/CQB-206), [CQB-207](https://project-sunbird.atlassian.net/browse/CQB-207), [CQB-208](https://project-sunbird.atlassian.net/browse/CQB-208), [CQB-209](https://project-sunbird.atlassian.net/browse/CQB-209), [CQB-210](https://project-sunbird.atlassian.net/browse/CQB-210), [CQB-211](https://project-sunbird.atlassian.net/browse/CQB-211), [CQB-212](https://project-sunbird.atlassian.net/browse/CQB-212), [CQB-213](https://project-sunbird.atlassian.net/browse/CQB-213), [CQB-214](https://project-sunbird.atlassian.net/browse/CQB-214)

| No. | Feature | Description | Roles Impacted |
| :--- | :--- | :--- | :--- |
| 1 | Map Report | State, District, Block, Cluster, and school level Student assessment percentages/ levels are displayed on the Maps based on the user’s selection | Admin, Report viewer users |
| 2 | Color Gradient | The color gradient on the map shows the attendance assessment percentages/ levels of the students. Red shows lowest performance and green shows highest performance. | Admin, Report viewer users |
| 3 | Drill Down Functionality | A hierarchical drill down functionality from state level to school level is available and can be accessed by clicking on the individual dots in the map. | Admin, Report viewer users |
| 4 | User selection functionality | District-wise, Block-wise and Cluster-wise reports are displayed based on the user’s selection. | Admin, Report viewer users |
| 5 | Download metrics data | Download functionality for the report metrics is available at various levels like the district, block and cluster levels. | Admin, Report viewer users |
| 6 | Time series Functionality | Report should generate based on the selected month and the year | Admin, Report viewer users |
| 7 | Workflow | . Student assessment reports have been developed using the latest semester assessment’s data. |  |

1. **Known Issues:**

This is a section that describes all the known issues/ bugs that are present in the cQube product and they have been reported as being a part of this release.

| Sl No | Component | Issues |
| :--- | :--- | :--- |
| 1 | Workflow | When there are duplicate records in the data file, The nifi validations do not happen currently. This will be corrected in the next release. [CQB-324](https://project-sunbird.atlassian.net/browse/CQB-324) |
| 2 | Installation | After Installation is successful, a new S3 emission bucket is created. The new S3 emission bucket does not accept data immediately. It takes a minimum of two hours to start the emission. Further R&D is planned to find a solution for this. [CQB-325](https://project-sunbird.atlassian.net/browse/CQB-325) |
| 3 | CRC report | Performance issue in CRC reports. The data loading on the tables and charts in the school levels and cluster levels take approximately 40-50 seconds which is a longer time than other reports. [CQB-326](https://project-sunbird.atlassian.net/browse/CQB-326) |
| 4 | Student Attendance & semester report | Performance issue in student attendance reports. The data loading on the maps in the school levels and cluster levels take approximately 6 seconds which is a longer time than others. Due to this, there are alignment issues in the reports, while loading markers on the map. [CQB-327](https://project-sunbird.atlassian.net/browse/CQB-327) |
|  |  |  |
|  |  |  |


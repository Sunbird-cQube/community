---
description: 'Release Version 1.1, 16 July 2020'
---

# cQube Release Notes V1.1

**1.**           **Objectives of the cQube release 1.1**

cQube V 1.1 release, as an upgrade to the cQube release 1.0. This release will not retain the data from Release 1.0 once upgraded.  This release also adds a new report, faster and improved report viewing capability with admin functionalities.

**2.**           **Scope**

cQube product release features and issues are described in this version 1.1 of the document​.

**3.**           **Summary of the Product Features** 

This document contains information on the following new features and enhancements to the existing features of the cQube product:

1. Infrastructure reports with configuration stage implementation
   1. Infrastructure Map report
   2. Infrastructure Scatter plot report
2. API development for downloading log files and files, metrics from S3 buckets
3. Improvements in CRC report performance
4. Data validations
5. Admin monitoring screens
   1. View and download log files
   2. Download metrics and transformed data files
   3. User management
   4. Grafana dashboard
6. Access management using Keycloak
7. UI upgrades from last release
   1. Footer value calculations in the backend
   2. Admin login separation
   3. Landing page for admin and report viewer

**4.**           **Description of the Product Features**

**1. Infrastructure reports**

CQB-[276](https://project-sunbird.atlassian.net/browse/CQB-276), [CQB-277](https://project-sunbird.atlassian.net/browse/CQB-277), [CQB-278](https://project-sunbird.atlassian.net/browse/CQB-278), [CQB-279](https://project-sunbird.atlassian.net/browse/CQB-279), [CQB-280](https://project-sunbird.atlassian.net/browse/CQB-280), [CQB-281](https://project-sunbird.atlassian.net/browse/CQB-281), [CQB-282](https://project-sunbird.atlassian.net/browse/CQB-282), [CQB-283](https://project-sunbird.atlassian.net/browse/CQB-283), [CQB-284](https://project-sunbird.atlassian.net/browse/CQB-284), [CQB-359](https://project-sunbird.atlassian.net/browse/CQB-359), [CQB-374](https://project-sunbird.atlassian.net/browse/CQB-374),

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
      <td style="text-align:left">Map Report</td>
      <td style="text-align:left">State, District, Block, Cluster, and school level infrastructure details
        are displayed in the maps based on the user&#x2019;s selection.</td>
      <td
      style="text-align:left">Admin, Report viewers</td>
    </tr>
    <tr>
      <td style="text-align:left">2</td>
      <td style="text-align:left">Scatter plot</td>
      <td style="text-align:left">
        <p>State, District, Block, Cluster, and school level infrastructure details
          are displayed in a scatter plot.</p>
        <p>A table with all the details is also displayed alongside.</p>
      </td>
      <td style="text-align:left">Admin, Report viewers</td>
    </tr>
  </tbody>
</table>

**2. API development**

[CQB-378](https://project-sunbird.atlassian.net/browse/CQB-378)

| No. | Feature | Description | Roles Impacted |
| :--- | :--- | :--- | :--- |
| 1 | Download log files API | A common API has been generated for all the log files | Admin and report creator |
| 2 | Download metrics files | A common API has been generated to download the metrics files | Admin and report creator |
| 3 | S3 input and output bucket API | A common API has been generated for the S3 input and output buckets \(both for report creator and admin user\) | Admin and report creator |
| 4 | API to view list of documents | A common API has been generated to view the list of all the documents | Admin and report creator |

**3. Improvement in CRC report performance**

[CQB-326](https://project-sunbird.atlassian.net/browse/CQB-326)**,** [CQB-342](https://project-sunbird.atlassian.net/browse/CQB-342), [CQB-343](https://project-sunbird.atlassian.net/browse/CQB-343), [CQB-344](https://project-sunbird.atlassian.net/browse/CQB-344), [CQB-345](https://project-sunbird.atlassian.net/browse/CQB-345)

| No. | Feature | Description | Roles Impacted |
| :--- | :--- | :--- | :--- |
| 1 | CRC performance improvement | CRC Queries are now in the metrics and not at the UI side, thus improving the performance | Report viewer |

**4. Data validations**

[CQB-324](https://project-sunbird.atlassian.net/browse/CQB-324), [CQB-385](https://project-sunbird.atlassian.net/browse/CQB-385), [CQB-386](https://project-sunbird.atlassian.net/browse/CQB-386), [CQB-392](https://project-sunbird.atlassian.net/browse/CQB-392)

| No. | Feature | Description | Roles Impacted |
| :--- | :--- | :--- | :--- |
| 1 | Duplicate records validation | Duplicate records are validated before inserting into the database | -            |
| 2 | Null values and blank lines validation | Blank lines will be eliminated and null values are validated | -            |
| 3 | Overlapping data validation | The records are checked with pre-existing records before inserting to avoid overlapping data | -            |

**5. Admin monitoring screens**

[CQB-328](https://project-sunbird.atlassian.net/browse/CQB-328), [CQB-329](https://project-sunbird.atlassian.net/browse/CQB-329), [CQB-262](https://project-sunbird.atlassian.net/browse/CQB-262),

| No. | Feature | Description | Roles Impacted |
| :--- | :--- | :--- | :--- |
| 1 | View and download log files | This screen has been provided to view all the log files from postgreSQL, emission API, S3 bucket, NiFi, angular and nodej. These log files can be downloaded using the functionality provided | Admin |
| 2 | Download metrics and transformed data files | This screen has been provided to download metrics and transformed data filed | Admin |
| 3 | User management | This screen can be used by the admin to manage the users and add/ remove access | Admin |
| 4 | Grafana dashboard | This is an external dashboard which shows NiFi heat memory, RAM usage, JVM usage, CPU utilization by the cQube product | Admin |

**6. Access management using keycloak**

[CQB-366](https://project-sunbird.atlassian.net/browse/CQB-366)

| No. | Feature | Description | Roles Impacted |
| :--- | :--- | :--- | :--- |
| 1 | Keycloak authentication | Users authenticate with keycloak instead of individual applications. | Admin, Report viewer |

**7. UI upgrades from last release**

[CQB-351](https://project-sunbird.atlassian.net/browse/CQB-351), [CQB-393](https://project-sunbird.atlassian.net/browse/CQB-393), [CQB-435](https://project-sunbird.atlassian.net/browse/CQB-435)

| No. | Feature | Description | Roles Impacted |
| :--- | :--- | :--- | :--- |
| 1 | Footer value calculations | Footer values are calculated using metrics and not at the UI | Report viewer |
| 2 | Admin login separation | VPN login for admin users with two factor authentication | Admin |
| 3 | Landing page for admin and report viewer | Admin has a landing page with admin functionalities and the report viewer has a different landing page | Admin, Report viewer |

**5.**           **Known Issues:**

This is a section that describes all the known issues/ bugs that are present in the cQube product and they have been reported as being a part of this release.

| Sl No | Component | Issues |
| :--- | :--- | :--- |
| 1 | Page loading issue | The log summary and admin statistics in the admin UI screens show as ‘loading’ until it loads the data completely. It has to show ‘no data found’ [CQB-450](https://project-sunbird.atlassian.net/browse/CQB-450) |
| 2 | Logout twice in admin UI | The user has to click on Logout button twice in the admin UI [CQB-451](https://project-sunbird.atlassian.net/browse/CQB-451) |
| 3 | Installation | After Installation is successful, a new S3 emission bucket is created. The new S3 emission bucket does not accept data immediately. It takes a minimum of two hours to start the emission. Further R&D is planned to find a solution for this. [CQB-325](https://project-sunbird.atlassian.net/browse/CQB-325) |


---
description: 'Release Version 1.2,  20 August 2020. Release Version 1.2.1, 26 August 2020'
---

# cQube - Release Notes V1.2 and V1.2.1

**1.**           **Objectives of the cQube release 1.2 and release 1.2.1**

cQube release version 1.2 and version 1.2.1, as an upgrade to the cQube release 1.1 updated with a new reporting feature using diksha data, telemetry visualization, semester exception and Process configurations, Two factor authentication.

**2.**           **Scope**

cQube product release features and issues are described in this version 1.2 and version 1.2.1 of the document​. This document describes the functionality of below reports

-             Diksha textbook linked content plays, Diksha course linked content plays and Diksha overall content plays

-             Telemetry implementation for student attendance and Telemetry map report.

-             Semester exception map report

-             New user creation from the admin console user interface.

**3.**           **Summary of the Product Features** 

This document contains information on the following new features and enhancements to the existing features of the cQube product:

**Release 1.2**

1. Diksha data content play visualization
2. Telemetry implementation and telemetry visualization
3. Enhancement of the process scheduler
4. cQube Configurations
   1. Enable/ Disable the process groups at installation
   2. Infrastructure configuration
   3. Configurable two factor authentication
   4. Process configuration
5. Keycloak integration automation
6. User management through admin screens

**Release 1.2.1**

Release 1.2.1 is for the following pending tasks in diksha visualization from the release 1.2:

-             Overall usage count for textbooks, courses in Diksha charts, Metrics for diksha usage count, Diksha report in summary statistics

-             crc report metric issue

**Description of the Product Features**

**1. Diksha data content play visualization**

[CQB-431](https://project-sunbird.atlassian.net/browse/CQB-431), [CQB-455](https://project-sunbird.atlassian.net/browse/CQB-455), [CQB-456](https://project-sunbird.atlassian.net/browse/CQB-456), [CQB-457](https://project-sunbird.atlassian.net/browse/CQB-457), [CQB-458](https://project-sunbird.atlassian.net/browse/CQB-458)

| Sl No. | Feature | Description | Roles Impacted |
| :--- | :--- | :--- | :--- |
| 1 | Stacked bar chart report | Diksha report based on district selection and time range selection. | Admin, Report viewers |
| 2 | Diksha table report | Diksha table report based on district selection and time range selection | Admin, Report viewers |

**2. Telemetry implementation and telemetry visualization**

[CQB-186](https://project-sunbird.atlassian.net/browse/CQB-186), [CQB-452](https://project-sunbird.atlassian.net/browse/CQB-452), [CQB-445](https://project-sunbird.atlassian.net/browse/CQB-445)

<table>
  <thead>
    <tr>
      <th style="text-align:left">No.</th>
      <th style="text-align:left">Feature</th>
      <th style="text-align:left">Description</th>
      <th style="text-align:left">Roles Impacted</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">1</td>
      <td style="text-align:left">Map based report</td>
      <td style="text-align:left">User interaction &amp; impression - location wise (District, Block, cluster
        and School level) along with the lat long details.</td>
      <td style="text-align:left">Admin and report creator</td>
    </tr>
    <tr>
      <td style="text-align:left">2</td>
      <td style="text-align:left">Map based report</td>
      <td style="text-align:left">The number of views by location will be shown on the Map report.</td>
      <td
      style="text-align:left">Admin and report creator</td>
    </tr>
    <tr>
      <td style="text-align:left">3</td>
      <td style="text-align:left">Tooltip on map report</td>
      <td style="text-align:left">
        <p>- Number of users that have accessed student attendance reports</p>
        <p>- Number of views for student attendance reports</p>
      </td>
      <td style="text-align:left">Admin and report creator</td>
    </tr>
  </tbody>
</table>

**3. Enhancement of the process scheduler**

[CQB-400](https://project-sunbird.atlassian.net/browse/CQB-400), [CQB-410](https://project-sunbird.atlassian.net/browse/CQB-410)

| No. | Feature | Description | Roles Impacted |
| :--- | :--- | :--- | :--- |
| 1 | Nifi process scheduler | Scheduler for the start and stop of Nifi processor groups | Admin user |
| 2 | Nifi process Modification/ configuration | Modification/ configuration of nifi process by admin during installation | Admin user |

**4. cQube Configurations**

[CQB-410,](https://project-sunbird.atlassian.net/browse/CQB-410) [CQB-444](https://project-sunbird.atlassian.net/browse/CQB-444), [CQB-374](https://project-sunbird.atlassian.net/browse/CQB-374)

| No. | Feature | Description | Roles Impacted |
| :--- | :--- | :--- | :--- |
| 1 | Process group configuration | Enable/ Disable the process groups at installation | Admin |
| 2 | Infrastructure configuration | Infrastructure configuration | Admin |
| 3 | Two factor authentication | Two factor authentication for all users is provided as an option and can be configurable by admin | Admin |

**5. Keycloak integration automation**

[CQB-453,](https://project-sunbird.atlassian.net/browse/CQB-453) [CQB-454](https://project-sunbird.atlassian.net/browse/CQB-454) 

| No. | Feature | Description | Roles Impacted |
| :--- | :--- | :--- | :--- |
| 1 | Keycloak integration automation | Keycloak integration automation for realm creation, role creation and client creation | Admin |

**6. User management through admin screens**

[CQB-460](https://project-sunbird.atlassian.net/browse/CQB-460), [CQB-461](https://project-sunbird.atlassian.net/browse/CQB-461), [CQB-224](https://project-sunbird.atlassian.net/browse/CQB-224), [CQB-462](https://project-sunbird.atlassian.net/browse/CQB-462), [CQB-463](https://project-sunbird.atlassian.net/browse/CQB-463)

| No. | Feature | Description | Roles Impacted |
| :--- | :--- | :--- | :--- |
| 1 | User management through admin screens | User management was through keycloak in the release 1.1. User management is done with cQUbe screens in this release. | Admin, Report viewer |

**7. Release version 1.2.1**

[CQB-532](https://project-sunbird.atlassian.net/browse/CQB-532)

<table>
  <thead>
    <tr>
      <th style="text-align:left">No.</th>
      <th style="text-align:left">Feature</th>
      <th style="text-align:left">Description</th>
      <th style="text-align:left">Roles Impacted</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">1</td>
      <td style="text-align:left">Diksha Visualization updates</td>
      <td style="text-align:left">
        <p>Overall usage count for textbooks, courses in Diksha charts, Metrics for
          diksha usage count, Diksha report in summary statistics</p>
        <p>crc report metric issue</p>
      </td>
      <td style="text-align:left">Admin, Report viewer</td>
    </tr>
  </tbody>
</table>

**4.**           **Known Issues:**

This is a section that describes all the known issues/ bugs that are present in the cQube product and they have been reported as being a part of this release.

<table>
  <thead>
    <tr>
      <th style="text-align:left">Sl No</th>
      <th style="text-align:left">Issues</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">1</td>
      <td style="text-align:left">Continuous refresh in incognito window for admin screens <a href="https://project-sunbird.atlassian.net/browse/CQB-480">CQB-480</a>.</td>
    </tr>
    <tr>
      <td style="text-align:left">2</td>
      <td style="text-align:left">RAM size issue - During installation, the RAM size validation is allowing
        upto 100% of the system RAM size. It should ideally allow only 70% of the
        RAM to be used. <a href="https://project-sunbird.atlassian.net/browse/CQB-527">CQB-527</a>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">3</td>
      <td style="text-align:left">Diksha report has not been added to the summary statistics <a href="https://project-sunbird.atlassian.net/browse/CQB-528">CQB-528</a>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">4</td>
      <td style="text-align:left">Semester report - The semester report gets overwritten when the calendar
        year changes. <a href="https://project-sunbird.atlassian.net/browse/CQB-529">CQB-529</a>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">5</td>
      <td style="text-align:left">
        <p>Admin is redirecting to the login page again when they click on the admin
          console.</p>
        <p>Once after login again all the functionalities are working. <a href="https://project-sunbird.atlassian.net/browse/CQB-530">CQB-530</a>
        </p>
      </td>
    </tr>
  </tbody>
</table>


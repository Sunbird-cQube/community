---
description: Release Version 1.7 - 08 December 2020
---

# cQube - Release Notes V 1.7

**1.**           **Objectives of the cQube release 1.7**

cQube release version 1.7, as an upgrade to the cQube release 1.6, has TPD reports, load balancer changes from ELB to ALB, NIFI scheduler and state specific configurations.

**2.**           **Scope**

cQube product release features and issues are described in this version 1.7. This release has enhancements on Diksha API test with real data, load balancer changes from ELB to ALB, Nifi Scheduler for Daily, Weekly, Monthly and Yearly and state specific configurations.

**3.**           **Summary of the Product Features** 

This document contains information on the following new features and enhancements to the existing features of the cQube product:

1. Load balancer changes from ELB to ALB
2. Nifi Scheduler for Daily, Weekly, Monthly and Yearly
3. State specific configurations
4. State specific Static table configurations from UDISE data
5. Diksha TPD Enrolment/Completion reports
6. API Token based authentication
7. Configuration of session out time
8. Configuration of Diksha Columns

**4.**           **Description of the Product Features**

1. Load balancer changes from ELB to ALB

 [CQB-761](https://project-sunbird.atlassian.net/browse/CQB-761)

| Sl No. | Feature | Description | Roles Impacted |
| :--- | :--- | :--- | :--- |
| 1 | Load balancer change | -          Migration from AWS Classic Load Balancer to Application Load Balancer |  |

2. Nifi scheduler frequency

[CQB-743](https://project-sunbird.atlassian.net/browse/CQB-743)

| Sl No. | Feature | Description | Roles Impacted |
| :--- | :--- | :--- | :--- |
| 1 | Nifi scheduler | -          Nifi scheduler has been added the option to set Daily, Weekly, Monthly and Yearly. | Admin, Report viewers |

3. State specific configurations 

[CQB-762](https://project-sunbird.atlassian.net/browse/CQB-762)

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
      <td style="text-align:left">State specific configurations</td>
      <td style="text-align:left">
        <p>- Add the state specific configurations at installation</p>
        <p>- State selection added for the cQube 1.7 upgrade from 1.6.1</p>
      </td>
      <td style="text-align:left">Admin, Report viewers</td>
    </tr>
  </tbody>
</table>

4. State specific Static table configurations from UDISE data

[CQB-764](https://project-sunbird.atlassian.net/browse/CQB-764)

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
      <td style="text-align:left">State specific table configurations</td>
      <td style="text-align:left">
        <p>- Changing of static tables using UDISE data from state specific static
          tables</p>
        <p>- Validations need to be done using UDISE data structure for district_mst,block_mst,cluster_mst,school_mst</p>
        <p>- All the metrics calculation should be updated based on the UDISE data.</p>
      </td>
      <td style="text-align:left">Admin, Report viewers</td>
    </tr>
  </tbody>
</table>

5. Diksha TPD Enrolment/Completion reports

[CQB-752,](https://project-sunbird.atlassian.net/browse/CQB-752) [CQB-766](https://project-sunbird.atlassian.net/browse/CQB-766)

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
      <td style="text-align:left">Nifi process status</td>
      <td style="text-align:left">
        <p>- New report, Diksha TPD Enrolment/Completion report is added</p>
        <p>- New report, Diksha TPD Completion Percentage Report is added</p>
      </td>
      <td style="text-align:left">Admin, Report viewers</td>
    </tr>
  </tbody>
</table>

6. Upgradation from release 1.6.1 to 1.7

[CQB-768](https://project-sunbird.atlassian.net/browse/CQB-768)

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
      <td style="text-align:left">Upgradation from release 1.6.1 to 1.7</td>
      <td style="text-align:left">
        <p>- Ansible code added for the upgradation from release 1.6.1 to 1.7</p>
        <p>- State specific configurations were added</p>
        <p>- Diksha columns configuration were added</p>
        <p>- Session timeout was changed to default 7 days, minimum timeout 30 Minutes
          and maximum timeout period is 3650 days</p>
        <p>- Kong API gateway is added</p>
      </td>
      <td style="text-align:left">Admin, Report viewers</td>
    </tr>
  </tbody>
</table>

7. API Token based authentication

[CQB-808](https://project-sunbird.atlassian.net/browse/CQB-808)

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
      <td style="text-align:left">API token based authentication</td>
      <td style="text-align:left">
        <p>- Token based authentication using Kong gateway.</p>
        <p>- Emission user creation was modified with the token creation at admin
          console &#x201C;Create User&#x201D; page.</p>
        <p>- The configurations have been updated by ansible during the installation
          &amp; upgradation.</p>
      </td>
      <td style="text-align:left">Admin, Report viewers</td>
    </tr>
  </tbody>
</table>

7. Configuration of session out time

[CQB-807](https://project-sunbird.atlassian.net/browse/CQB-807)

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
      <td style="text-align:left">Configuration of session out time</td>
      <td style="text-align:left">
        <p>- Configuration of the access_token life span for the cQube Active session.</p>
        <p>- Session timeout was changed to default 7 days, minimum timeout 30 Minutes
          and maximum timeout period is 3650 days</p>
        <p>- Session time specified during the installation &amp; upgradation.</p>
      </td>
      <td style="text-align:left">Admin, Report viewers</td>
    </tr>
  </tbody>
</table>

8. Configuration of diksha columns

[CQB-809](https://project-sunbird.atlassian.net/browse/CQB-809)

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
      <td style="text-align:left">Configuration of diksha columns</td>
      <td style="text-align:left">
        <p>- The diksha columns can be configured during the installation &amp; upgradation
          stage.</p>
        <p>- Nifi side validations can be done if the columns are available</p>
        <p>- Metrics are calculated according to the column&apos;s availability.</p>
        <p>- If the columns are not available, Diksha &#x201C;Usage by user profile&#x201D;
          report will be disabled from the dashboard else the report will be enabled.</p>
      </td>
      <td style="text-align:left">Admin, Report viewers</td>
    </tr>
  </tbody>
</table>

**5.**           **Known Issues:**

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
      <td style="text-align:left">Nifi scheduler issue - Nifi schedulers were pointed to the scheduler names
        instead of IDs as Ids are refreshing at upgradation. For 1.7 we must do
        the manual scheduling and it will work with the auto schedules. <a href="https://project-sunbird.atlassian.net/browse/CQB-800">CQB-800</a>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">2</td>
      <td style="text-align:left">
        <p>Usage by course content Report - Sorting issue</p>
        <p>Classes like Class 3, Class 4 need to be added &apos;0&apos; before the
          number at the input data. then the sorting order will be fixed.</p>
        <p>Ex: Class 10, Class 3 and Class 4, First system is considered Class after
          then will check for the number. As 3 and 4 are bigger than 1, Class 10
          is coming at the wrong place. <a href="https://project-sunbird.atlassian.net/browse/CQB-814">CQB-814</a>
        </p>
      </td>
    </tr>
  </tbody>
</table>


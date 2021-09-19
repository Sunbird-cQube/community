---
description: 'Release Version 1.3, 11 September 2020'
---

# cQube - Release Notes V1.3

**1.**           **Objectives of the cQube release 1.3**

cQube release version 1.3, as an upgrade to the cQube release 1.2 and 1.2.1 has been updated with a new reporting feature using UDISE data.

**2.**           **Scope**

cQube product release features and issues are described in this version 1.3. This document describes the map based reports created using UDISE metrics and indices. The map based reports contain school rankings based on the UDISE data.

**3.**           **Summary of the Product Features** 

This document contains information on the following new features and enhancements to the existing features of the cQube product:

1. UDISE data map based visualization
2. Issues from the previous release have been resolved:
   1. Continuous refresh issue
   2. RAM size issue
   3. Manifest file removal
3. Upgradation from 1.2.1 to 1.3

**Description of the Product Features**

**1. UDISE Visualization**

[CQB-531](https://project-sunbird.atlassian.net/browse/CQB-531), [CQB-539](https://project-sunbird.atlassian.net/browse/CQB-539), [CQB-136](https://project-sunbird.atlassian.net/browse/CQB-136), [CQB-134](https://project-sunbird.atlassian.net/browse/CQB-134), [CQB-133](https://project-sunbird.atlassian.net/browse/CQB-133), [CQB-137](https://project-sunbird.atlassian.net/browse/CQB-137), [CQB-131](https://project-sunbird.atlassian.net/browse/CQB-131), [CQB-135](https://project-sunbird.atlassian.net/browse/CQB-135), [CQB-128](https://project-sunbird.atlassian.net/browse/CQB-128), [CQB-130](https://project-sunbird.atlassian.net/browse/CQB-130), [CQB-132](https://project-sunbird.atlassian.net/browse/CQB-132)

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
      <td style="text-align:left">Map based report</td>
      <td style="text-align:left">
        <p>Map based reports have been created for the following metrics:</p>
        <p>1. administration</p>
        <p>2. arts lab index</p>
        <p>3. community participation</p>
        <p>4. enrollment</p>
        <p>5. grant expenditure</p>
        <p>6. ict lab index</p>
        <p>7. medical index</p>
        <p>8. nsqf</p>
        <p>9. policy implementation</p>
        <p>10. safety</p>
        <p>11. school infrastructure</p>
        <p>12. school inspection</p>
        <p>13. school performance</p>
        <p>14. science lab index</p>
        <p>15. teacher profile</p>
        <p>Each of these metrics have indices in them which have been described in
          a document attached to the JIRA ticket <a href="https://project-sunbird.atlassian.net/browse/CQB-133">CQB-133</a>
        </p>
      </td>
      <td style="text-align:left">Admin, Report viewers</td>
    </tr>
  </tbody>
</table>

**2 Issues from the previous release**

[CQB-480](https://project-sunbird.atlassian.net/browse/CQB-480), [CQB-527](https://project-sunbird.atlassian.net/browse/CQB-527), [CQB-525](https://project-sunbird.atlassian.net/browse/CQB-525)

| Sl No. | Feature | Description | Roles Impacted |
| :--- | :--- | :--- | :--- |
| 1 | Continuous refresh issue | Continuous refresh in incognito window for admin screens [CQB-480](https://project-sunbird.atlassian.net/browse/CQB-480). |  |
| 2 | RAM Size issue | During installation, the RAM size validation is allowing upto 100% of the system RAM size. It should ideally allow only 70% of the RAM to be used. [CQB-527](https://project-sunbird.atlassian.net/browse/CQB-527) | Admin, Report viewers |
| 3 | Manifest file removal | Removed manifest file validation in Static data ,Diksha, semester and infra nifi processor groups, Student attendance and CRC and validations in all the processor groups. [CQB-525](https://project-sunbird.atlassian.net/browse/CQB-525) |  |

**4.**           **Known Issues:**

This is a section that describes all the known issues/ bugs that are present in the cQube product and they have been reported as being a part of this release.

| Sl No | Issues |
| :--- | :--- |
| 1 | Infrastructure column validation issue - [CQB-561](https://project-sunbird.atlassian.net/browse/CQB-561) |
| 2 | Nifi restart issue while semester data file processing - [CQB-562](https://project-sunbird.atlassian.net/browse/CQB-562) |


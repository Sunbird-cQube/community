---
description: 'Release Version 1.5, 16 October 2020'
---

# cQube - Release Notes V 1.5

**1.**           **Objectives of the cQube release 1.5**

cQube release version 1.5, as an upgrade to the cQube release 1.4 has enhancements to the UDISE reports, telemetry reports and diksha reports.

**2.**           **Scope**

cQube product release features and issues are described in this version 1.5. This release has enhancements to UDISE reports, api call for diksha reports and dashboard for the telemetry report.

**3.**           **Summary of the Product Features** 

This document contains information on the following new features and enhancements to the existing features of the cQube product:

1. UDISE Report - Configuration stage implementation
2. DIKSHA api call
3. Telemetry dashboard implementation
4. Upgradation from release 1.4 to 1.5
5. Nifi restart issue
6. PAT report enhancement - addition of time range

**4.**           **Description of the Product Features**

1. UDISE report - configuration stage implementation

[CQB-630](https://project-sunbird.atlassian.net/browse/CQB-630), [CQB-631](https://project-sunbird.atlassian.net/browse/CQB-631), [CQB-632](https://project-sunbird.atlassian.net/browse/CQB-632), [CQB-634](https://project-sunbird.atlassian.net/browse/CQB-634)

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
      <td style="text-align:left">Configuration stage implementation</td>
      <td style="text-align:left">
        <p>- Udise report has an exhaustive list of calculated metrics. Users can
          create normalised metrics by adding two or more calculated metrics.</p>
        <p>- Users can configure the newly created normalised metrics under any of
          the predefined index</p>
        <p>- Users can also configure the newly created normalised metrics under
          a new index.</p>
        <p>- The weights &amp; statuses of the normalised metrics &amp; those of
          the indices can be updated in the configuration stage.</p>
      </td>
      <td style="text-align:left">Admin, Report viewers</td>
    </tr>
  </tbody>
</table>

2. DIKSHA api call

[CQB-635](https://project-sunbird.atlassian.net/browse/CQB-635), [CQB-636](https://project-sunbird.atlassian.net/browse/CQB-636), [CQB-637](https://project-sunbird.atlassian.net/browse/CQB-637)

| Sl No. | Feature | Description | Roles Impacted |
| :--- | :--- | :--- | :--- |
| 1 | Diksha Api call | Existing cQube Diksha report data is emitted by the emission users. But the Diksha data should be loaded by the API call which is provided by Diksha development team | Admin, Report viewers |

3. Telemetry dashboard implementation

[CQB-638](https://project-sunbird.atlassian.net/browse/CQB-638),  [CQB-640](https://project-sunbird.atlassian.net/browse/CQB-640),  [CQB-641](https://project-sunbird.atlassian.net/browse/CQB-641)

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
      <td style="text-align:left">Telemetry dashboard changes</td>
      <td style="text-align:left">
        <p>Telemetry dashboard displays the following:</p>
        <p>- The views from the landing page.</p>
        <p>- The views count is displayed on the cQube landing page under the &#x2018;each&#x2019;
          icon.</p>
        <p>The view count will be displayed for the last 24 hours, 7 days and 30
          days as a scrolling text.</p>
      </td>
      <td style="text-align:left">Admin, Report viewers</td>
    </tr>
  </tbody>
</table>

4. Resolutions to issues from the previous release

[CQB-643](https://project-sunbird.atlassian.net/browse/CQB-643)

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
      <td style="text-align:left">Nifi restart issue</td>
      <td style="text-align:left">
        <p>Nifi was restarting unexpectedly. This issue was only while processing
          the semester data file.</p>
        <p>The heap memory size has been increased in the configuration file and
          the issue has been resolved</p>
      </td>
      <td style="text-align:left">Admin, Report viewers</td>
    </tr>
  </tbody>
</table>

5. Upgradation from release 1.4 to release 1.5

[CQB-542](https://project-sunbird.atlassian.net/browse/CQB-642)

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
      <td style="text-align:left">Upgradation Tasks for release 1.5</td>
      <td style="text-align:left">
        <p>Ansible code update should be done for the below items,</p>
        <p>Nifi parameters to be added</p>
        <p>Postgres Scripts to be called.</p>
      </td>
      <td style="text-align:left">Admin, Report viewers</td>
    </tr>
  </tbody>
</table>

**5.**           **Known Issues:**

This is a section that describes all the known issues/ bugs that are present in the cQube product and they have been reported as being a part of this release.

| Sl No | Issues |
| :--- | :--- |
| 1 |  |
| 2 |  |


# Table DrillDown Customization

A service named report-drill down-service  has been created to maintain the state of the drilldown in a given program, which can be found in the below path of the dashboard ms codebase:&#x20;

`src/app/core/services/report-drilldown/report-drilldown.service.ts`

In order to implement the drill down feature in a given table report, subscribe to the above service in the ngOnInit lifecycle function as shown below.

<figure><img src="https://lh3.googleusercontent.com/lz121e77GyjMoxNAz_S-lbDSbHsT0L5RsCWr6KLIFqiOLDgpG3HvTUm4tBDYxmsClwmboFP_bE1PsnAE7tAKZ0zBoqJRObzpd3DOF-srqRNxmZFNJH8M2oxeR7aLsfg1zOAj03iNvX-cPWT2ggnBIF8" alt=""><figcaption></figcaption></figure>

Add the drilldown function to the table report component file. (In future this function will be placed in the service itself). For reference the function can be found in the below file: src/app/views/teacher-attendance/pages/teacher-attendance-summary/reports/tas-average-attendance/tas-average-attendance.component.ts

To enable clickable level columns in the table add the below configuration into the column object of the table report configuration.\


<figure><img src="https://lh5.googleusercontent.com/fknytDWBEgeu7h8l-v4p7Tvb6QQBM_0XT20as1NRYGnL_xrClpD7Pizw94hhesDdVDkowRPV87B8FGT9GDNzDS9ThvnAe2y-JgMz8K8_w4dSOxNxwT6CfnERkIrJQRIdsY93IBrxX39Ahv242--U1gQ" alt=""><figcaption></figcaption></figure>

Here are the steps:

* dataProps is to specify what property name the column be and alias name of that property.
* hierarchyLevel specifies which level the current column is in.
* linkedReports represents which other reports will be affected by the drilldown of this table.
* allowedLevels restricts the drill down to specified levels in the array

To Link a report to drill down features of another report, subscribe to the service like above and add the drilldown function to the report component file.\


For reference follow the implementation in the below file&#x20;

src/app/views/teacher-attendance/pages/teacher-attendance-summary/reports/average-attendance-school-table/average-attendance-school-table.component.ts

\

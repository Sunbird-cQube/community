---
description: Example adding a BigNumber KPI
---

# Adding a new KPI

A shared BigNumber component is available in the below path

src/app/shared/components/big-number

* Create a new angular Component inside a Program following the below folder structure.



<figure><img src="https://lh4.googleusercontent.com/CYWSKPpFe7_sMf1mI8RkMa6zyMTW18vLCk0bAvnN6c6TWlPN8x9XQtsa033DOg7_oPOY8w5CGg7symzujEhU7bRq-J8S4VUmpzliQpGvSdd_s-RnO62Lbfymf-K3_J4pn6rgjevrxlmoCBxEaQm59hw" alt=""><figcaption></figcaption></figure>

* Add the common component in the html file.
* In the component typescript file add the getReportData Function which fetches the queries according to the configurations. For reference follow this file&#x20;

src/app/views/teacher-attendance/pages/teacher-attendance-summary/reports/tas-average-attendance-bignumber/tas-average-attendance-bignumber.component.ts

* Add the configuration to the program config files found in the config folder.

<figure><img src="https://lh5.googleusercontent.com/xxj07p2Wvd9ijrSu0UaGU6VeVgZowbTNnAKPgEI78e_rVBS_UT72i0SiNiNpK4rI39TGeqSBnlPqf2I70HQRtxnXYqfDbV2ivx2yVHaP_FiVH5iTR5XES65wBKfDDrix3vIcUwOtP1OEUQUK_3tI6AU" alt=""><figcaption></figcaption></figure>

<figure><img src="https://lh3.googleusercontent.com/COsiUlSOKpqTWPEmrE0oQ0CZEf3hqvBYVy8OBbwOXphJMAHvP6mtV8mxJkMXTK1PEf7zCEnEOwd2nXCAIkjMbcjAZ5oQWtyow_-9BZaFq-5s96UJnzqzyNGJNysNO3shKd1jhuwJmqSmkY7jMkxrGb8" alt=""><figcaption></figcaption></figure>

\


* label is the tab/report name the current kpi belongs to
* filter is an array of objects, where each object corresponds to the rbac level containing specific details for each levels

1. hierarchyLevel is the mapping of the current level to the logged in Level.
2. timeSeriesQueries hold key/object pairs where key is the chart type and value is the query for fetching the data for that chart. They are fetched when date time filter is involved
3. Similar to timeSeriesQueries queries hold the queries for non-date time filter scenarios
4. level inside the actions just specifies the name of next level in the given hierarchy.
5. The bigNumber object inside options contains extra options to be sent to that specific chart type.
6. title is the bigNumber titles to be displayed
7. valueSuffix is the suffix to the bigNumber Value to be displayed

property is the column name/ property name in the output of the query to be displayed as the BigNumber.

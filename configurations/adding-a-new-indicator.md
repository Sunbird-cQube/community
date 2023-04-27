---
description: 'Note: The steps are used for adding a new report to an existing program'
---

# Adding a New Indicator

1. Navigate to the component created for the given report and into the "reports" folder.
2. Create a child component using the following CLI command: `ng g c <indicator-name>`.
3. Once the component is created, fill the HTML and TypeScript files with references to previous indicators or with Angular/implementation knowledge.
4. Later, in the configuration file of that program, add an object with a unique key for that indicator.
5. Fill the configurations according to the reference again with the older indicators and fill the queries using the datasets ingested for this indicator for every level that this indicator is required for.

<img src="../.gitbook/assets/image (36).png" alt="" data-size="original">

6. Based on the chart type, you can also provide options in the same configurations, such as titles, color of the columns, legend of the map report, etc.

<img src="../.gitbook/assets/image (1).png" alt="" data-size="original">

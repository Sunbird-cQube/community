---
description: 'Note: These steps are for adding a new report to an existing program'
---

# Adding a New Report

1. Navigate to the respective program in the client-side code base where the report has to be added.
2. Inside the "pages" folder, create an Angular component named after the report using the following CLI command: `ng g c <report-name>`

<img src="../.gitbook/assets/image (34).png" alt="" data-size="original">

3. Once the component is created, it will contain four files - `ts`, `spec-ts`, `html`, and `css`.
4. Fill the TypeScript and HTML files with the reference of other programs. You may need to have knowledge about Angular and how functions have been designed.
5. Include this component in the program HTML file to be rendered.
6. Under the same program name, there will be a config folder that contains a configuration file for the entire program (a JSON file).
7. If any filters are required for the specific report, add an object under the "filter" key in the above configuration file which specifies the filter and its values required for the report. You may need Angular knowledge to fill the object with the appropriate structure.

![](<../.gitbook/assets/image (35).png>)

\

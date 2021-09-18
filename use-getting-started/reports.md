# Reports

cQube reports provide data-based insights in the field of education. These reports help cQube admins to make appropriate decisions based on the insights. 

### Landing page dashboard

cQube dashboard will contain the shortcut icons of all the reports. Telemetry details will be displayed on each icon. The number of views will be displayed for the last one day, 7 days and last 30 days with a 15 seconds time delay. Each icon will have an ‘i’ symbol at the right corner of the icon which will display the description of the report with whoever mouse.  

For the visualisation of the metrics cQube uses the below types of reports.

1. Map based visualisation
2. Scatter plot visualisation
3. Stacked bar report
4. Table format visualisation
5. Bar chart visualisation

More details of the visualisation feature wise details are explained below,

### Map based visualisation 

Landing page of the Map report will be represented for the whole state by having the colour gradient dots on the different districts of the state. Colour gradient will be declared from Red-Green where Red represents the poor performance and the Green represents the good performance.

All the dots will be displayed at the centre of the screen. Zoom functionality will be applicable only for the school level representation that too only up to the state dimensional level only. Maps can be dragged up to state specific. 

Tooltip: On mouse hover of the dot, The user will be able to see the tooltip which can give the results in formation of the metric calculations. Along with the results the tooltips are containing the data like id and the location name and location details also.

Blocks button: Block button will be a clickable function and it will display the information and the metrics results with the color gradient dots, tooltip information of the total blocks of the state.

Clusters button: Clusters button will be a clickable function and it will display the information and the metrics results with the color gradient dots, tooltip information of the total clusters of the state.

Schools button: Schools button will be a clickable function and it will display the information and the metrics results with the color gradient dots, tooltip information of the total Schools of the state.

Drill down functionality: Users will be redirected to the next hierarchical level of the locations by clicking on the dots. 

For example: If the user clicks on some district’s dot, then the visualisation will be populated by all the blocks of the districts.

If the user clicks on some block’s dot, then the visualisation will be populated by all the clusters of the districts.

Drop down functionality: Drop down functionality will be experienced by the selection from the “Choose a District”, “Choose a Block” and “Choose a cluster” drop down box values. 

Time series: By selection of the time represented dropdown values users will get the time series information. Time series will be changed according to the data sources.

* Student attendance report has the Year and Month time series selection.
* Semester report is having the Semester wise time series selection.
* Infrastructure report does not have the time series. It represents the whole information of the infrastructure data. 
* CRC report, Teacher attendance, student attendance, PAT map report, UDISE is having the Previous day, last 7 days & 30 days time selection.

Absolute & Relative toggle button: The Absolute and Relative toggle button in the footer will represent the dots color in the absolute and relative calculation explained below.

Absolute color will be calculated in the range of 1 to 100. The statically derived 50 gradient colors will be distributed between Red and Green colors. Each color will be assigned with 2 numbers interval

Relative color will be calculated by taking the difference between the maximum & Minimum values of the data and applying the statically derived 50 gradient colors will be distributed between Red and Green colors. Each color will be assigned the mean value of the difference.

Download Functionality: The download icon provides the download functionality of the report metrics based on the selection of the drop down values. The report names are named as below

```text
{report_name}_{time_period/region_specification}_{district_id/block_id/cluster_id/school_id}_{date}.csv
time_period -->{last_1_day,last_7_days,last_30_days,overall,month_year}
Region_specification -->{blocks_of_district,clusters_of_block,schools_of_cluster}
date & time -->{DD-MM-YYYY}
```

### Map exception reports

The functionalities of the exception reports will be the same as the map reports except the color representation of the dots. The color of the dots will be represented in the reverse order of the normal report. The colors will be applied from Red to Green gradient for the maximum to minimum value.

### Scatter plot visualisation 

The landing page of the scatter plot report will be represented for the whole state by having the several normalised metrics using the raw data and you can read more about them.

A key feature of this dashboard is its ability to Zoom In and Out at various administrative levels. The administrative levels include District, Block and Cluster. 

This has been done to provide relevant insights at the appropriate administrative level. In addition to visualising data, the dashboard also gives you the ability to download the data at various administrative levels. 

This feature has been enabled to provide freedom to power users to derive additional insights that may not be captured in this dashboard. You can download the data using the dropdown option on the top right corner.

Table representation: The table in the scatter plot will have the different insights as columns of the table which represent the performances of different educational areas.

X-Axis & Y-Axis: these are the dropdown boxes which contain the columns of the above mentioned table. By selecting the x-axis value and the y-axis value the dot will be displayed at the cross point of the x & y results.

Drop down functionality: Drop down functionality will be experienced by the selection from the “Choose a District”, “Choose a Block” and “Choose a cluster” drop down box values. 

Download Functionality: The download icon provides the download functionality of the report metrics based on the selection of the drop down values.

### Table format visualisation 

Diksha is using the table format representation. The landing page of the table format visualisation is having the metrics in combination with the ‘Textbook content plays’ and the ‘Course content plays’. This report is having the pagination and a total of 1000 records will be shown in each page.

Each cell of the table will represent the color gradient based on the performance. The color gradient is applied same as heat map and 10 different colors between red to green

Content Selection: Content selection is the dropdown box which will represent the overall content, Textbook content and course content. By selecting the value table will be filtered as per the selected value.

Drop down functionality: Drop down functionality will be experienced by the selection from the “Choose a District” drop down box values.

Time series: By selection of the time represented dropdown values users will get the time series information. Time series will be changed according to the data sources. Diksha is having the Previous day, last 7 days & 30 days time selection.

Download Functionality: The download icon provides the download functionality of the report metrics based on the selection of the drop down values.

### Bar Chart visualization 

Diksha is using the bar chart visualisation. The landing page of the bar chart visualisation is having the metrics of in combination with the ‘Textbook content plays’ and the ‘Course content plays’ in the form of horizontal bars.

Content Selection: Content selection is the dropdown box which will represent the overall content, Textbook content and course content. By selecting the value table will be filtered as per the selected value.

Choose collection Name: By choosing the Collection name from the dropdown the bars will represent the selected results.

Drop down functionality: Drop down functionality will be experienced by the selection from the “Choose a District” drop down box values.

Time series: By selection of the time represented dropdown values users will get the time series information. Time series will be changed according to the data sources. Diksha is having the Previous day, last 7 days & 30 days time selection.

Download Functionality: The download icon provides the download functionality of the report metrics based on the selection of the drop down values.

### Heat Map Report visualization 

Periodic Assessment Test \(PAT\) and Diksha Teacher professional development \(TPD\) are using the Heat map visualization. This report contains the average performance of the district, block, cluster and school wise users. 

X-axis contains the location names and Y-axis contains the consolidated information of the course, exam date, grade and subject details.

For Diksha TPD Course Progress Report  & Diksha TPD Teachers Percentage Report, A drop down box was added for selection of multiple courses. All the courses will be available in the dropdown box and users will be able to select multiple courses from the dropdown box. When the user selects the causes and clicks on the submit button the results will be displayed according to the selection.

Heat map should have the pagination functionality. Records will be divided into 40 records per page. Each page will display the 40 records with vertical scroll bar operation. 

The color indicators were added to the heat map for the understanding of the color differences of various performance ranges.

Heatmap contains various filters as described below.

Choose view by: This filter contains the Question ID & Indicator. By the selection of Choose view the report should show the Y-axis changes the representation to Question id and Indicator name.

Heat map shows the results by applying the colour gradient will be declared from Red-Green where Red represents the poor performance and the Green represents the good performance.

### Progress card  Report

Progress card report is the report where all the report highlights are displayed at one page. This report should contain the information of Student attendance, Semester, PAT, CRC, UDISE and School infrastructure details. 

Progress card index report contains various filters as described below.

Choose Level: This filter contains the text of District, Block, Cluster and School options. Users may select one of the options and have to enter either name \(OR\) ID of the selected level. 

By clicking on the submit button the data for the selected place will be displayed. 

Info icon has been placed for each report data box which will display the complete details of the metrics of the selected area.

A hyperlink will be provided at the bottom of each report data box which will be redirected to the actual report and shows the selected place at the actual report. Each map report will be displayed with the link “Click here to access Progress card” to access the Progress card index report at the right which will redirect the user to the Progress card with selected options.

**Trends Chart**

Trends Chart is introduced to cQube to observe how the schools are performing in comparison to the previous months. It will give the user to understand the performance of schools and how it is trending month by month.

By clicking on the hyperlink user will be redirected to the trends chart. Below are the trends chart functionalities

* By default trends chart will load the full state information on the home page
* At a time user can select up to 10 inner hierarchical level selections such as Districts, Blocks and clusters and user has to click the submit button
* If the user selects only one option and clicks on the submit button, Then the next level of hierarchical locations will be displayed.
* Users will be able to select the academic year from the “Choose year” select box.
* Each option will be represented with different color coding and the code will be given as a legend at the right side of the screen
* X- Axis should be the performance and the Y-axis should be the months of the academic year.
* Users will be able to see the Relative & Absolute markers on Y-Axis by selecting the switch at the left bottom of the report. 

Data source wise reports Visualisations are as below  


Student Attendance Report: Map visualisation, Heat Map

Student Attendance Exception Report: Exception Map visualisation

Teacher Attendance Report: Map visualisation

Teacher Attendance Exception Report: Exception Map visualisation

Semester Report: Map visualisation

CRC Report: Scatter plot visualisation

School Infrastructure Reports: Map Visualisation and Scatter plot visualisation

Diksha: Bar chart and table type visualisations 

UDISE: Map visualisation

PAT: Map visualisation, Heat map, Table type visualisations 

PAT Exception Report: Exception Map visualisation

Composite Report : Scatter plot visualisation

Telemetry : Map visualisation


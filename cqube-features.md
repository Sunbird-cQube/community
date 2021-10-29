# cQube Product Features

cQube mainly have following features to support data analysis and visualizations.

1.	Data Ingestion
2.	Data Processing
3.	Error Logging
4.	Data Visualization
5.	User Interface


**Data Ingestion** – cQube can accept data via API on set interval defined by emission user depends on the need and updates on the data. It also provides feature to ingest data on ad-hoc basis for certain updates or missing data. Generally, the defined intervals are Daily, Weekly, Monthly, Half-Yearly or Yearly.


**Data Processing** - Data processing includes the data validation, Data transformation and metrics calculations once data ingested to cQube it goes through detailed testing and validation before computing metrics (e.g., File format, Column Validation, Data type validation, Missing value validation, Data duplication check)

Once data passed through the test & validation phase it goes to processing stage where all calculation will be performed for the defined metrics and output will be sent to designated output folder for visualization

**Error logging** – Errors at each step being recorded and stored at designated place and available to Admin for review and further actions

**Data Visualization** – Pre-defined visuals will be shown on user interface via internet for existing use case, below are the examples of visualization –
- Maps
- BAR chart
- Scatter Plot
- Tabular reports
- Heat Map
- Trend chart

Further customization/extension of cQube can be done by creating new use case

**User Interface** – User interface facility helps users to access the reports via internet based on the defined access level, there are mainly 3 roles exist in cQube namely Admin, Emission and Report viewer



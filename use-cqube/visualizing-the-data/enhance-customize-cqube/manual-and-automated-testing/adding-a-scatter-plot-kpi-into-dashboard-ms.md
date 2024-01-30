# Adding a Scatter Plot KPI into dashboard ms

A sunbird dashlet library is being used to plot scatter charts across the application.

* Create a new report component and add the above library selector in the html files with any (additional elements if needed)



**For reference follow the below file:**

src/app/views/udise/pages/correlation-tab/reports/correlation/correlation.component.html

* In the component ts file add the required functions (ex: get reportData, apply criteria, drilldown) respective to each feature.

**For reference follow the below file:**

src/app/views/udise/pages/correlation-tab/reports/correlation/correlation.component.ts

A common function getScatterChartReportData() is used to get the data based on the configuration which will be then passed to the dashlet library. The chart configurations present are based on the chartJS requirements which is used within the sb-dashlet library.



**The above function can be found in the below file:**

src/app/core/services/data.service.ts

\
**Options available in the specifically for the scatter plot configuration:**

* groupByNeeded specifies whether the group by is needed upon the data received from the query
* groupByLabel specifies property name on which group by will be done
* metricLabelProp specifies the property which will be converted as key after group by
* metricValueProp specifies the property which will be converted as value after group by
* valueSuffix is a suffix string which can be attached after the value in the tooltip, EX: %
* tooltipMetrics is the configuration required to develop custom tooltips. It is an array of objects, in which each object represents a line in the tooltip (except the x-axis and y-axis values).

**Each object consists of 3 properties as follows:**

* valuePrefix is the prefix string before the value.
* value is the property name of the value in the query result
* valueSuffix is the suffix string after the value.

<figure><img src="https://lh3.googleusercontent.com/qrne5homn7GelBxJOFQdv8sxiqwjFEX8VzWrBAMP_4R9nJuy0V9hqaWxZ_2BQRZPWjGDbe3ROQrnyxJu4BIAB-wKPtp0hh4lJkJwjCoDdozPkSfuEaGW_9-2IYcY68_hXOORkL5Uf2-3qAIXNH2bFpo" alt=""><figcaption></figcaption></figure>

* Filters for the Scatter Plot (X-axis and Y-axis) can be configured as shown below.

<figure><img src="https://lh6.googleusercontent.com/ytZQZA5j9Ua_YcdXpmO2T30xk3z6PyVn3iyvsjD0ggVWFwochcc0YdZZyyJ4VAp7k2OlpqqwdRO-RZGQ506Ai2i6hUKEMgLkjc3HSlJtZSzwFWCCVLZ1KYoLUgoLybdXD3vVwlznog1cNMCo7ibTkXM" alt=""><figcaption></figcaption></figure>

**Options for filter configuration:**

* label is the tab name under which the filter will be included
* name is the placeholder name that will be displayed above the filter in the UI.
* labelProp specifies the property in the query result for dropdown names.
* valueProp specifies the property which will be mapped with the dropdown values.
* id is just an identifier for each filter.
* axis specifies which axis (out of x and y) this filter corresponds to.
* query as the name suggests, holds the query which fetches the filter data.

# Adding a Map KPI into dashboard ms

A shared map component using leaflet is available in the below path

`src/app/shared/components/maps/leaflet-map`\


* Create a new report component and add the above shared component in the html files with any (additional elements if needed)

\


For reference follow the below file:

src/app/views/teacher-attendance/pages/teacher-attendance-summary/reports/teacher-attendance-map/teacher-attendance-map.component.html

* In the component ts file add the required functions (ex: get reportData, apply criteria, drilldown) respective to each feature.

**For reference follow the below file:**

src/app/views/teacher-attendance/pages/teacher-attendance-summary/reports/teacher-attendance-map/teacher-attendance-map.component.ts



* Options available in the configuration:&#x20;
* indicatorType specifies whether the kpi is of type percent or any general value type.
* indicator represents the property name of the kpi on which map has to be based on. (property name is nothing but alias name in the query)
* title specifies the title to be displayed in the legend
* tooltipMetrics  is an array of objects which is used to construct tooltip.It contains a property name/value which if present in the data will be added along with its prefix and suffixes to the tooltip element.&#x20;

&#x20;

<figure><img src="https://lh5.googleusercontent.com/1LbZAtbo9SZXvTZtAKNCSMTmPrW1ra3oKQQnB89ZX5ZyaPDbR1TW3b2Dxt8x9MWs-kayg6Cez6-hdmAuBZSJG8Zj__oq1k1KmhehU-_RJfUTP9hyVXP--Z4qu3Hb9oILcRLCZ1W8fWWOWPI7HzmTmV0" alt=""><figcaption></figcaption></figure>

Above options are applicable for certain scenarios where metric filter is not needed.



In a case where a metric filter is needed few extra options are available in the configuration.

* metricFilterNeeded is a flag which can be set true if a metric filter is involved in the map report.
* groupByColumn is a property by which the data from the queries can be grouped on a given level.
* metricValueProp specifies the value property to identify the value of a given metric option.
* metricLabelProp specifies the label of the metric option.

Example for the above scenario can be found below:

<figure><img src="https://lh4.googleusercontent.com/bNBtB-x9HiHy_8TUfQdy8Azq_13KNRWFg42hgqIYsWPfObJpHue7wGRpXYCvILPD9i3P5_vN2KaONA1tzZZxdMLW3lURdYpVC9-vw7XfNlsnX_W4x0ZZ9c9qSFC2EaQSxohIwa70HlxI_NPwBOkV8Gc" alt=""><figcaption></figcaption></figure>

Group by is used to group all metrics for a given district/block/cluster into a single row.\


**Before Group By:**

<figure><img src="https://lh5.googleusercontent.com/GCZoJzfw_WOdnu2XbYzZ890X4pusvwl62zgsP4O7EtSMIY6er5ziVt2feyxRZsGNSyFZnxjewVvkuKGw0YCoPDP7c_kkawg7s9fqO6pUuyg7C2ZNjuHLwMip7GgLFOr4Zch33u39Y5nx8ap4wij5j1k" alt=""><figcaption></figcaption></figure>

\
**After Group By:**&#x20;

<figure><img src="https://lh5.googleusercontent.com/BAf9YYYfdr8n86sMGcVt-PXlshBbvBrK3GgWu3TBp2-yNb0Ms3Ihd_4IuvPqRpmvlEN3NCof4uuBFFk9GoHiZup4n3_Sw5uX7hY9ypmG1kEiwS6bfEoY3Y4UeYZEBvMSVyU5oBnizhB48Ig7VV0f6wU" alt=""><figcaption></figcaption></figure>

To add drill down features just follow the steps in the table i.e to subscribe to the drilldown service in the map report component .

For reference follow below report:

src/app/views/teacher-attendance/pages/teacher-attendance-summary/reports/teacher-attendance-map/teacher-attendance-map.component.ts

\
\

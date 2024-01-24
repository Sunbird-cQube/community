# Schema

The schema in cQube is a json object which needs to be defined in a specific format. cQube expects a schema to validate the data file provided by the state team. The current cQube schema should be defined as follows.&#x20;

{​​&#x20;

&#x20;   "program": "string",&#x20;

&#x20;   "input": {​​&#x20;

&#x20;       "type": "object",&#x20;

&#x20;       "properties": {​​&#x20;

&#x20;           "column\_name": {​​&#x20;

&#x20;               "type": "string || number",&#x20;

&#x20;               "shouldnotnull": true&#x20;

&#x20;           }&#x20;

&#x20;       },&#x20;

&#x20;       "required": \[&#x20;

&#x20;           "column\_name"&#x20;

&#x20;       ]&#x20;

&#x20;   }&#x20;

}&#x20;

&#x20;\


The properties consist of the column names present in the data file. We can specify the type of the column. It currently supports two types: string and number. The shouldnotnull property indicates that null values are not allowed. The required key indicates that the column names specified inside an array are mandatory and should be present in the data file.&#x20;


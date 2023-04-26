---
description: Describes the specifications of a dimension in cQube V 5.0
---

# Dimensions

Dimensions describe events.

cQube adopts the below Dimension specification.

{\
"title": \<NAME OF THE DIMENSION TABLE>,\
"indexes": \[\
{\
"columns": \[\
\[\
\<COLUMN NAME TO BE INDEXED>\
]\
]\
}\
],\
"properties": {\
\<COLUMN NAME>: {\
"type": "string || number",\
"unique": true\
}\
},\
"psql\_schema": "dimensions"\
}

Example

```
{
    "title": "sch_att_teachers_marked_Weekly_cluster",
    "properties": {
        "sum": {
            "type": "number"
        },
        "count": {
            "type": "number"
        },
        "cluster_id": {
            "type": "string"
        }
    },
    "psql_schema": "datasets"
}
```

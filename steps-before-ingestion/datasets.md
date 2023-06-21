---
description: Describes the specifications of a dataset in cQube V 5.0
---

# Datasets

High-level data which is computed by aggregating events. It is a data representation of the indicator. Datasets are persistent within cQube Ed. A dataset is created for at least one indicator.

Below is the Dataset specification for Datasets

{\
"title": \<NAME OF THE DATASET TABLE>,\
"properties": {\
\<COLUMN NAME>: {\
"type": "string || number"\
}\
},\
"psql\_schema": "datasets"\
}

```
{
    "title": "subject",
    "indexes": [
        {
            "columns": [
                [
                    "subject_nas",
                    "subject_diksha",
                    "subject_state"
                ]
            ]
        }
    ],
    "properties": {
        "subject_id": {
            "type": "string",
            "unique": true
        },
        "subject_nas": {
            "type": "string",
            "unique": true
        },
        "subject_state": {
            "type": "string",
            "unique": true
        },
        "subject_diksha": {
            "type": "string",
            "unique": true
        }
    },
    "psql_schema": "dimensions"
}
```

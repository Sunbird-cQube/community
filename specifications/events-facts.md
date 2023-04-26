---
description: Describes the specifications of an event / fact in cQube V 5.0
---

# Events / Facts

An event is a data structure that records an occurrence at a particular time for an entity (eg: school, etc). It is a combination of simple data types (eg: integer, varchar, etc.). An event should always contain a column/set of columns that helps you calculate the Indicator. A table with a timestamp doesn’t necessarily mean that it is an event; it should contribute to either aggregation or filtering of the dataset.

cQube adopts below event specification.

{\
"type": "object",\
"properties": {\
\<COLUMN NAME>: {\
"type": "string || number",\
"shouldnotnull": true\
}\
}\
}

Ex:

```
{
    "properties": {
        "date": {
            "type": "string",
            "format": "date"
        },
        "grade_state": {
            "type": "string",
            "unique": true
        },
        "total_teachers": {
            "type": "integer",
            "unique": true
        }
    }
}
```

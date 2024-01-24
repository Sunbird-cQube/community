# How to prepare schemas for event files

An event is a data structure that records an occurrence at a particular time for an entity (eg: school, etc). It is a combination of simple data types (eg: integer, varchar, etc.). An event should always contain a column/set of columns that helps you calculate the Indicator. A table with a timestamp doesn’t necessarily mean that it is an event; it should contribute to either aggregation or filtering of the dataset.

```
{
    “program”: “string”, // Name of the event
    “input”: {
        "type": "object",
        "properties": {
             <COLUMN NAME>: {
"type": "string || number",
             "shouldnotnull": true,
	“format”?: “date”
         }
    }
}

Example: school-attendance

  "program": "teacher-attendance",
  "input": {
    "type": "object",
    "properties": {
      "date": {
        "type": "string",
        "shouldNotNull": true,
        "format": "date"
      },
      "school_id": {
        "type": "string",
        "shouldNotNull": true
      },
      "grade": {
        "type": "string",
        "shouldNotNull": true
      },
      "district_id": {
        "type": "string",
        "shouldNotNull": true
      },
      "block_id": {
        "type": "string",
        "shouldNotNull": true
      },
      "cluster_id": {
        "type": "string",
        "shouldNotNull": true
      },
      "schoolcategory_id": {
        "type": "string",
        "shouldNotNull": true
      },
      "total_teachers": {
        "type": "string",
        "shouldNotNull": true
      }
    },
    "required": [
      "date",
      "school_id",
      "grade",
      "district_id",
      "cluster_id",
      "block_id",
      "schoolcategory_id",
      "total_teachers"
    ]
  }
}
```

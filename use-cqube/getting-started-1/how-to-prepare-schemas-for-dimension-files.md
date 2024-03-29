---
description: >-
  Dimensions are the columns that describe events. The dimensions are those
  values which do not change frequently and remain constant. Example: State name
---

# How to prepare schemas for  dimension files

**CQube adopts the Dimension Specification as defined below**

<pre><code>"program": "school",//Name of the dimension
<strong>  "input": {
</strong>    "type": "object",
    "properties": {
      "school_id": {
        "type": "string",
        "shouldNotNull": true
      },
      "udise_code": {
        "type": "string",
        "shouldNotNull": true
      },
      "school_name": {
        "type": "string",
        "shouldNotNull": true
      },
      "schoolcategory_id": {
        "type": "string",
        "shouldNotNull": false
      },
      "schoolmanagement_id": {
        "type": "string",
        "shouldNotNull": false
      },
      "school_statecategory_id": {
        "type": "string",
        "shouldNotNull": false
      },
      "cluster_id": {
        "type": "string",
        "shouldNotNull": true
      },
      "cluster_name": {
        "type": "string",
        "shouldNotNull": true
      },
      "block_id": {
        "type": "string",
        "shouldNotNull": true
      },
      "block_name": {
        "type": "string",
        "shouldNotNull": true
      },
      "district_id": {
        "type": "string",
        "shouldNotNull": true
      },
      "district_name": {
        "type": "string",
        "shouldNotNull": true
      },
      "latitude": {
        "type": "number",
        "shouldNotNull": false
      },
      "longitude": {
        "type": "number",
        "shouldNotNull": false
      }
    },
    "required": [
      "school_id",
      "udise_code",
      "school_name",
      "cluster_id",
      "cluster_name",
      "block_id",
      "block_name",
      "district_id",
      "district_name",
      "latitude",
      "longitude"
    ]
  }
}
</code></pre>


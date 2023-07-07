---
description: Describes the specifications of a dimension in cQube
---

# Define Dimensions Schema

These schemas are used for state as well as national programs. It is important to get clarity on the schemas to have the csv files ready for ingestion. Steps for data ingestion can be found in the [Data Ingestion](broken-reference) section once the files are ready.

**CQube adopts the Dimension Specification as defined below** (this structure is generating through code)**:**

```
{
    "title": <NAME OF THE DIMENSION TABLE>,
    "indexes": [
        {
            "columns": [
                [
                    <COLUMN NAME TO BE INDEXED>
                ]
            ]
        }
    ],
    "properties": {
        <COLUMN NAME>: {
            "type": "string || number",
            "unique": true
        }
    },
    "psql_schema": "dimensions"
}

Example
   {
  "title": "school",
  "indexes": [
    {
      "columns": [
        [
          "school_id"
        ]
      ]
    }
  ],
  "properties": {
    "block_id": {
      "type": "string",
      "unique": false
    },
    "latitude": {
      "type": "string",
      "unique": false
    },
    "longitude": {
      "type": "string",
      "unique": false
    },
    "school_id": {
      "type": "string",
      "unique": true
    },
    "block_name": {
      "type": "string",
      "unique": false
    },
    "cluster_id": {
      "type": "string",
      "unique": false
    },
    "district_id": {
      "type": "string",
      "unique": false
    },
    "school_name": {
      "type": "string",
      "unique": false
    },
    "cluster_name": {
      "type": "string",
      "unique": false
    },
    "district_name": {
      "type": "string",
      "unique": false
    },
    "schoolcategory_id": {
      "type": "string",
      "unique": false
    }
  },
  "psql_schema": "dimensions"
}


Example
   {
  "title": "school",
  "indexes": [
    {
      "columns": [
        [
          "school_id"
        ]
      ]
    }
  ],
  "properties": {
    "block_id": {
      "type": "string",
      "unique": false
    },
    "latitude": {
      "type": "string",
      "unique": false
    },
    "longitude": {
      "type": "string",
      "unique": false
    },
    "school_id": {
      "type": "string",
      "unique": true
    },
    "block_name": {
      "type": "string",
      "unique": false
    },
    "cluster_id": {
      "type": "string",
      "unique": false
    },
    "district_id": {
      "type": "string",
      "unique": false
    },
    "school_name": {
      "type": "string",
      "unique": false
    },
    "cluster_name": {
      "type": "string",
      "unique": false
    },
    "district_name": {
      "type": "string",
      "unique": false
    },
    "schoolcategory_id": {
      "type": "string",
      "unique": false
    }
  },
  "psql_schema": "dimensions"
}


Example
   {
  "title": "school",
  "indexes": [
    {
      "columns": [
        [
          "school_id"
        ]
      ]
    }
  ],
  "properties": {
    "block_id": {
      "type": "string",
      "unique": false
    },
    "latitude": {
      "type": "string",
      "unique": false
    },
    "longitude": {
      "type": "string",
      "unique": false
    },
    "school_id": {
      "type": "string",
      "unique": true
    },
    "block_name": {
      "type": "string",
      "unique": false
    },
    "cluster_id": {
      "type": "string",
      "unique": false
    },
    "district_id": {
      "type": "string",
      "unique": false
    },
    "school_name": {
      "type": "string",
      "unique": false
    },
    "cluster_name": {
      "type": "string",
      "unique": false
    },
    "district_name": {
      "type": "string",
      "unique": false
    },
    "schoolcategory_id": {
      "type": "string",
      "unique": false
    }
  },
  "psql_schema": "dimensions"
}

```

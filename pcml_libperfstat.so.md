
### Sample PCML Definition file

```json
{
  "pcml" : {
    "id" : "idperf71S2v0.1",
    "version" : "v0.1",
    "library" : "/usr/lib/libperfstat.a",
    "oslevel" : "71TL06_SP2"
  },
  "definitions" : {
    "perfstat_partition_config_t" : {
      "type" : "object",
      "length" : 808,
      "properties" : {
        "partitionname" : {
          "type" : "string",
          "maxLength" : 64,
          "offset" : 0,
          "length" : 64
        },
        "partitionnum" : {
          "type" : "integer",
          "minimum": 0,
          "offset" : 64,
          "length" : 4
        },
        "groupid" : {
          "type" : "integer",
          "minimum": 0,
          "offset" : 68,
          "length" : 4
        }
      },
      "required": [
        "partitionname",
        "partitionnum",
        "groupid"
      ]
    }
  },
  "functions" : {
    "perfstat_partition_config" : {
      "returnCode" : {
        "type" : "integer",
        "minimum": 0
      },
      "params" : {
        "name" : {
          "type" : "integer",
          "minimum": 0,
          "passby" : 0,
          "length" : 8
        },
        "userbuff" : {
          "type" : "array",
          "items" : {
            "$ref" : "#/definitions/perfstat_partition_config_t"
          },
          "passby" : 1
        },
        "sizeof_userbuff" : {
          "type" : "integer",
          "minimum": 0,
          "length" : 4

        },
        "desired_number" : {
          "type" : "integer",
          "minimum": 0,
          "length" : 4

        }
      }
    }
  }
}


```


### Sample PCML Schema Definition file

```json 
{
  "pcml" : {
    "id" : "idabc71S2v0.1",
    "version" : "v0.1",
    "library" : "/usr/lib/libabc.a",
    "oslevel" : "71TL06_SP2"
  },
  "definitions" : {
    "abcdptr" : {
      "type" : "object",
      "length" : 32,
      "properties" : {
        "a" : {
          "type" : "array",
          "items" : {
            "type" : "integer",
            "format" : "int32",
            "length" : 2
          },
          "offset" : 0,
          "length" : 8,
          "passby" : 1
        },
        "b" : {
          "type" : "array",
          "items" : {
            "type" : "integer",
            "format" : "int32",
            "length" : 4
          },
          "offset" : 4,
          "length" : 8,
          "passby" : 1
        },
        "c" : {
          "type" : "array",
          "items" : {
            "type" : "integer",
            "format" : "int64",
            "length" : 8
          },
          "offset" : 8,
          "length" : 8,
          "passby" : 1
        },
        "d" : {
          "type" : "array",
          "items" : {
            "type" : "string"
          },
          "maxItems" : 1,
          "offset" : 16,
          "length" : 8,
          "passby" : 1
        }
      },
      "required": [
        "a",
        "b",
        "c",
        "d"
      ]
    },
    "abcdarray" : {
      "type" : "object",
      "length" : 56,
      "properties" : {
        "a" : {
          "type" : "array",
          "items" : {
            "type" : "integer",
            "format" : "int32",
            "length" : 2
          },
          "maxItems" : 2,
          "offset" : 0,
          "length" : 4
        },
        "b" : {
          "type" : "array",
          "items" : {
            "type" : "integer",
            "format" : "int32",
            "length" : 4
          },
          "maxItems" : 3,
          "offset" : 4,
          "length" : 12
        },
        "c" : {
          "type" : "array",
          "items" : {
            "type" : "integer",
            "format" : "int64",
            "length" : 8
          },
          "maxItems" : 4,
          "offset" : 12,
          "length" : 32
        },
        "d" : {
          "type" : "string",
          "maxLength" : 4,
          "offset" : 44,
          "length" : 5
        }
      },
      "required": [
        "a",
        "b",
        "c",
        "d"
      ]
    }
  },
  "functions" : {
    "squareabcdptr" : {
      "returnCode" : {
        "type" : "array",
        "items" : {
          "$ref" : "#/definitions/abcdptr"
        }
      },
      "params" : {
        "abcdptr" : {
          "type" : "array",
          "items" : {
            "$ref" : "#/definitions/abcdptr"
          },
          "passby" : 1
        }
      }
    },
    "squareabcdarray" : {
      "returnCode" : {
        "type" : "array",
        "items" : {
          "$ref" : "#/definitions/abcdarray"
        }
      },
      "params" : {
        "abcdarray1" : {
          "type" : "array",
          "items" : {
            "$ref" : "#/definitions/abcdarray"
          },
          "passby" : 1
        },
        "abcdarray2" : {
          "type" : "string",
          "maxLength" : 4,
          "offset" : 44,
          "length" : 5
        }
      }
    }
  }
}
```

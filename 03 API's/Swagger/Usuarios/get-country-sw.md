### Consulta Lista de Países

```json
{
  "openapi": "3.0.0",
  "info": {
    "title": "Country List API",
    "version": "1.0.0",
    "description": "Obtiene la lista de países"
  },
  "servers": [
    {
      "url": "{{URL}}",
      "description": "Servidor principal de la API"
    }
  ],
  "paths": {
    "/country_list": {
      "get": {
        "summary": "Obtener lista de países",
        "operationId": "getCountryList",
        "tags": [
          "Utilities"
        ],
        "parameters": [],
        "responses": {
          "200": {
            "description": "Lista de países obtenida exitosamente.",
            "content": {
              "application/json": {
                "schema": {
                  "$ref": "#/components/schemas/CountryListResponse"
                },
                "example": {
                  "success": true,
                  "message": "70",
                  "country": [
                    {
                      "_id": "603cd990a6e8d06cfd7081af",
                      "phone_number_length": 10,
                      "phone_number_min_length": 10,
                      "countryphonecode": "+91",
                      "flag_url": "/flags/india.gif",
                      "countryname": "India"
                    }
                  ]
                }
              }
            }
          }
        }
      }
    }
  },
  "components": {
    "schemas": {
      "CountryDetail": {
        "type": "object",
        "description": "Detalles de un país específico.",
        "properties": {
          "_id": {
            "type": "string",
            "description": "ID único del país."
          },
          "phone_number_length": {
            "type": "integer",
            "description": "Longitud máxima esperada del número de teléfono."
          },
          "phone_number_min_length": {
            "type": "integer",
            "description": "Longitud mínima esperada del número de teléfono."
          },
          "countryphonecode": {
            "type": "string",
            "description": "Código telefónico internacional del país (e.g., +91)."
          },
          "flag_url": {
            "type": "string",
            "description": "Ruta o URL de la bandera del país."
          },
          "countryname": {
            "type": "string",
            "description": "Nombre del país."
          }
        },
        "required": [
          "_id",
          "countryphonecode",
          "countryname"
        ]
      },
      "CountryListResponse": {
        "type": "object",
        "properties": {
          "success": {
            "type": "boolean",
            "description": "Indica si la operación fue exitosa."
          },
          "message": {
            "type": "string",
            "description": "Código o mensaje interno de estado."
          },
          "country": {
            "type": "array",
            "description": "Arreglo de detalles de los países disponibles.",
            "items": {
              "$ref": "#/components/schemas/CountryDetail"
            }
          }
        },
        "required": [
          "success",
          "country"
        ]
      }
    }
  }
}


```

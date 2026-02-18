### Listado de Ciudades

```json
{
  "openapi": "3.0.0",
  "info": {
    "title": "Locations API",
    "description": "API para obtener el listado de países y sus respectivas ciudades configuradas en el sistema.",
    "version": "1.0.0"
  },
  "paths": {
    "/get_country_city_list": {
      "post": {
        "summary": "Obtener lista de países y ciudades",
        "description": "Retorna un árbol jerárquico de países con sus códigos telefónicos, longitudes de validación de número y su listado de ciudades asociadas.",
        "responses": {
          "200": {
            "description": "Listado de ubicaciones obtenido con éxito",
            "content": {
              "application/json": {
                "schema": {
                  "$ref": "#/components/schemas/CountryCityResponse"
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
      "CountryCityResponse": {
        "type": "object",
        "properties": {
          "success": {
            "type": "boolean",
            "example": true
          },
          "country_list": {
            "type": "array",
            "items": {
              "$ref": "#/components/schemas/Country"
            }
          }
        }
      },
      "Country": {
        "type": "object",
        "properties": {
          "_id": { "type": "string", "example": "6020ea5a01a03b0612ffa8f6" },
          "countryname": { "type": "string", "example": "Venezuela, Bolivarian Republic of Venezuela" },
          "countryphonecode": { "type": "string", "example": "+58" },
          "phone_number_min_length": { "type": "integer", "example": 10 },
          "phone_number_length": { "type": "integer", "example": 10 },
          "city_list": {
            "type": "array",
            "items": {
              "$ref": "#/components/schemas/City"
            }
          }
        }
      },
      "City": {
        "type": "object",
        "properties": {
          "_id": { "type": "string", "example": "6020ec4e01a03b0612ffa8f8" },
          "full_cityname": { "type": "string", "example": "Caracas, Capital District" },
          "cityname": { "type": "string", "example": "Caracas" }
        }
      }
    }
  }
}
```

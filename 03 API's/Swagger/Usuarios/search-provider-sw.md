### Consulta de Conductores Según un Filtro.

```json
{
  "openapi": "3.0.0",
  "info": {
    "title": "Listado de conductore y proveedores",
    "version": "1.0.0",
    "description": "API para obtener una lista de conductores/proveedores, opcionalmente filtrada por un valor de búsqueda."
  },
  "servers": [
    {
      "url": "{URL}",
      "variables": {
        "URL": {
          "default": "https://api.ejemplo.com",
          "description": "URL base de la API."
        }
      }
    }
  ],
  "paths": {
    "/get_all_driver_list": {
      "post": {
        "summary": "Obtener lista de conductores",
        "description": "Recupera una lista de conductores (providers). La búsqueda se puede refinar con el campo 'search_value'.",
        "requestBody": {
          "required": true,
          "content": {
            "application/json": {
              "schema": {
                "$ref": "#/components/schemas/GetDriverListRequest"
              },
              "example": {
                "user_id": "{{USER_ID}}",
                "token": "{{USER_TOKEN}}",
                "search_value": "elluminati12@gmail.com"
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "Lista de conductores recuperada exitosamente (puede contener una lista vacía).",
            "content": {
              "application/json": {
                "schema": {
                  "type": "array",
                  "items": {
                    "$ref": "#/components/schemas/DriverListResponseItem"
                  }
                },
                "example": [
                  {
                    "success": true,
                    "provider_list": []
                  },
                  {
                    "success": true,
                    "provider_list": [
                      {
                        "_id": "60227d7765b27b2840e6ea25",
                        "picture": "provider_profile/60227d7765b27b2840e6ea254S0K.jpg",
                        "last_name": "Pvt",
                        "first_name": "Elluminati"
                      }
                    ]
                  }
                ]
              }
            }
          },
          "401": {
            "description": "Token de autenticación inválido."
          }
        }
      }
    }
  },
  "components": {
    "schemas": {
      "GetDriverListRequest": {
        "type": "object",
        "properties": {
          "user_id": {
            "type": "string",
            "description": "Identificador único del usuario que realiza la solicitud."
          },
          "token": {
            "type": "string",
            "description": "Token de autenticación del usuario."
          },
          "search_value": {
            "type": "string",
            "description": "Valor de búsqueda opcional (ej. email, nombre, etc.) para filtrar la lista de conductores."
          }
        },
        "required": [
          "user_id",
          "token"
        ]
      },
      "Driver": {
        "type": "object",
        "properties": {
          "_id": {
            "type": "string",
            "description": "ID interno del conductor/proveedor."
          },
          "picture": {
            "type": "string",
            "description": "Ruta a la imagen de perfil del conductor."
          },
          "last_name": {
            "type": "string"
          },
          "first_name": {
            "type": "string"
          }
        },
        "required": [
          "_id",
          "picture",
          "last_name",
          "first_name"
        ]
      },
      "DriverListResponseItem": {
        "type": "object",
        "properties": {
          "success": {
            "type": "boolean",
            "description": "Indica si el segmento de la respuesta es exitoso."
          },
          "provider_list": {
            "type": "array",
            "description": "Lista de objetos de conductor. Puede estar vacía si no hay resultados.",
            "items": {
              "$ref": "#/components/schemas/Driver"
            }
          }
        },
        "required": [
          "success",
          "provider_list"
        ]
      }
    }
  }
}

```

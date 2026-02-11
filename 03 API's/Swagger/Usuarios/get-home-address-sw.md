```json
{
  "openapi": "3.0.0",
  "info": {
    "title": "API para de consulta de direcciones",
    "version": "1.0.0",
    "description": "API para recuperar las direcciones guardadas de un usuario."
  },
  "servers": [
    {
      "url": "http://{{URL}}",
      "description": "Servidor principal (reemplazar {{URL}})"
    }
  ],
  "paths": {
    "/get_home_address": {
      "post": {
        "summary": "Obtener direcciones guardadas del usuario",
        "operationId": "getHomeAddress",
        "requestBody": {
          "required": true,
          "content": {
            "application/json": {
              "schema": {
                "$ref": "#/components/schemas/GetAddressRequest"
              },
              "examples": {
                "AddressRequestExample": {
                  "value": {
                    "user_id": "{{USER_ID}}",
                    "token": "{{USER_TOKEN}}"
                  }
                }
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "Recuperación exitosa de las direcciones",
            "content": {
              "application/json": {
                "schema": {
                  "$ref": "#/components/schemas/GetAddressResponse"
                },
                "examples": {
                  "SuccessfulAddressResponse": {
                    "value": {
                      "success": true,
                      "user_address": {
                        "_id": "61962d683b0daa5338204ce6",
                        "work_location": [
                          22,
                          70
                        ],
                        "home_location": [
                          22,
                          70
                        ],
                        "work_address": "Rajkot",
                        "home_address": "Rajkot",
                        "token": "MxWCEDRftQcZ2lv780bWd2VmfsrhHURv"
                      }
                    }
                  }
                }
              }
            }
          },
          "401": {
            "description": "No Autorizado (Token Inválido o Expirado)"
          }
        }
      }
    }
  },
  "components": {
    "schemas": {
      "GetAddressRequest": {
        "type": "object",
        "properties": {
          "user_id": {
            "type": "string",
            "description": "ID único del usuario."
          },
          "token": {
            "type": "string",
            "description": "Token de autenticación del usuario."
          }
        },
        "required": [
          "user_id",
          "token"
        ]
      },
      "UserAddressDetail": {
        "type": "object",
        "properties": {
          "_id": {
            "type": "string",
            "description": "ID interno o de usuario."
          },
          "work_location": {
            "type": "array",
            "description": "Coordenadas [latitud, longitud] de la dirección de trabajo.",
            "items": {
              "type": "number"
            },
            "minItems": 2,
            "maxItems": 2
          },
          "home_location": {
            "type": "array",
            "description": "Coordenadas [latitud, longitud] de la dirección de casa.",
            "items": {
              "type": "number"
            },
            "minItems": 2,
            "maxItems": 2
          },
          "work_address": {
            "type": "string"
          },
          "home_address": {
            "type": "string"
          },
          "token": {
            "type": "string",
            "description": "Token de sesión del usuario."
          }
        },
        "required": [
          "_id",
          "work_location",
          "home_location",
          "work_address",
          "home_address",
          "token"
        ]
      },
      "GetAddressResponse": {
        "type": "object",
        "properties": {
          "success": {
            "type": "boolean",
            "description": "Indica si la operación fue exitosa."
          },
          "user_address": {
            "$ref": "#/components/schemas/UserAddressDetail",
            "description": "Detalles de las direcciones de casa y trabajo."
          }
        },
        "required": [
          "success",
          "user_address"
        ]
      }
    }
  }
}


```


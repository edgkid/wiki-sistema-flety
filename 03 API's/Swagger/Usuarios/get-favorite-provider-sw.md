### Consulta de Conductores Favoritos

```json

{
  "openapi": "3.0.0",
  "info": {
    "title": "API - Consultar conductores favoritos",
    "version": "1.0.0",
    "description": "API para consultar lista de conductores favoritos de un usuario."
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
    "/get_favourite_driver": {
      "post": {
        "summary": "Obtener lista de conductores favoritos",
        "description": "Recupera la lista de conductores que el usuario ha marcado como favoritos.",
        "requestBody": {
          "required": true,
          "content": {
            "application/json": {
              "schema": {
                "$ref": "#/components/schemas/GetFavoriteDriverRequest"
              },
              "example": {
                "user_id": "{{USER_ID}}",
                "token": "{{USER_TOKEN}}"
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "Lista de conductores favoritos recuperada exitosamente.",
            "content": {
              "application/json": {
                "schema": {
                  "$ref": "#/components/schemas/GetFavoriteDriverResponse"
                },
                "example": {
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
              }
            }
          },
          "401": {
            "description": "No autorizado (Token inválido o expirado)."
          }
        }
      }
    }
  },
  "components": {
    "schemas": {
      "GetFavoriteDriverRequest": {
        "type": "object",
        "properties": {
          "user_id": {
            "type": "string",
            "description": "Identificador único del usuario."
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
      "FavoriteDriver": {
        "type": "object",
        "properties": {
          "_id": {
            "type": "string",
            "description": "ID interno del conductor/proveedor."
          },
          "picture": {
            "type": "string",
            "description": "Ruta de la imagen de perfil del conductor."
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
      "GetFavoriteDriverResponse": {
        "type": "object",
        "properties": {
          "success": {
            "type": "boolean",
            "description": "Indica si la operación fue exitosa."
          },
          "provider_list": {
            "type": "array",
            "description": "Lista de conductores favoritos. Puede ser una matriz vacía si no hay favoritos.",
            "items": {
              "$ref": "#/components/schemas/FavoriteDriver"
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

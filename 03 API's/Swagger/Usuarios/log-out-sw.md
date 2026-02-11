### Cierre de sesión

```json
{
  "openapi": "3.0.0",
  "info": {
    "title": "API de Cierre de Sesión",
    "version": "1.0.0",
    "description": "Endpoint para cerrar la sesión de un usuario y revocar su token."
  },
  "servers": [
    {
      "url": "https://{{URL}}",
      "description": "Servidor principal (reemplazar {{URL}})"
    }
  ],
  "paths": {
    "/logout": {
      "post": {
        "summary": "Cerrar sesión del usuario",
        "operationId": "userLogout",
        "requestBody": {
          "required": true,
          "content": {
            "application/json": {
              "schema": {
                "$ref": "#/components/schemas/LogoutRequest"
              },
              "examples": {
                "LogoutExample": {
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
            "description": "Cierre de sesión exitoso",
            "content": {
              "application/json": {
                "schema": {
                  "$ref": "#/components/schemas/LogoutResponse"
                },
                "examples": {
                  "SuccessfulLogout": {
                    "value": {
                      "success": true,
                      "message": "5"
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
      "LogoutRequest": {
        "type": "object",
        "properties": {
          "user_id": {
            "type": "string",
            "description": "ID único del usuario cuya sesión se cerrará."
          },
          "token": {
            "type": "string",
            "description": "Token de autenticación del usuario a revocar."
          }
        },
        "required": [
          "user_id",
          "token"
        ]
      },
      "LogoutResponse": {
        "type": "object",
        "properties": {
          "success": {
            "type": "boolean",
            "description": "Indica si el cierre de sesión fue exitoso."
          },
          "message": {
            "type": "string",
            "description": "Código o mensaje de respuesta."
          }
        },
        "required": [
          "success",
          "message"
        ]
      }
    }
  }
}

```

### Actualizar Contraseña

```json
{
  "openapi": "3.0.0",
  "info": {
    "title": "API - actualizar password",
    "version": "1.0.0",
    "description": "Endpoint de actualización de contraseña."
  },
  "servers": [
    {
      "url": "{URL}",
      "description": "actualización de contraseña."
    }
  ],
  "paths": {
    "/update_password": {
      "post": {
        "summary": "Actualiza la contraseña del usuario.",
        "operationId": "updatePassword",
        "requestBody": {
          "description": "Datos necesarios para cambiar la contraseña del usuario identificado por teléfono.",
          "required": true,
          "content": {
            "application/json": {
              "schema": {
                "type": "object",
                "properties": {
                  "phone": {
                    "type": "string",
                    "description": "Número de teléfono del usuario.",
                    "example": "9904385946"
                  },
                  "country_phone_code": {
                    "type": "string",
                    "description": "Código internacional del país.",
                    "example": "+91"
                  },
                  "password": {
                    "type": "string",
                    "format": "password",
                    "description": "La nueva contraseña que se desea establecer.",
                    "example": "123456"
                  }
                },
                "required": [
                  "phone",
                  "country_phone_code",
                  "password"
                ]
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "Respuesta exitosa de actualización de contraseña.",
            "content": {
              "application/json": {
                "schema": {
                  "$ref": "#/components/schemas/UpdatePasswordSuccessResponse"
                },
                "example": {
                  "success": true,
                  "message": "81"
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
      "UpdatePasswordSuccessResponse": {
        "type": "object",
        "properties": {
          "success": {
            "type": "boolean",
            "description": "Indica si la operación fue exitosa.",
            "example": true
          },
          "message": {
            "type": "string",
            "description": "Código de mensaje '81' indicando que la contraseña ha sido actualizada.",
            "example": "81"
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

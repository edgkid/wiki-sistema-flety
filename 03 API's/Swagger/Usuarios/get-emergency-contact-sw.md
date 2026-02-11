### Consultar Contacto de Emergencia

```json
{
  "openapi": "3.0.0",
  "info": {
    "title": "API - consultar contacto de emergencia",
    "version": "1.0.0",
    "description": "API para obtener la lista completa de contactos de emergencia de un usuario."
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
    "/get_emergency_contact_list": {
      "post": {
        "summary": "Obtener Lista de Contactos de Emergencia",
        "description": "Recupera todos los contactos de emergencia guardados por el usuario.",
        "requestBody": {
          "required": true,
          "content": {
            "application/json": {
              "schema": {
                "$ref": "#/components/schemas/GetContactListRequest"
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
            "description": "Lista de contactos recuperada exitosamente, o un objeto de error.",
            "content": {
              "application/json": {
                "schema": {
                  "type": "array",
                  "items": {
                    "oneOf": [
                      {
                        "$ref": "#/components/schemas/SuccessResponse"
                      },
                      {
                        "$ref": "#/components/schemas/ErrorResponse"
                      }
                    ]
                  }
                },
                "example": [
                  {
                    "success": true,
                    "message": "71",
                    "emergency_contact_data": [
                      {
                        "_id": "61965bc435a1c02ca00d3483",
                        "user_id": "61962d683b0daa5338204ce6",
                        "name": "Test",
                        "phone": "3022874531"
                      }
                    ]
                  }
                ]
              }
            }
          },
          "401": {
            "description": "No autorizado (Token inválido)."
          }
        }
      }
    }
  },
  "components": {
    "schemas": {
      "GetContactListRequest": {
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
      "EmergencyContact": {
        "type": "object",
        "properties": {
          "_id": {
            "type": "string",
            "description": "ID del contacto de emergencia."
          },
          "user_id": {
            "type": "string"
          },
          "__v": {
            "type": "integer"
          },
          "updated_at": {
            "type": "string",
            "format": "date-time"
          },
          "created_at": {
            "type": "string",
            "format": "date-time"
          },
          "is_always_share_ride_detail": {
            "type": "integer",
            "description": "Indicador de si siempre se comparten los detalles del viaje (1=Sí)."
          },
          "phone": {
            "type": "string"
          },
          "name": {
            "type": "string"
          }
        },
        "required": [
          "_id",
          "user_id",
          "name",
          "phone"
        ]
      },
      "SuccessResponse": {
        "type": "object",
        "properties": {
          "success": {
            "type": "boolean",
            "enum": [true]
          },
          "message": {
            "type": "string",
            "description": "Código de mensaje de éxito (ej. '71')."
          },
          "emergency_contact_data": {
            "type": "array",
            "description": "Lista de contactos de emergencia del usuario.",
            "items": {
              "$ref": "#/components/schemas/EmergencyContact"
            }
          }
        },
        "required": [
          "success",
          "emergency_contact_data"
        ]
      },
      "ErrorResponse": {
        "type": "object",
        "properties": {
          "success": {
            "type": "boolean",
            "enum": [false]
          },
          "error_code": {
            "type": "string",
            "description": "Código de error específico (ej. '467')."
          }
        },
        "required": [
          "success",
          "error_code"
        ]
      }
    }
  }
}

```

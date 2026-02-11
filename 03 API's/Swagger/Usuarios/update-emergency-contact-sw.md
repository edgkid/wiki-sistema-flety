### Actualizar Contacto de Emergencia

```json
{
  "openapi": "3.0.0",
  "info": {
    "title": "API - Actualizar contacto de emergencia",
    "version": "1.0.0",
    "description": "API para actualizar la información de un contacto de emergencia existente de un usuario
    ."
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
    "/update_emergency_contact": {
      "post": {
        "summary": "Actualizar Contacto de Emergencia",
        "description": "Modifica los detalles (nombre, teléfono, configuración de compartir viaje) de un contacto de emergencia usando su ID.",
        "requestBody": {
          "required": true,
          "content": {
            "application/json": {
              "schema": {
                "$ref": "#/components/schemas/UpdateEmergencyContactRequest"
              },
              "example": {
                "user_id": "{{USER_ID}}",
                "token": "{{USER_TOKEN}}",
                "phone": "3022874531",
                "name": "Test Updated",
                "emergency_contact_detail_id": "61965bc435a1c02ca00d3483",
                "is_always_share_ride_detail": 0
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "El contacto fue actualizado exitosamente, o se devolvió un error de negocio.",
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
                    "message": "68",
                    "emergency_contact_data": {
                      "_id": "61965bc435a1c02ca00d3483",
                      "user_id": "61962d683b0daa5338204ce6",
                      "is_always_share_ride_detail": 0,
                      "phone": "3022874531",
                      "name": "Test"
                    }
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
      "UpdateEmergencyContactRequest": {
        "type": "object",
        "properties": {
          "user_id": {
            "type": "string",
            "description": "Identificador único del usuario."
          },
          "token": {
            "type": "string",
            "description": "Token de autenticación del usuario."
          },
          "emergency_contact_detail_id": {
            "type": "string",
            "description": "ID del contacto de emergencia a actualizar."
          },
          "name": {
            "type": "string",
            "description": "Nuevo nombre para el contacto."
          },
          "phone": {
            "type": "string",
            "description": "Nuevo número de teléfono para el contacto."
          },
          "is_always_share_ride_detail": {
            "type": "integer",
            "format": "int32",
            "enum": [0, 1],
            "description": "Indicador para compartir siempre los detalles del viaje (1=Sí, 0=No)."
          }
        },
        "required": [
          "user_id",
          "token",
          "emergency_contact_detail_id",
          "name",
          "phone",
          "is_always_share_ride_detail"
        ]
      },
      "EmergencyContactData": {
        "type": "object",
        "properties": {
          "_id": {
            "type": "string"
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
            "format": "int32"
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
            "description": "Código de mensaje de éxito (ej. '68')."
          },
          "emergency_contact_data": {
            "$ref": "#/components/schemas/EmergencyContactData"
          }
        },
        "required": [
          "success",
          "message",
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
            "description": "Código de error específico (ej. '472' para contacto no encontrado o datos inválidos)."
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

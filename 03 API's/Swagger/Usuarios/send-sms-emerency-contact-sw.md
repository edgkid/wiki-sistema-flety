
### Envio de SMS a Contactos de Emergencia

```json
{
  "openapi": "3.0.0",
  "info": {
    "title": "API - envio de mensajes",
    "version": "1.0.0",
    "description": "API para enviar un sms a todos los contactos de emergencia del usuario con la ubicación actual."
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
    "/send_sms_to_emergency_contact": {
      "post": {
        "summary": "Enviar SMS a Contactos de Emergencia",
        "description": "Envía una alerta por SMS que incluye un enlace al mapa de ubicación del usuario a sus contactos de emergencia configurados.",
        "requestBody": {
          "required": true,
          "content": {
            "application/json": {
              "schema": {
                "$ref": "#/components/schemas/SendEmergencySmsRequest"
              },
              "example": {
                "user_id": "{{USER_ID}}",
                "map": "https://www.google.com/maps/@22.2855168,70.7887104,12z"
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "SMS enviado exitosamente a los contactos de emergencia.",
            "content": {
              "application/json": {
                "schema": {
                  "$ref": "#/components/schemas/SendEmergencySmsResponse"
                },
                "example": {
                  "success": true,
                  "message": "72"
                }
              }
            }
          },
          "401": {
            "description": "No autorizado (Usuario o token inválido)."
          },
          "400": {
            "description": "Datos de entrada inválidos (ej. URL del mapa mal formada)."
          }
        }
      }
    }
  },
  "components": {
    "schemas": {
      "SendEmergencySmsRequest": {
        "type": "object",
        "properties": {
          "user_id": {
            "type": "string",
            "description": "Identificador único del usuario que envía la alerta."
          },
          "map": {
            "type": "string",
            "format": "url",
            "description": "URL de Google Maps u otra URL que apunta a la ubicación actual del usuario."
          }
        },
        "required": [
          "user_id",
          "map"
        ]
      },
      "SendEmergencySmsResponse": {
        "type": "object",
        "properties": {
          "success": {
            "type": "boolean",
            "description": "Indica si el envío del SMS fue exitoso."
          },
          "message": {
            "type": "string",
            "description": "Código de mensaje o estado de éxito (ej. '72')."
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

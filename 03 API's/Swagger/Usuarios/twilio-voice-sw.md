### Permite el Uso de Twilio

```json
{
  "openapi": "3.0.0",
  "info": {
    "title": "Twilio Voice Call API",
    "description": "API paa hacer uso del  servicio de Twilio.",
    "version": "1.0.0"
  },
  "servers": [
    {
      "url": "{{URL}}",
      "description": "Servidor de API"
    }
  ],
  "paths": {
    "/twilio_voice_call": {
      "post": {
        "summary": "Iniciar llamada de voz",
        "description": "Activa una llamada de voz basada en el ID del viaje y el tipo de usuario que la solicita.",
        "operationId": "startTwilioCall",
        "requestBody": {
          "required": true,
          "content": {
            "application/json": {
              "schema": {
                "$ref": "#/components/schemas/VoiceCallRequest"
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "Solicitud de llamada recibida correctamente",
            "content": {
              "application/json": {
                "schema": {
                  "$ref": "#/components/schemas/VoiceCallResponse"
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
      "VoiceCallRequest": {
        "type": "object",
        "required": [
          "trip_id",
          "type"
        ],
        "properties": {
          "trip_id": {
            "type": "string",
            "description": "ID único del viaje para identificar a los participantes de la llamada.",
            "example": "619f99ecc68548396ff542a4"
          },
          "type": {
            "type": "string",
            "description": "Define quién inicia la llamada (ej. '1' para Usuario, '2' para Proveedor).",
            "example": "1"
          }
        }
      },
      "VoiceCallResponse": {
        "type": "object",
        "properties": {
          "success": {
            "type": "boolean",
            "example": true
          }
        }
      }
    }
  }
}

```

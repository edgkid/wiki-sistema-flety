### Rechazar y/o Aceptar Viaje - Proveedor

```json

{
  "openapi": "3.0.0",
  "info": {
    "title": "Provider Response API",
    "description": "Endpoint encargado de procesar la respuesta del proveedor (aceptación o rechazo) ante una solicitud de viaje.",
    "version": "1.0.0"
  },
  "paths": {
    "/respondstrip": {
      "post": {
        "summary": "Responder a solicitud de viaje",
        "description": "Permite al proveedor aceptar o rechazar un viaje asignado, notificando si la respuesta fue dentro del tiempo límite.",
        "requestBody": {
          "required": true,
          "content": {
            "application/json": {
              "schema": {
                "$ref": "#/components/schemas/RespondTripRequest"
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "Respuesta procesada exitosamente",
            "content": {
              "application/json": {
                "schema": {
                  "$ref": "#/components/schemas/RespondTripResponse"
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
      "RespondTripRequest": {
        "type": "object",
        "required": [
          "trip_id",
          "provider_id",
          "is_provider_accepted",
          "token"
        ],
        "properties": {
          "trip_id": {
            "type": "string",
            "description": "ID único del viaje",
            "example": "{{TRIP_ID}}"
          },
          "provider_id": {
            "type": "string",
            "description": "ID único del proveedor",
            "example": "{{PROVIDER_ID}}"
          },
          "is_provider_accepted": {
            "type": "integer",
            "enum": [0, 1],
            "description": "1 para aceptar el viaje, 0 para rechazarlo",
            "example": 1
          },
          "token": {
            "type": "string",
            "description": "Token de autenticación del proveedor",
            "example": "{{PROVIDER_TOKEN}}"
          },
          "is_request_timeout": {
            "type": "boolean",
            "description": "Indica si la solicitud expiró antes de responder",
            "example": false
          }
        }
      },
      "RespondTripResponse": {
        "type": "object",
        "properties": {
          "success": {
            "type": "boolean",
            "example": true
          },
          "message": {
            "type": "string",
            "description": "Código de mensaje (e.g., '22' para aceptado, '23' para rechazado)",
            "example": "22"
          },
          "is_provider_accepted": {
            "type": "integer",
            "enum": [0, 1],
            "example": 1
          }
        }
      }
    }
  }
}
```

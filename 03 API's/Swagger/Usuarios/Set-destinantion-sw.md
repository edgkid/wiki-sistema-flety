### Actualización de Coordenadas

```json
{
  "openapi": "3.0.0",
  "info": {
    "title": "Set Destination API",
    "description": "API que permite al usuario actualizar las coordenadas de destino de un viaje en curso.",
    "version": "1.0.0"
  },
  "servers": [
    {
      "url": "{{URL}}",
      "description": "Servidor principal"
    }
  ],
  "paths": {
    "/usersetdestination": {
      "post": {
        "summary": "Actualizar destino del viaje",
        "description": "Establece una nueva ubicación de destino mediante latitud y longitud, devolviendo el estado actual del proveedor.",
        "operationId": "userSetDestination",
        "requestBody": {
          "required": true,
          "content": {
            "application/json": {
              "schema": {
                "$ref": "#/components/schemas/SetDestinationRequest"
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "Destino actualizado exitosamente",
            "content": {
              "application/json": {
                "schema": {
                  "$ref": "#/components/schemas/TrackingResponse"
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
      "SetDestinationRequest": {
        "type": "object",
        "required": [
          "user_id",
          "trip_id",
          "token",
          "d_latitude",
          "d_longitude"
        ],
        "properties": {
          "user_id": {
            "type": "string",
            "example": "{{USER_ID}}"
          },
          "trip_id": {
            "type": "string",
            "example": "{{TRIP_ID}}"
          },
          "token": {
            "type": "string",
            "example": "{{USER_TOKEN}}"
          },
          "d_latitude": {
            "type": "string",
            "description": "Latitud del nuevo destino",
            "example": "22.275354640085016"
          },
          "d_longitude": {
            "type": "string",
            "description": "Longitud del nuevo destino",
            "example": "70.77289044857025"
          }
        }
      },
      "TrackingResponse": {
        "type": "object",
        "properties": {
          "success": {
            "type": "boolean",
            "example": true
          },
          "message": {
            "type": "string",
            "description": "Código de respuesta",
            "example": "34"
          },
          "providerLocation": {
            "type": "array",
            "items": {
              "type": "number"
            },
            "description": "Coordenadas del proveedor [latitud, longitud]",
            "example": [0, 0]
          },
          "bearing": {
            "type": "number",
            "description": "Orientación del proveedor",
            "example": 0
          },
          "total_distance": {
            "type": "number",
            "description": "Distancia total estimada",
            "example": 0
          },
          "total_time": {
            "type": "number",
            "description": "Tiempo total estimado",
            "example": 0
          }
        }
      }
    }
  }
}
```

### Ubicación de Viaje en Tiempo Real

```json
{
  "openapi": "3.0.0",
  "info": {
    "title": "Provider Tracking API",
    "description": "API para obtener la ubicación actual (latitud y longitud), orientación y métricas de viaje del proveedor en tiempo real.",
    "version": "1.0.0"
  },
  "servers": [
    {
      "url": "{{URL}}",
      "description": "Servidor de seguimiento"
    }
  ],
  "paths": {
    "/getproviderlatlong": {
      "post": {
        "summary": "Obtener ubicación del proveedor",
        "description": "Retorna las coordenadas geográficas, el ángulo de rotación (bearing) y los totales de distancia y tiempo del proveedor para un viaje específico.",
        "operationId": "getProviderLocation",
        "requestBody": {
          "required": true,
          "content": {
            "application/json": {
              "schema": {
                "$ref": "#/components/schemas/ProviderLocationRequest"
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "Ubicación y métricas obtenidas exitosamente",
            "content": {
              "application/json": {
                "schema": {
                  "$ref": "#/components/schemas/ProviderLocationResponse"
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
      "ProviderLocationRequest": {
        "type": "object",
        "required": [
          "provider_id",
          "trip_id",
          "token"
        ],
        "properties": {
          "provider_id": {
            "type": "string",
            "description": "ID único del proveedor/conductor.",
            "example": "{{PROVIDER_ID}}"
          },
          "trip_id": {
            "type": "string",
            "description": "ID del viaje activo.",
            "example": "{{TRIP_ID}}"
          },
          "token": {
            "type": "string",
            "description": "Token de autenticación del usuario.",
            "example": "{{USER_TOKEN}}"
          }
        }
      },
      "ProviderLocationResponse": {
        "type": "object",
        "properties": {
          "success": {
            "type": "boolean",
            "example": true
          },
          "message": {
            "type": "string",
            "description": "Código de respuesta del sistema.",
            "example": "34"
          },
          "providerLocation": {
            "type": "array",
            "description": "Coordenadas actuales [latitud, longitud].",
            "items": {
              "type": "number"
            },
            "example": [22.30388, 70.80195]
          },
          "bearing": {
            "type": "number",
            "description": "Orientación o ángulo de dirección del vehículo (0-360).",
            "example": 145.5
          },
          "total_distance": {
            "type": "number",
            "description": "Distancia total recorrida hasta el momento.",
            "example": 5.2
          },
          "total_time": {
            "type": "number",
            "description": "Tiempo total transcurrido del viaje.",
            "example": 12.5
          }
        }
      }
    }
  }
}


```

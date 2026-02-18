### Verificar Coordenadas de Ubicación y Destino

```json
{
  "openapi": "3.0.0",
  "info": {
    "title": "Trip Destination Validation API",
    "description": "Endpoint diseñado para verificar si el proveedor se encuentra en las coordenadas geográficas correctas del destino antes de finalizar el servicio.",
    "version": "1.0.0"
  },
  "paths": {
    "/check_destination": {
      "post": {
        "summary": "Validar llegada a destino",
        "description": "Compara la ubicación actual del proveedor con la ubicación de destino registrada en el viaje.",
        "requestBody": {
          "required": true,
          "content": {
            "application/json": {
              "schema": {
                "$ref": "#/components/schemas/CheckDestinationRequest"
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "Validación procesada (Revisar campo success)",
            "content": {
              "application/json": {
                "schema": {
                  "$ref": "#/components/schemas/CheckDestinationResponse"
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
      "CheckDestinationRequest": {
        "type": "object",
        "required": [
          "trip_id",
          "provider_id",
          "token",
          "latitude",
          "longitude"
        ],
        "properties": {
          "trip_id": {
            "type": "string",
            "description": "ID único del viaje a validar.",
            "example": "{{TRIP_ID}}"
          },
          "provider_id": {
            "type": "string",
            "description": "ID del proveedor que realiza la consulta.",
            "example": "{{PROVIDER_ID}}"
          },
          "token": {
            "type": "string",
            "description": "Token de autenticación activo del proveedor.",
            "example": "{{PROVIDER_TOKEN}}"
          },
          "latitude": {
            "type": "number",
            "format": "double",
            "description": "Latitud actual del proveedor.",
            "example": 22.303971160142797
          },
          "longitude": {
            "type": "number",
            "format": "double",
            "description": "Longitud actual del proveedor.",
            "example": 70.80225252263104
          }
        }
      },
      "CheckDestinationResponse": {
        "type": "object",
        "properties": {
          "success": {
            "type": "boolean",
            "description": "Indica si el proveedor está dentro del radio permitido del destino.",
            "example": true
          },
          "error_code": {
            "type": "string",
            "description": "Código de error en caso de success: false (Ej: 437, 451, 458, 479, 991).",
            "example": "437"
          }
        }
      }
    }
  }
}
```

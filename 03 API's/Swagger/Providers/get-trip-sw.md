### Consultar Información de Viaje

```json
{
  "openapi": "3.0.0",
  "info": {
    "title": "Provider Trip Discovery API",
    "description": "Endpoint que permite a los proveedores obtener solicitudes de viaje disponibles y detalles del cliente.",
    "version": "1.0.0"
  },
  "paths": {
    "/gettrips": {
      "post": {
        "summary": "Obtener viajes disponibles",
        "description": "Recupera la información del viaje asignado actualmente al proveedor.",
        "requestBody": {
          "required": true,
          "content": {
            "application/json": {
              "schema": {
                "$ref": "#/components/schemas/GetTripsRequest"
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "Datos del viaje recuperados con éxito",
            "content": {
              "application/json": {
                "schema": {
                  "$ref": "#/components/schemas/GetTripsResponse"
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
      "GetTripsRequest": {
        "type": "object",
        "required": [
          "provider_id",
          "token"
        ],
        "properties": {
          "provider_id": {
            "type": "string",
            "example": "{{PROVIDER_ID}}",
            "description": "Identificador único del proveedor."
          },
          "token": {
            "type": "string",
            "example": "{{PROVIDER_TOKEN}}",
            "description": "Token de autenticación activo."
          }
        }
      },
      "GetTripsResponse": {
        "type": "object",
        "properties": {
          "success": {
            "type": "boolean",
            "example": true
          },
          "message": {
            "type": "string",
            "example": "21"
          },
          "trip_id": {
            "type": "string",
            "example": "619f64c5d2a10642ca9e6f9f"
          },
          "source_address": {
            "type": "string",
            "example": "GJ SH 25, Sadar, Rajkot, Gujarat 360001, India"
          },
          "destination_address": {
            "type": "string",
            "example": "Rajkot"
          },
          "sourceLocation": {
            "type": "array",
            "items": {
              "type": "number"
            },
            "example": [22.3039971, 70.8022464],
            "description": "[Latitud, Longitud] de origen."
          },
          "destinationLocation": {
            "type": "array",
            "items": {
              "type": "number"
            },
            "example": [22.3039, 70.8022],
            "description": "[Latitud, Longitud] de destino."
          },
          "is_trip_end": {
            "type": "integer",
            "example": 0
          },
          "time_left_to_responds_trip": {
            "type": "integer",
            "description": "Segundos restantes para aceptar el viaje.",
            "example": 24
          },
          "user": {
            "type": "object",
            "properties": {
              "_id": { "type": "string", "example": "61978529e3a07451a82404a5" },
              "unique_id": { "type": "integer", "example": 36 },
              "first_name": { "type": "string", "example": "Android" },
              "last_name": { "type": "string", "example": "User" },
              "email": { "type": "string", "example": "android@user.com" },
              "phone": { "type": "string", "example": "9904385946" },
              "country_phone_code": { "type": "string", "example": "+91" },
              "rate": { "type": "number", "example": 0 },
              "wallet": { "type": "number", "example": 100 },
              "wallet_currency_code": { "type": "string", "example": "INR" },
              "device_type": { "type": "string", "example": "android" }
            }
          }
        }
      }
    }
  }
}
```

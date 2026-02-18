### Modificar Estatus de Viaje

```json

{
  "openapi": "3.0.0",
  "info": {
    "title": "Trip Status Management API",
    "description": "Endpoint para actualizar el estado del viaje .",
    "version": "1.0.0"
  },
  "paths": {
    "/settripstatus": {
      "post": {
        "summary": "Actualizar estado del viaje",
        "description": "Permite al proveedor notificar cambios en el progreso del viaje junto con sus coordenadas GPS actuales.",
        "requestBody": {
          "required": true,
          "content": {
            "application/json": {
              "schema": {
                "$ref": "#/components/schemas/SetTripStatusRequest"
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "Estado actualizado exitosamente",
            "content": {
              "application/json": {
                "schema": {
                  "$ref": "#/components/schemas/SetTripStatusResponse"
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
      "SetTripStatusRequest": {
        "type": "object",
        "required": [
          "trip_id",
          "provider_id",
          "token",
          "is_provider_status",
          "latitude",
          "longitude"
        ],
        "properties": {
          "trip_id": {
            "type": "string",
            "example": "{{TRIP_ID}}",
            "description": "ID único del viaje."
          },
          "provider_id": {
            "type": "string",
            "example": "{{PROVIDER_ID}}",
            "description": "ID único del proveedor."
          },
          "token": {
            "type": "string",
            "example": "{{PROVIDER_TOKEN}}",
            "description": "Token de sesión del proveedor."
          },
          "is_provider_status": {
            "type": "integer",
            "description": "Código de estado: 2 (Coming), 4 (Arrived), 6 (Started), 9 (Completed), etc.",
            "example": 2
          },
          "latitude": {
            "type": "number",
            "format": "double",
            "example": 22.3040217933851
          },
          "longitude": {
            "type": "number",
            "format": "double",
            "example": 70.80228966547214
          }
        }
      },
      "SetTripStatusResponse": {
        "type": "object",
        "properties": {
          "success": {
            "type": "boolean",
            "example": true
          },
          "message": {
            "type": "string",
            "example": "24"
          },
          "trip": {
            "type": "object",
            "properties": {
              "_id": { "type": "string", "example": "619f6c344ae0be5359c6cc85" },
              "unique_id": { "type": "integer", "example": 310 },
              "user_id": { "type": "string", "example": "61978529e3a07451a82404a5" },
              "provider_id": { "type": "string", "example": "61979073da10546535a80fc1" },
              "is_provider_status": { "type": "integer", "example": 6 },
              "source_address": { "type": "string", "example": "GJ SH 25, Sadar, Rajkot, Gujarat 360001, India" },
              "destination_address": { "type": "string", "example": "Rajkot" },
              "sourceLocation": {
                "type": "array",
                "items": { "type": "number" },
                "example": [22.30402674, 70.80228014]
              },
              "destinationLocation": {
                "type": "array",
                "items": { "type": "number" },
                "example": [22.28596647, 70.77092232]
              },
              "provider_arrived_time": { "type": "string", "format": "date-time", "example": "2021-11-25T11:11:16.288Z" },
              "provider_trip_start_time": { "type": "string", "format": "date-time", "example": "2021-11-25T11:12:18.944Z" },
              "total": { "type": "number", "example": 0 },
              "currency": { "type": "string", "example": "₹" },
              "currencycode": { "type": "string", "example": "INR" },
              "payment_mode": { "type": "integer", "example": 1 },
              "user_first_name": { "type": "string", "example": "Android" },
              "user_last_name": { "type": "string", "example": "User" },
              "invoice_number": { "type": "string", "example": "TA PTE 25112021 0000310" }
            }
          }
        }
      }
    }
  }
}

```

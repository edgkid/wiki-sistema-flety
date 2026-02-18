### Historial de Viajes de Proveedor

```json
{
  "openapi": "3.0.0",
  "info": {
    "title": "Provider History API",
    "description": "Endpoint para consultar el historial de viajes realizados por un proveedor.",
    "version": "1.0.0"
  },
  "paths": {
    "/providerhistory": {
      "post": {
        "summary": "Obtener historial de viajes",
        "description": "Retorna una lista con detalles de facturación, direcciones y estados de calificación.",
        "requestBody": {
          "required": true,
          "content": {
            "application/json": {
              "schema": {
                "$ref": "#/components/schemas/HistoryRequest"
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "Lista de viajes recuperada con éxito",
            "content": {
              "application/json": {
                "schema": {
                  "$ref": "#/components/schemas/HistoryResponse"
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
      "HistoryRequest": {
        "type": "object",
        "required": [
          "provider_id",
          "token"
        ],
        "properties": {
          "provider_id": {
            "type": "string",
            "example": "{{PROVIDER_ID}}"
          },
          "token": {
            "type": "string",
            "example": "{{PROVIDER_TOKEN}}"
          },
          "start_date": {
            "type": "string",
            "format": "date",
            "example": "2021-11-25"
          },
          "end_date": {
            "type": "string",
            "format": "date",
            "example": "2021-11-27"
          },
          "page": {
            "type": "integer",
            "default": 1,
            "example": 1
          }
        }
      },
      "HistoryResponse": {
        "type": "object",
        "properties": {
          "success": {
            "type": "boolean",
            "example": true
          },
          "trips": {
            "type": "array",
            "items": {
              "$ref": "#/components/schemas/TripItem"
            }
          }
        }
      },
      "TripItem": {
        "type": "object",
        "properties": {
          "trip_id": { "type": "string", "example": "61a0c441516fca576a82c46c" },
          "unique_id": { "type": "integer", "example": 316 },
          "invoice_number": { "type": "string", "example": "TA PTE 26112021 0000316" },
          "created_at": { "type": "string", "format": "date-time", "example": "2021-11-26T11:25:53.389Z" },
          "provider_trip_end_time": { "type": "string", "format": "date-time", "example": "2021-11-26T11:26:51.144Z" },
          "source_address": { "type": "string", "example": "Hospital Chowk, Rajkot, India" },
          "destination_address": { "type": "string", "example": "Hospital Chowk, Rajkot, India" },
          "total": { "type": "number", "example": 100 },
          "currency": { "type": "string", "example": "₹" },
          "currencycode": { "type": "string", "example": "INR" },
          "total_time": { "type": "integer", "example": 0 },
          "total_distance": { "type": "number", "example": 0 },
          "is_trip_completed": { "type": "integer", "enum": [0, 1], "example": 1 },
          "is_provider_rated": { "type": "integer", "enum": [0, 1], "example": 0 },
          "is_user_rated": { "type": "integer", "enum": [0, 1], "example": 1 },
          "first_name": { "type": "string", "example": "Android" },
          "last_name": { "type": "string", "example": "User" },
          "picture": { "type": "string", "example": "" }
        }
      }
    }
  }
}


```

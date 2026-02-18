
### Finalizar Viaje

```json
{
  "openapi": "3.0.0",
  "info": {
    "title": "Trip Completion API",
    "description": "Endpoint para finalizar un viaje activo.",
    "version": "1.0.0"
  },
  "paths": {
    "/completetrip": {
      "post": {
        "summary": "Finalizar viaje",
        "description": "Permite al proveedor completar el viaje enviando las coordenadas finales y el historial de ubicación para el cálculo de la tarifa.",
        "requestBody": {
          "required": true,
          "content": {
            "application/json": {
              "schema": {
                "$ref": "#/components/schemas/CompleteTripRequest"
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "Viaje completado exitosamente",
            "content": {
              "application/json": {
                "schema": {
                  "$ref": "#/components/schemas/CompleteTripResponse"
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
      "CompleteTripRequest": {
        "type": "object",
        "required": ["trip_id", "provider_id", "token", "latitude", "longitude"],
        "properties": {
          "trip_id": { "type": "string", "example": "{{TRIP_ID}}" },
          "provider_id": { "type": "string", "example": "{{PROVIDER_ID}}" },
          "token": { "type": "string", "example": "{{PROVIDER_TOKEN}}" },
          "latitude": { "type": "number", "format": "double", "example": 22.30396501831061 },
          "longitude": { "type": "number", "format": "double", "example": 70.80226626072988 },
          "destination_address": { "type": "string", "example": "SHOP NO-529 5TH FLOOR..." },
          "toll_amount": { "type": "number", "example": 0 },
          "location": {
            "type": "array",
            "description": "Historial de coordenadas [latitud, longitud, timestamp]",
            "items": {
              "type": "array",
              "items": { "type": "string" },
              "example": ["22.3040217933851", "70.80228966547214", "1637838681542"]
            }
          }
        }
      },
      "CompleteTripResponse": {
        "type": "object",
        "properties": {
          "success": { "type": "boolean", "example": true },
          "message": { "type": "string", "example": "28" },
          "trip": {
            "type": "object",
            "properties": {
              "_id": { "type": "string", "example": "619f71895bedc85f72791c9d" },
              "unique_id": { "type": "integer", "example": 311 },
              "total": { "type": "number", "example": 145 },
              "currency": { "type": "string", "example": "₹" },
              "is_provider_status": { "type": "integer", "example": 9 },
              "invoice_number": { "type": "string", "example": "TA PTE 25112021 0000311" },
              "provider_trip_end_time": { "type": "string", "format": "date-time" },
              "admin_currencycode": { "type": "string", "example": "VEF" }
            }
          },
          "tripservice": {
            "type": "object",
            "properties": {
              "service_type_name": { "type": "string", "example": "Suv" },
              "base_price": { "type": "number", "example": 95 },
              "min_fare": { "type": "number", "example": 100 },
              "price_per_unit_distance": { "type": "number", "example": 4 }
            }
          }
        }
      }
    }
  }
}
```

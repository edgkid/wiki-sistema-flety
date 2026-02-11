### Factura de Viaje

```json
{
  "openapi": "3.0.0",
  "info": {
    "title": "API de Finalización de Viajes",
    "description": "Endpoint que devuelve el resumen detallado de un viaje, incluyendo desglose de costos, detalles del servicio aplicado y datos del proveedor.",
    "version": "1.0.0"
  },
  "paths": {
    "/get_trip_summary": {
      "post": {
        "summary": "Obtener resumen del viaje por proveedor",
        "operationId": "getTripSummary",
        "tags": ["Trips"],
        "requestBody": {
          "required": true,
          "content": {
            "application/json": {
              "schema": {
                "type": "object",
                "properties": {
                  "provider_id": {
                    "type": "string",
                    "example": "61979073da10546535a80fc1"
                  }
                },
                "required": ["provider_id"]
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "Resumen del viaje recuperado exitosamente",
            "content": {
              "application/json": {
                "schema": {
                  "$ref": "#/components/schemas/TripSummaryResponse"
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
      "TripSummaryResponse": {
        "type": "object",
        "properties": {
          "success": { "type": "boolean", "example": true },
          "message": { "type": "string", "example": "38" },
          "trip": { "$ref": "#/components/schemas/TripDetails" },
          "tripservice": { "$ref": "#/components/schemas/TripService" },
          "provider_detail": { "$ref": "#/components/schemas/ProviderBrief" }
        }
      },
      "TripDetails": {
        "type": "object",
        "properties": {
          "_id": { "type": "string" },
          "unique_id": { "type": "integer" },
          "invoice_number": { "type": "string", "example": "TA PTE 25112021 0000314" },
          "source_address": { "type": "string" },
          "destination_address": { "type": "string" },
          "sourceLocation": { "type": "array", "items": { "type": "number" } },
          "destinationLocation": { "type": "array", "items": { "type": "number" } },
          "total": { "type": "number", "example": 147 },
          "cash_payment": { "type": "number", "example": 147 },
          "card_payment": { "type": "number", "example": 0 },
          "is_fixed_fare": { "type": "boolean" },
          "fixed_price": { "type": "number" },
          "currency": { "type": "string", "example": "₹" },
          "currencycode": { "type": "string", "example": "INR" },
          "admin_currency": { "type": "string", "example": "Bs" },
          "accepted_time": { "type": "string", "format": "date-time" },
          "provider_arrived_time": { "type": "string", "format": "date-time" },
          "provider_trip_start_time": { "type": "string", "format": "date-time" },
          "provider_trip_end_time": { "type": "string", "format": "date-time" },
          "is_trip_completed": { "type": "integer", "example": 0 },
          "is_paid": { "type": "integer", "example": 1 }
        }
      },
      "TripService": {
        "type": "object",
        "properties": {
          "_id": { "type": "string" },
          "service_type_name": { "type": "string", "example": "Suv" },
          "base_price": { "type": "number", "example": 95 },
          "min_fare": { "type": "number", "example": 100 },
          "price_per_unit_distance": { "type": "number", "example": 4 },
          "cancellation_fee": { "type": "number", "example": 90 }
        }
      },
      "ProviderBrief": {
        "type": "object",
        "properties": {
          "first_name": { "type": "string" },
          "last_name": { "type": "string" },
          "picture": { "type": "string" }
        }
      }
    }
  }
}

```

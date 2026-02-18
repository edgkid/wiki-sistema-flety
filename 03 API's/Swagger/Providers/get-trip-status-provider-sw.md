### Consulta de Viaje Proveedo

```json
{
  "openapi": "3.0.0",
  "info": {
    "title": "Provider Trip Status API",
    "description": "Endpoint para que el proveedor consulte el estado detallado de un viaje.",
    "version": "1.0.0"
  },
  "paths": {
    "/providergettripstatus": {
      "post": {
        "summary": "Obtener estado actual del viaje",
        "description": "Retorna información en tiempo real sobre la ubicación, el cliente y el servicio asociado a un ID de viaje específico.",
        "requestBody": {
          "required": true,
          "content": {
            "application/json": {
              "schema": {
                "$ref": "#/components/schemas/TripStatusRequest"
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "Detalles del estado del viaje obtenidos correctamente",
            "content": {
              "application/json": {
                "schema": {
                  "$ref": "#/components/schemas/TripStatusResponse"
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
      "TripStatusRequest": {
        "type": "object",
        "required": ["provider_id", "token", "trip_id"],
        "properties": {
          "provider_id": { "type": "string", "example": "{{PROVIDER_ID}}" },
          "token": { "type": "string", "example": "{{PROVIDER_TOKEN}}" },
          "trip_id": { "type": "string", "example": "{{TRIP_ID}}" }
        }
      },
      "TripStatusResponse": {
        "type": "object",
        "properties": {
          "success": { "type": "boolean", "example": true },
          "map_pin_image_url": { "type": "string", "example": "service_type_map_pin_images/image.png" },
          "message": { "type": "string", "example": "25" },
          "country_phone_code": { "type": "string", "example": "+91" },
          "phone": { "type": "string", "example": "9904385946" },
          "trip": {
            "type": "object",
            "properties": {
              "_id": { "type": "string", "example": "619e4b38a3a3924e076c55a5" },
              "unique_id": { "type": "integer", "example": 301 },
              "sourceLocation": { 
                "type": "array", 
                "items": { "type": "number" }, 
                "example": [22.3039291, 70.8020043] 
              },
              "destinationLocation": { 
                "type": "array", 
                "items": { "type": "number" }, 
                "example": [22.3039, 70.8022] 
              },
              "payment_mode": { "type": "integer", "example": 1 },
              "currencycode": { "type": "string", "example": "INR" },
              "currency": { "type": "string", "example": "₹" },
              "status": { "type": "integer", "example": 0 },
              "source_address": { "type": "string", "example": "Hospital Chowk, Rajkot" },
              "destination_address": { "type": "string", "example": "Rajkot" }
            }
          },
          "user": {
            "type": "object",
            "properties": {
              "_id": { "type": "string", "example": "61978529e3a07451a82404a5" },
              "first_name": { "type": "string", "example": "Android" },
              "last_name": { "type": "string", "example": "User" },
              "email": { "type": "string", "example": "android@user.com" },
              "wallet": { "type": "number", "example": 100 },
              "wallet_currency_code": { "type": "string", "example": "INR" }
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
          },
          "waiting_time_start_after_minute": { "type": "integer", "example": 1 },
          "price_for_waiting_time": { "type": "number", "example": 20 },
          "total_wait_time": { "type": "number", "example": -55 }
        }
      }
    }
  }
}
```

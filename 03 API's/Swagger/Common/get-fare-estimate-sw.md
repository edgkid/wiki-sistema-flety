### Calculo de Tarifa

```json
{
  "openapi": "3.0.0",
  "info": {
    "title": "Fare Estimate API",
    "description": "Endpoint para calcular la estimación de tarifa de un viaje basado en distancia, tiempo y tipo de servicio.",
    "version": "1.0.0"
  },
  "servers": [
    {
      "url": "{{URL}}",
      "description": "Servidor de Desarrollo"
    }
  ],
  "paths": {
    "/getfareestimate": {
      "post": {
        "summary": "Obtener estimación de tarifa",
        "operationId": "getFareEstimate",
        "requestBody": {
          "required": true,
          "content": {
            "application/json": {
              "schema": {
                "$ref": "#/components/schemas/FareRequest"
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "Estimación calculada exitosamente",
            "content": {
              "application/json": {
                "schema": {
                  "$ref": "#/components/schemas/FareResponse"
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
      "FareRequest": {
        "type": "object",
        "properties": {
          "distance": { "type": "integer", "example": 5000 },
          "time": { "type": "integer", "example": 600 },
          "service_type_id": { "type": "string", "example": "602278c765b27b2840e6ea1e" },
          "is_surge_hours": { "type": "integer", "example": 0 },
          "surge_multiplier": { "type": "integer", "example": 0 },
          "pickup_latitude": { "type": "number", "format": "float", "example": 22.30393797226562 },
          "pickup_longitude": { "type": "number", "format": "float", "example": 70.80198041880888 },
          "destination_latitude": { "type": "number", "format": "float", "example": 22.3039 },
          "destination_longitude": { "type": "number", "format": "float", "example": 70.8022 }
        }
      },
      "FareResponse": {
        "type": "object",
        "properties": {
          "success": { "type": "boolean", "example": true },
          "trip_type": { "type": "string", "example": "0" },
          "user_tax_fee": { "type": "integer", "example": 0 },
          "user_miscellaneous_fee": { "type": "integer", "example": 0 },
          "message": { "type": "string", "example": "36" },
          "time": { "type": "number", "example": 10.00002 },
          "distance": { "type": "string", "example": "5.00" },
          "is_min_fare_used": { "type": "integer", "example": 0 },
          "base_price": { "type": "integer", "example": 95 },
          "price_per_unit_distance": { "type": "integer", "example": 0 },
          "price_per_unit_time": { "type": "integer", "example": 40 },
          "estimated_fare": { "type": "integer", "example": 135 },
          "unit_set": { "type": "integer", "example": 1 }
        }
      }
    }
  }
}
```

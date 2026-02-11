### Obtener Detalle de Viaje de Usuario

```json
{
  "openapi": "3.0.0",
  "info": {
    "title": "User Trip Detail API",
    "description": "API para obtener los detalles  de un viaje realizado por un usuario.",
    "version": "1.0.0"
  },
  "servers": [
    {
      "url": "{{URL}}",
      "description": "Servidor principal"
    }
  ],
  "paths": {
    "/usertripdetail": {
      "post": {
        "summary": "Obtener detalles del viaje",
        "operationId": "getUserTripDetail",
        "requestBody": {
          "required": true,
          "content": {
            "application/json": {
              "schema": {
                "$ref": "#/components/schemas/TripRequest"
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "Detalles del viaje recuperados con éxito",
            "content": {
              "application/json": {
                "schema": {
                  "$ref": "#/components/schemas/TripResponse"
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
      "TripRequest": {
        "type": "object",
        "required": ["user_id", "token", "trip_id"],
        "properties": {
          "user_id": { "type": "string", "example": "61978529e3a07451a82404a5" },
          "token": { "type": "string", "example": "USER_TOKEN_HERE" },
          "trip_id": { "type": "string", "example": "619f99ecc68548396ff542a4" }
        }
      },
      "TripResponse": {
        "type": "object",
        "properties": {
          "success": { "type": "boolean" },
          "message": { "type": "integer", "example": 15 },
          "trip": { "$ref": "#/components/schemas/TripDetail" },
          "tripservice": { "$ref": "#/components/schemas/TripService" },
          "provider": { "$ref": "#/components/schemas/ProviderDetail" }
        }
      },
      "TripDetail": {
        "type": "object",
        "properties": {
          "_id": { "type": "string" },
          "unique_id": { "type": "integer" },
          "source_address": { "type": "string" },
          "destination_address": { "type": "string" },
          "sourceLocation": { "type": "array", "items": { "type": "number" } },
          "destinationLocation": { "type": "array", "items": { "type": "number" } },
          "total": { "type": "number" },
          "cash_payment": { "type": "number" },
          "currency": { "type": "string" },
          "admin_currency": { "type": "string" },
          "is_trip_completed": { "type": "integer" },
          "provider_first_name": { "type": "string" },
          "provider_last_name": { "type": "string" },
          "user_first_name": { "type": "string" },
          "user_last_name": { "type": "string" },
          "invoice_number": { "type": "string" },
          "created_at": { "type": "string", "format": "date-time" }
        }
      },
      "TripService": {
        "type": "object",
        "properties": {
          "_id": { "type": "string" },
          "service_type_name": { "type": "string" },
          "base_price": { "type": "number" },
          "min_fare": { "type": "number" },
          "max_space": { "type": "integer" }
        }
      },
      "ProviderDetail": {
        "type": "object",
        "properties": {
          "_id": { "type": "string" },
          "unique_id": { "type": "integer" },
          "service_type": { "type": "string" },
          "cityid": { "type": "string" },
          "country_id": { "type": "string" }
        }
      }
    }
  }
}

```

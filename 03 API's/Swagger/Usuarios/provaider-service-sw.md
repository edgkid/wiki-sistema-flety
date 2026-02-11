### Consultar Lista de Proveedores

```json
{
  "openapi": "3.0.0",
  "info": {
    "title": "API de Proveedores de Servicios",
    "description": "Endpoint para obtener la lista de proveedores cercanos basados en la ubicación del usuario.",
    "version": "1.0.0"
  },
  "paths": {
    "/providers": {
      "post": {
        "summary": "Obtener proveedores cercanos",
        "operationId": "getProviders",
        "requestBody": {
          "required": true,
          "content": {
            "application/json": {
              "schema": {
                "$ref": "#/components/schemas/ProviderRequest"
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "Lista de proveedores encontrada con éxito",
            "content": {
              "application/json": {
                "schema": {
                  "$ref": "#/components/schemas/ProviderResponse"
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
      "ProviderRequest": {
        "type": "object",
        "properties": {
          "user_id": { "type": "string", "example": "12345" },
          "token": { "type": "string", "example": "abcde12345token" },
          "latitude": { "type": "string", "example": "22.300242857807394" },
          "longitude": { "type": "string", "example": "70.79921440497847" }
        },
        "required": ["user_id", "token", "latitude", "longitude"]
      },
      "ProviderResponse": {
        "type": "object",
        "properties": {
          "success": { "type": "boolean", "example": true },
          "message": { "type": "string", "example": "35" },
          "providers": {
            "type": "array",
            "items": { "$ref": "#/components/schemas/Provider" }
          }
        }
      },
      "Provider": {
        "type": "object",
        "properties": {
          "_id": { "type": "string", "example": "61979073da10546535a80fc1" },
          "unique_id": { "type": "integer", "example": 20 },
          "service_type": { "type": "string" },
          "cityid": { "type": "string" },
          "country_id": { "type": "string" },
          "providerLocation": {
            "type": "array",
            "items": { "type": "number" },
            "example": [22.3039, 70.8022]
          },
          "first_name": { "type": "string", "example": "Nick" },
          "last_name": { "type": "string", "example": "Duo" },
          "email": { "type": "string", "format": "email", "example": "nick@driver.com" },
          "phone": { "type": "string", "example": "9876543210" },
          "is_available": { "type": "integer", "example": 1 },
          "is_active": { "type": "integer", "example": 1 },
          "wallet": { "type": "number", "example": 215 },
          "wallet_currency_code": { "type": "string", "example": "INR" },
          "vehicle_detail": {
            "type": "array",
            "items": { "$ref": "#/components/schemas/VehicleDetail" }
          },
          "updated_at": { "type": "string", "format": "date-time" },
          "created_at": { "type": "string", "format": "date-time" }
        }
      },
      "VehicleDetail": {
        "type": "object",
        "properties": {
          "_id": { "type": "string" },
          "name": { "type": "string", "example": "Scooter" },
          "plate_no": { "type": "string", "example": "1111" },
          "model": { "type": "string", "example": "Access" },
          "color": { "type": "string", "example": "Black" },
          "is_selected": { "type": "boolean", "example": true },
          "accessibility": {
            "type": "array",
            "items": { "type": "string" },
            "example": ["baby_seat", "hotspot"]
          }
        }
      }
    }
  }
}

```

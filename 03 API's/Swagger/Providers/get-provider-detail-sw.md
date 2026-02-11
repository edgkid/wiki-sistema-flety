### Consulta Detallada de Proveedor

```json
{
  "openapi": "3.0.0",
  "info": {
    "title": "Provider Detail API - Get detail",
    "description": "Servicio para obtener la información detallada de un proveedor.",
    "version": "1.0.0"
  },
  "servers": [
    {
      "url": "{{URL}}",
      "description": "Servidor base"
    }
  ],
  "paths": {
    "/get_provider_detail": {
      "post": {
        "summary": "Obtener detalles del proveedor",
        "operationId": "getProviderDetail",
        "requestBody": {
          "required": true,
          "content": {
            "application/json": {
              "schema": {
                "type": "object",
                "required": ["provider_id", "token", "app_version"],
                "properties": {
                  "provider_id": { "type": "string", "example": "{{PROVIDER_ID}}" },
                  "token": { "type": "string", "example": "{{PROVIDER_TOKEN}}" },
                  "app_version": { "type": "string", "example": "1.1.9" }
                }
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "Detalles recuperados exitosamente",
            "content": {
              "application/json": {
                "schema": {
                  "$ref": "#/components/schemas/ProviderDetailResponse"
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
      "ProviderDetailResponse": {
        "type": "object",
        "properties": {
          "success": { "type": "boolean", "example": true },
          "partner_detail": {
            "type": "object",
            "properties": {
              "wallet": { "type": "number", "example": 0 }
            }
          },
          "message": { "type": "string", "example": "32" },
          "provider": { "$ref": "#/components/schemas/Provider" }
        }
      },
      "Provider": {
        "type": "object",
        "properties": {
          "_id": { "type": "string", "example": "61979073da10546535a80fc1" },
          "unique_id": { "type": "integer", "example": 20 },
          "first_name": { "type": "string", "example": "Nick" },
          "last_name": { "type": "string", "example": "Duo" },
          "email": { "type": "string", "example": "nick@driver.com" },
          "phone": { "type": "string", "example": "9876543210" },
          "country_phone_code": { "type": "string", "example": "+91" },
          "address": { "type": "string", "example": "Rajkot" },
          "city": { "type": "string", "example": "Rajkot" },
          "country": { "type": "string", "example": "India" },
          "token": { "type": "string", "example": "0U0RxuLEeCp9gUUh80rrUI1vQis3q4wo" },
          "wallet": { "type": "number", "example": 0 },
          "wallet_currency_code": { "type": "string", "example": "INR" },
          "is_available": { "type": "integer", "example": 1 },
          "is_approved": { "type": "integer", "example": 0 },
          "is_active": { "type": "integer", "example": 0 },
          "providerLocation": {
            "type": "array",
            "items": { "type": "number" },
            "example": [0, 0]
          },
          "referral_code": { "type": "string", "example": "M44W0YRU" },
          "app_version": { "type": "string", "example": "1.1.9" },
          "device_type": { "type": "string", "example": "android" },
          "created_at": { "type": "string", "format": "date-time", "example": "2021-11-19T11:54:27.110Z" },
          "updated_at": { "type": "string", "format": "date-time", "example": "2021-11-19T12:19:33.478Z" }
        }
      }
    }
  }
}

```

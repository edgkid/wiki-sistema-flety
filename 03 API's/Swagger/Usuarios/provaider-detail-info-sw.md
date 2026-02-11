
### Consulta Detallada de Proveedor 

```json
{
  "openapi": "3.0.0",
  "info": {
    "title": "API de Gestión de Proveedores - detalle de proveedor",
    "description": "Endpoint para obtener el perfil detallado, estado de disponibilidad y detalles del vehículo.",
    "version": "1.0.0"
  },
  "paths": {
    "/get_provider_details": {
      "post": {
        "summary": "Obtener detalles del proveedor",
        "operationId": "getProviderDetails",
        "tags": ["Providers"],
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
            "description": "Perfil del proveedor recuperado con éxito",
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
          "message": { "type": "string", "example": "32" },
          "provider": { "$ref": "#/components/schemas/ProviderProfile" }
        }
      },
      "ProviderProfile": {
        "type": "object",
        "properties": {
          "_id": { "type": "string" },
          "unique_id": { "type": "integer" },
          "first_name": { "type": "string", "example": "Nick" },
          "last_name": { "type": "string", "example": "Duo" },
          "email": { "type": "string", "format": "email" },
          "phone": { "type": "string" },
          "providerLocation": {
            "type": "array",
            "items": { "type": "number" },
            "example": [22.3039, 70.8022]
          },
          "is_available": { "type": "integer", "example": 0 },
          "is_active": { "type": "integer", "example": 1 },
          "total_request": { "type": "integer", "example": 15 },
          "accepted_request": { "type": "integer", "example": 3 },
          "rejected_request": { "type": "integer", "example": 5 },
          "cancelled_request": { "type": "integer", "example": 0 },
          "wallet": { "type": "number", "example": 215 },
          "wallet_currency_code": { "type": "string", "example": "INR" },
          "device_token": { "type": "string" },
          "vehicle_detail": {
            "type": "array",
            "items": { "$ref": "#/components/schemas/VehicleDetail" }
          },
          "is_trip": {
            "type": "array",
            "items": { "type": "string" },
            "example": ["619e503272

```

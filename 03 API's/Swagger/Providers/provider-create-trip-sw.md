### Crear Viaje - Proveedor

```json
{
  "openapi": "3.0.0",
  "info": {
    "title": "Provider Trip Management API",
    "description": "Servicios para la creación y gestión de viajes por parte del proveedor (conductor).",
    "version": "1.0.0"
  },
  "paths": {
    "/provider_createtrip": {
      "post": {
        "summary": "Crear un nuevo viaje",
        "description": "Permite a un proveedor iniciar la creación de un viaje proporcionando los datos del cliente y la ubicación de origen/destino.",
        "requestBody": {
          "required": true,
          "content": {
            "application/json": {
              "schema": {
                "$ref": "#/components/schemas/CreateTripRequest"
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "Operación procesada (puede ser éxito o error de negocio)",
            "content": {
              "application/json": {
                "schema": {
                  "oneOf": [
                    { "$ref": "#/components/schemas/CreateTripSuccessResponse" },
                    { "$ref": "#/components/schemas/ErrorResponse" }
                  ]
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
      "CreateTripRequest": {
        "type": "object",
        "required": [
          "provider_id",
          "token",
          "latitude",
          "longitude",
          "service_type_id"
        ],
        "properties": {
          "d_latitude": { "type": "number", "example": 22.2834787, "description": "Latitud de destino" },
          "d_longitude": { "type": "number", "example": 70.811252, "description": "Longitud de destino" },
          "destination_address": { "type": "string", "example": "Sorthiyawadi, Rajkot", "description": "Dirección completa de destino" },
          "latitude": { "type": "number", "example": 22.303695, "description": "Latitud de origen" },
          "longitude": { "type": "number", "example": 70.801638, "description": "Longitud de origen" },
          "source_address": { "type": "string", "example": "Hospital Chowk, Rajkot", "description": "Dirección completa de origen" },
          "provider_id": { "type": "string", "example": "{{PROVIDER_ID}}" },
          "token": { "type": "string", "example": "{{PROVIDER_TOKEN}}" },
          "first_name": { "type": "string", "example": "Android" },
          "last_name": { "type": "string", "example": "User" },
          "email": { "type": "string", "format": "email", "example": "android@user.com" },
          "country_phone_code": { "type": "string", "example": "+91" },
          "phone": { "type": "string", "example": "9904385946" },
          "timezone": { "type": "string", "example": "Asia/Kolkata" },
          "payment_mode": { "type": "integer", "example": 1, "description": "1: Cash, 2: Card, 3: Wallet" },
          "service_type_id": { "type": "string", "example": "602278c765b27b2840e6ea1e" },
          "is_surge_hours": { "type": "integer", "enum": [0, 1], "example": 0 },
          "surge_multiplier": { "type": "number", "example": 0 }
        }
      },
      "CreateTripSuccessResponse": {
        "type": "object",
        "properties": {
          "success": { "type": "boolean", "example": true },
          "message": { "type": "string", "example": "9" },
          "trip_id": { "type": "string", "example": "61a0c441516fca576a82c46c" },
          "user": {
            "type": "object",
            "properties": {
              "_id": { "type": "string", "example": "61978529e3a07451a82404a5" },
              "unique_id": { "type": "integer", "example": 36 },
              "first_name": { "type": "string", "example": "Android" },
              "last_name": { "type": "string", "example": "User" },
              "wallet_currency_code": { "type": "string", "example": "INR" },
              "is_approved": { "type": "integer", "example": 1 },
              "token": { "type": "string", "example": "xdFYKFsDC..." }
            }
          }
        }
      },
      "ErrorResponse": {
        "type": "object",
        "properties": {
          "success": { "type": "boolean", "example": false },
          "error_code": { 
            "type": "string", 
            "example": "995",
            "description": "Códigos posibles: 995 (Trip Running), 810 (Type Not Found), 1003 (Area Off), etc."
          }
        }
      }
    }
  }
}
```

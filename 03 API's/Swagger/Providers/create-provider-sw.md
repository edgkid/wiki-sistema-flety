### Registrar Conductor

```json
{
  "openapi": "3.0.0",
  "info": {
    "title": "Provider Registration API",
    "description": "API para el registro de nuevos proveedores de servicios.",
    "version": "1.0.0"
  },
  "servers": [
    {
      "url": "{{URL}}",
      "description": "Servidor de desarrollo"
    }
  ],
  "paths": {
    "/providerregister": {
      "post": {
        "summary": "Registrar un nuevo proveedor",
        "operationId": "registerProvider",
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
            "description": "Registro exitoso",
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
          "first_name": { "type": "string", "example": "Nick" },
          "last_name": { "type": "string", "example": "Duo" },
          "email": { "type": "string", "format": "email", "example": "nick@driver.com" },
          "password": { "type": "string", "example": "123456" },
          "country_phone_code": { "type": "string", "example": "+91" },
          "phone": { "type": "string", "example": "9876543210" },
          "country": { "type": "string", "example": "India" },
          "country_id": { "type": "string", "example": "6022776065b27b2840e6ea1c" },
          "city": { "type": "string", "example": "Rajkot, Gujarat" },
          "city_id": { "type": "string", "example": "6022777b65b27b2840e6ea1d" },
          "address": { "type": "string", "example": "Rajkot" },
          "zipcode": { "type": "string", "example": "" },
          "bio": { "type": "string", "example": "" },
          "service_type": { "type": "string", "example": "" },
          "device_type": { "type": "string", "example": "android" },
          "device_token": { "type": "string", "example": "f5cKdH3CRqaE7e4XfDg6HU:APA91..." },
          "device_timezone": { "type": "string", "example": "Asia/Kolkata" },
          "app_version": { "type": "string", "example": "1.1.9" },
          "login_by": { "type": "string", "example": "manual" }
        }
      },
      "ProviderResponse": {
        "type": "object",
        "properties": {
          "success": { "type": "boolean", "example": true },
          "message": { "type": "string", "example": "16" },
          "provider_detail": {
            "type": "object",
            "properties": {
              "first_name": { "type": "string" },
              "last_name": { "type": "string" },
              "email": { "type": "string" },
              "country_phone_code": { "type": "string" },
              "is_document_uploaded": { "type": "integer" },
              "address": { "type": "string" },
              "is_approved": { "type": "integer" },
              "_id": { "type": "string" },
              "social_unique_id": { "type": "string" },
              "phone": { "type": "string" },
              "login_by": { "type": "string" },
              "is_documents_expired": { "type": "boolean" },
              "account_id": { "type": "string" },
              "bank_id": { "type": "string" },
              "city": { "type": "string" },
              "country": { "type": "string" },
              "rate": { "type": "number" },
              "rate_count": { "type": "integer" },
              "is_referral": { "type": "integer" },
              "token": { "type": "string" },
              "referral_code": { "type": "string" },
              "is_vehicle_document_uploaded": { "type": "boolean" },
              "service_type": { "type": "string", "nullable": true },
              "admintypeid": { "type": "string", "nullable": true },
              "is_available": { "type": "integer" },
              "is_active": { "type": "integer" },
              "is_partner_approved_by_admin": { "type": "integer" },
              "picture": { "type": "string" },
              "wallet_currency_code": { "type": "string" },
              "country_detail": {
                "type": "object",
                "properties": {
                  "is_referral": { "type": "boolean" }
                }
              }
            }
          },
          "phone_number_min_length": { "type": "integer", "example": 10 },
          "phone_number_length": { "type": "integer", "example": 10 }
        }
      }
    }
  }
}

```

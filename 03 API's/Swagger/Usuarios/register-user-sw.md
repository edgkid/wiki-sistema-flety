
### Registro de Usarios

```json
{
  "openapi": "3.0.0",
  "info": {
    "title": "API de Registro de Usuario",
    "version": "1.0.0",
    "description": "API para el registro de nuevos usuarios en el sistema."
  },
  "servers": [
    {
      "url": "{{URL}}",
      "description": "Servidor Principal"
    }
  ],
  "paths": {
    "/userregister": {
      "post": {
        "summary": "Registrar un nuevo usuario",
        "operationId": "userRegister",
        "requestBody": {
          "description": "Datos necesarios para registrar un nuevo usuario",
          "required": true,
          "content": {
            "application/json": {
              "schema": {
                "$ref": "#/components/schemas/UserRegistrationRequest"
              },
              "example": {
                "first_name": "Android",
                "last_name": "User",
                "email": "android@user.com",
                "country_phone_code": "+91",
                "phone": "9904385946",
                "password": "123456",
                "device_token": "12121212",
                "device_type": "android",
                "bio": "My Bio",
                "address": "Rajkot",
                "zipcode": "123456",
                "social_unique_id": "",
                "login_by": "manual",
                "device_timezone": "UTC",
                "city": "Rajkot",
                "country": "India"
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
                  "$ref": "#/components/schemas/UserRegistrationResponse"
                },
                "example": {
                  "success": true,
                  "message": "1",
                  "user_detail": {
                    "user_id": "string",
                    "first_name": "string",
                    "last_name": "string",
                    "email": "string",
                    "phone": "string",
                    "token": "string",
                    "referral_code": "string"
                  }
                }
              }
            }
          },
          "400": {
            "description": "Solicitud incorrecta o error de validación"
          }
        }
      }
    }
  },
  "components": {
    "schemas": {
      "UserRegistrationRequest": {
        "type": "object",
        "properties": {
          "first_name": { "type": "string", "example": "Android" },
          "last_name": { "type": "string", "example": "User" },
          "email": { "type": "string", "format": "email", "example": "android@user.com" },
          "country_phone_code": { "type": "string", "example": "+91" },
          "phone": { "type": "string", "example": "9904385946" },
          "password": { "type": "string", "format": "password", "example": "123456" },
          "device_token": { "type": "string", "example": "12121212" },
          "device_type": { "type": "string", "enum": ["android", "ios"], "example": "android" },
          "bio": { "type": "string", "example": "My Bio" },
          "address": { "type": "string", "example": "Rajkot" },
          "zipcode": { "type": "string", "example": "123456" },
          "social_unique_id": { "type": "string", "nullable": true, "example": "" },
          "login_by": { "type": "string", "enum": ["manual", "facebook", "google"], "example": "manual" },
          "device_timezone": { "type": "string", "example": "UTC" },
          "city": { "type": "string", "example": "Rajkot" },
          "country": { "type": "string", "example": "India" }
        },
        "required": [
          "first_name",
          "last_name",
          "email",
          "country_phone_code",
          "phone",
          "password",
          "device_token",
          "device_type",
          "login_by"
        ]
      },
      "UserDetail": {
        "type": "object",
        "properties": {
          "user_id": { "type": "string" },
          "first_name": { "type": "string" },
          "last_name": { "type": "string" },
          "email": { "type": "string", "format": "email" },
          "phone": { "type": "string" },
          "token": { "type": "string" },
          "referral_code": { "type": "string" }
        }
      },
      "UserRegistrationResponse": {
        "type": "object",
        "properties": {
          "success": { "type": "boolean" },
          "message": { "type": "string" },
          "user_detail": { "$ref": "#/components/schemas/UserDetail" }
        },
        "required": ["success", "message", "user_detail"]
      }
    }
  }
}

```

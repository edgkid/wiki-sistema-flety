### Inicio de Sesión

```json
{
  "openapi": "3.0.0",
  "info": {
    "title": "API de Inicio de Sesión",
    "version": "1.0.0",
    "description": "Endpoint para que un usuario inicie sesión en la aplicación."
  },
  "servers": [
    {
      "url": "{{URL}}",
      "description": "Servidor Base de la API"
    }
  ],
  "paths": {
    "/userslogin": {
      "post": {
        "summary": "Autenticación de Usuario",
        "operationId": "userLogin",
        "requestBody": {
          "description": "Credenciales y datos del dispositivo para el login",
          "required": true,
          "content": {
            "application/x-www-form-urlencoded": {
              "schema": {
                "$ref": "#/components/schemas/LoginRequest"
              },
              "example": {
                "email": "9904385946",
                "password": "123456",
                "device_type": "android",
                "device_token": "1ede0868733d56ae7b8a5c434a0877cb97b65d9ba4f666f7d34f12dfd0159162",
                "login_by": "manual",
                "app_version": "1.0",
                "social_unique_id": "",
                "country_phone_code": "+91"
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "Inicio de sesión exitoso. Devuelve los detalles del usuario y el token de sesión.",
            "content": {
              "application/json": {
                "schema": {
                  "$ref": "#/components/schemas/LoginResponse"
                },
                "example": {
                  "success": true,
                  "user_detail": {
                    "first_name": "Android",
                    "last_name": "User",
                    "email": "android@user.com",
                    "country_phone_code": "+91",
                    "is_document_uploaded": 1,
                    "address": "Rajkot",
                    "is_approved": 1,
                    "user_id": "61962d683b0daa5338204ce6",
                    "social_ids": [],
                    "social_unique_id": "",
                    "login_by": "manual",
                    "city": "Rajkot",
                    "country": "India",
                    "referral_code": "YUR85FNS",
                    "rate": 0,
                    "rate_count": 0,
                    "is_referral": 0,
                    "token": "J0CUZ3si9T2KZYPIHYVPLjA6TyGq5QhX",
                    "phone": "9904385946",
                    "picture": "",
                    "wallet_currency_code": "INR",
                    "country_detail": {
                      "is_referral": true
                    }
                  }
                }
              }
            }
          },
          "401": {
            "description": "Credenciales inválidas (No autorizado)"
          }
        }
      }
    }
  },
  "components": {
    "schemas": {
      "LoginRequest": {
        "type": "object",
        "properties": {
          "email": { "type": "string", "description": "Correo electrónico o número de teléfono del usuario." },
          "password": { "type": "string", "format": "password" },
          "device_type": { "type": "string", "enum": ["android", "ios", "web"] },
          "device_token": { "type": "string", "description": "Token para notificaciones push." },
          "login_by": { "type": "string", "enum": ["manual", "facebook", "google"] },
          "app_version": { "type": "string" },
          "social_unique_id": { "type": "string", "nullable": true },
          "country_phone_code": { "type": "string" }
        },
        "required": ["email", "password", "device_type", "device_token", "login_by"]
      },
      "CountryDetail": {
        "type": "object",
        "properties": {
          "is_referral": { "type": "boolean" }
        }
      },
      "UserDetail": {
        "type": "object",
        "properties": {
          "first_name": { "type": "string" },
          "last_name": { "type": "string" },
          "email": { "type": "string", "format": "email" },
          "country_phone_code": { "type": "string" },
          "is_document_uploaded": { "type": "integer", "description": "Indicador binario (1 o 0)." },
          "address": { "type": "string" },
          "is_approved": { "type": "integer", "description": "Indicador binario (1 o 0)." },
          "user_id": { "type": "string" },
          "social_ids": { "type": "array", "items": {} },
          "social_unique_id": { "type": "string" },
          "login_by": { "type": "string" },
          "city": { "type": "string" },
          "country": { "type": "string" },
          "referral_code": { "type": "string" },
          "rate": { "type": "number", "format": "float" },
          "rate_count": { "type": "integer" },
          "is_referral": { "type": "integer", "description": "Indicador binario (1 o 0)." },
          "token": { "type": "string", "description": "Token de autenticación de sesión generado." },
          "phone": { "type": "string" },
          "picture": { "type": "string", "format": "url", "nullable": true },
          "wallet_currency_code": { "type": "string" },
          "country_detail": { "$ref": "#/components/schemas/CountryDetail" }
        },
        "required": ["first_name", "user_id", "token", "phone"]
      },
      "LoginResponse": {
        "type": "object",
        "properties": {
          "success": { "type": "boolean" },
          "user_detail": { "$ref": "#/components/schemas/UserDetail" }
        },
        "required": ["success", "user_detail"]
      }
    }
  }
}

```

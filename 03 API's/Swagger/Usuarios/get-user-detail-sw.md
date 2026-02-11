### Consulta Detallada de Usuario

```json
{
  "openapi": "3.0.0",
  "info": {
    "title": "API de consulta de Usuario",
    "version": "1.0.0",
    "description": "Endpoint para recuperar todos los detalles de un usuario específico."
  },
  "servers": [
    {
      "url": "https://{{URL}}",
      "description": "Servidor principal (reemplazar {{URL}})"
    }
  ],
  "paths": {
    "/getuserdetail": {
      "post": {
        "summary": "Obtener detalles completos del usuario",
        "operationId": "getUserDetail",
        "requestBody": {
          "required": true,
          "content": {
            "application/json": {
              "schema": {
                "$ref": "#/components/schemas/GetUserDetailRequest"
              },
              "examples": {
                "UserDetailRequestExample": {
                  "value": {
                    "user_id": "{{USER_ID}}",
                    "token": "{{USER_TOKEN}}"
                  }
                }
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "Recuperación exitosa de los detalles del usuario",
            "content": {
              "application/json": {
                "schema": {
                  "$ref": "#/components/schemas/GetUserDetailResponse"
                },
                "examples": {
                  "SuccessfulDetailResponse": {
                    "value": {
                      "success": true,
                      "message": "33",
                      "user_id": "61962d683b0daa5338204ce6",
                      "first_name": "Android",
                      "last_name": "User",
                      "country_phone_code": "+91",
                      "phone": "9904385946",
                      "email": "android@user.com",
                      "wallet": 0,
                      "wallet_currency_code": "INR",
                      "picture": "",
                      "bio": "Bio",
                      "address": "Rajkot",
                      "city": "",
                      "country": "India",
                      "zipcode": "1234567",
                      "login_by": "manual",
                      "gender": "",
                      "social_unique_id": "",
                      "social_ids": [],
                      "device_token": "",
                      "device_type": "android",
                      "device_timezone": "UTC",
                      "referral_code": "YUR85FNS",
                      "token": "hu2hGFrvNuyOohJnCqPji8fY0iC48nAL",
                      "is_approved": 1,
                      "app_version": "1.0",
                      "is_referral": 0,
                      "is_document_uploaded": 1,
                      "country_detail": {
                        "is_referral": true
                      },
                      "rate": 0,
                      "rate_count": 0
                    }
                  }
                }
              }
            }
          },
          "401": {
            "description": "No Autorizado (Token Inválido o Expirado)"
          },
          "404": {
            "description": "Usuario no encontrado"
          }
        }
      }
    }
  },
  "components": {
    "schemas": {
      "GetUserDetailRequest": {
        "type": "object",
        "properties": {
          "user_id": {
            "type": "string",
            "description": "ID único del usuario cuyos detalles se solicitan."
          },
          "token": {
            "type": "string",
            "description": "Token de autenticación del usuario."
          }
        },
        "required": [
          "user_id",
          "token"
        ]
      },
      "GetUserDetailResponse": {
        "type": "object",
        "properties": {
          "success": {
            "type": "boolean",
            "description": "Indica si la operación fue exitosa."
          },
          "message": {
            "type": "string",
            "description": "Código o mensaje de respuesta."
          },
          "user_id": {
            "type": "string"
          },
          "first_name": {
            "type": "string"
          },
          "last_name": {
            "type": "string"
          },
          "country_phone_code": {
            "type": "string"
          },
          "phone": {
            "type": "string"
          },
          "email": {
            "type": "string",
            "format": "email"
          },
          "wallet": {
            "type": "number",
            "format": "float"
          },
          "wallet_currency_code": {
            "type": "string"
          },
          "picture": {
            "type": "string"
          },
          "bio": {
            "type": "string"
          },
          "address": {
            "type": "string"
          },
          "city": {
            "type": "string"
          },
          "country": {
            "type": "string"
          },
          "zipcode": {
            "type": "string"
          },
          "login_by": {
            "type": "string"
          },
          "gender": {
            "type": "string"
          },
          "social_unique_id": {
            "type": "string"
          },
          "social_ids": {
            "type": "array",
            "items": {
              "type": "string"
            }
          },
          "device_token": {
            "type": "string"
          },
          "device_type": {
            "type": "string",
            "enum": [
              "android",
              "ios"
            ]
          },
          "device_timezone": {
            "type": "string"
          },
          "referral_code": {
            "type": "string"
          },
          "token": {
            "type": "string"
          },
          "is_approved": {
            "type": "integer"
          },
          "app_version": {
            "type": "string"
          },
          "is_referral": {
            "type": "integer"
          },
          "is_document_uploaded": {
            "type": "integer"
          },
          "country_detail": {
            "type": "object",
            "properties": {
              "is_referral": {
                "type": "boolean"
              }
            }
          },
          "rate": {
            "type": "number",
            "format": "float"
          },
          "rate_count": {
            "type": "integer"
          }
        },
        "required": [
          "success",
          "message",
          "user_id"
        ]
      }
    }
  }
}

```

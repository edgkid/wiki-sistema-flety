### Actualizar Usuario

```json
{
  "openapi": "3.0.0",
  "info": {
    "title": "API de Actualización de Usuario",
    "version": "1.0.0",
    "description": "API para actualizar los detalles de un usuario."
  },
  "servers": [
    {
      "url": "https://{{URL}}",
      "description": "Servidor principal (reemplazar {{URL}})"
    }
  ],
  "paths": {
    "/userupdate": {
      "post": {
        "summary": "Actualizar detalles del usuario",
        "operationId": "userUpdate",
        "requestBody": {
          "required": true,
          "content": {
            "application/json": {
              "schema": {
                "$ref": "#/components/schemas/UserUpdateRequest"
              },
              "examples": {
                "UserUpdateExample": {
                  "value": {
                    "user_id": "{{USER_ID}}",
                    "token": "{{USER_TOKEN}}",
                    "email": "android@user.com",
                    "first_name": "Android",
                    "last_name": "User",
                    "new_password": "",
                    "old_password": "123456",
                    "country_phone_code": "+91",
                    "phone": "9904385946",
                    "bio": "Bio",
                    "address": "Rajkot",
                    "zipcode": "1234567"
                  }
                }
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "Actualización exitosa del usuario",
            "content": {
              "application/json": {
                "schema": {
                  "$ref": "#/components/schemas/UserUpdateResponse"
                },
                "examples": {
                  "SuccessfulResponse": {
                    "value": {
                      "success": true,
                      "message": "4",
                      "user_detail": {
                        "first_name": "Android",
                        "last_name": "User",
                        "country_phone_code": "+91",
                        "is_document_uploaded": 1,
                        "address": "Rajkot",
                        "is_approved": 1,
                        "user_id": "61962d683b0daa5338204ce6",
                        "social_ids": [],
                        "social_unique_id": "",
                        "login_by": "manual",
                        "country": "India",
                        "referral_code": "YUR85FNS",
                        "rate": 0,
                        "rate_count": 0,
                        "is_referral": 0,
                        "token": "AOoMZfZ8u7G2UzJlb8DOny8YeurUMMH7",
                        "country_detail": {
                          "is_referral": false
                        },
                        "phone": "9904385946",
                        "picture": "",
                        "wallet_currency_code": "INR"
                      }
                    }
                  }
                }
              }
            }
          },
          "400": {
            "description": "Solicitud Inválida o Error de Validación"
          },
          "401": {
            "description": "No Autorizado (Token Inválido)"
          }
        }
      }
    }
  },
  "components": {
    "schemas": {
      "UserUpdateRequest": {
        "type": "object",
        "properties": {
          "user_id": {
            "type": "string",
            "description": "ID único del usuario."
          },
          "token": {
            "type": "string",
            "description": "Token de autenticación del usuario."
          },
          "email": {
            "type": "string",
            "format": "email",
            "description": "Nuevo correo electrónico del usuario."
          },
          "first_name": {
            "type": "string",
            "description": "Nombre de pila del usuario."
          },
          "last_name": {
            "type": "string",
            "description": "Apellido del usuario."
          },
          "new_password": {
            "type": "string",
            "description": "Nueva contraseña (opcional)."
          },
          "old_password": {
            "type": "string",
            "description": "Contraseña actual (requerida si se cambia la contraseña)."
          },
          "country_phone_code": {
            "type": "string",
            "description": "Código de país para el teléfono (+XX)."
          },
          "phone": {
            "type": "string",
            "description": "Número de teléfono del usuario."
          },
          "bio": {
            "type": "string",
            "description": "Biografía/descripción del usuario."
          },
          "address": {
            "type": "string",
            "description": "Dirección física del usuario."
          },
          "zipcode": {
            "type": "string",
            "description": "Código postal."
          }
        },
        "required": [
          "user_id",
          "token",
          "email",
          "first_name",
          "last_name",
          "old_password"
        ]
      },
      "UserDetail": {
        "type": "object",
        "properties": {
          "first_name": {
            "type": "string"
          },
          "last_name": {
            "type": "string"
          },
          "country_phone_code": {
            "type": "string"
          },
          "is_document_uploaded": {
            "type": "integer"
          },
          "address": {
            "type": "string"
          },
          "is_approved": {
            "type": "integer"
          },
          "user_id": {
            "type": "string"
          },
          "social_ids": {
            "type": "array",
            "items": {
              "type": "string"
            }
          },
          "social_unique_id": {
            "type": "string"
          },
          "login_by": {
            "type": "string"
          },
          "country": {
            "type": "string"
          },
          "referral_code": {
            "type": "string"
          },
          "rate": {
            "type": "integer"
          },
          "rate_count": {
            "type": "integer"
          },
          "is_referral": {
            "type": "integer"
          },
          "token": {
            "type": "string"
          },
          "country_detail": {
            "type": "object",
            "properties": {
              "is_referral": {
                "type": "boolean"
              }
            }
          },
          "phone": {
            "type": "string"
          },
          "picture": {
            "type": "string"
          },
          "wallet_currency_code": {
            "type": "string"
          }
        }
      },
      "UserUpdateResponse": {
        "type": "object",
        "properties": {
          "success": {
            "type": "boolean",
            "description": "Indica si la operación fue exitosa."
          },
          "message": {
            "type": "string",
            "description": "Mensaje o código de respuesta."
          },
          "user_detail": {
            "$ref": "#/components/schemas/UserDetail",
            "description": "Detalles del usuario actualizado."
          }
        },
        "required": [
          "success",
          "message",
          "user_detail"
        ]
      }
    }
  }
}

```

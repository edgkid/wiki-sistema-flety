
### Verificar Usuario

```json
{
  "openapi": "3.0.0",
  "info": {
    "title": "User Registration Check API",
    "version": "1.0.0",
    "description": "Verifica si un número de teléfono está registrado en el sistema y, si la configuración lo permite, inicia el proceso de verificación de usuario por SMS."
  },
  "servers": [
    {
      "url": "{{URL}}",
      "description": "Servidor principal de la API"
    }
  ],
  "paths": {
    "/check_user_registered": {
      "post": {
        "summary": "Verificar registro de usuario y enviar OTP",
        "operationId": "checkUserRegistered",
        "tags": [
          "Authentication"
        ],
        "requestBody": {
          "required": true,
          "content": {
            "application/json": {
              "schema": {
                "type": "object",
                "properties": {
                  "phone": {
                    "type": "string",
                    "description": "Número de teléfono del usuario.",
                    "example": "9904385946"
                  },
                  "country_phone_code": {
                    "type": "string",
                    "description": "Código telefónico internacional del país (e.g., +91).",
                    "example": "+91"
                  }
                },
                "required": [
                  "phone",
                  "country_phone_code"
                ]
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "Verificación exitosa. Si 'userSms' es true, se envió un OTP.",
            "content": {
              "application/json": {
                "schema": {
                  "$ref": "#/components/schemas/CheckUserRegisteredResponse"
                },
                "example": {
                  "success": true,
                  "otpForSMS": "705946",
                  "userSms": true
                }
              }
            }
          },
          "400": {
            "description": "Datos de entrada inválidos (ej. formato de teléfono incorrecto).",
            "content": {
              "application/json": {
                "schema": {
                  "type": "object",
                  "properties": {
                    "success": { "type": "boolean", "example": false },
                    "error": { "type": "string", "example": "Invalid Phone Number" }
                  }
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
      "CheckUserRegisteredResponse": {
        "type": "object",
        "description": "Respuesta de verificación de registro de usuario.",
        "properties": {
          "success": {
            "type": "boolean",
            "description": "Indica si la operación fue exitosa."
          },
          "otpForSMS": {
            "type": "string",
            "description": "Código OTP enviado por SMS (puede ser devuelto en modo de prueba/desarrollo)."
          },
          "userSms": {
            "type": "boolean",
            "description": "Indica si la verificación por SMS está activa para el usuario/país, y si se ha enviado un código."
          }
        },
        "required": [
          "success",
          "userSms"
        ]
      }
    }
  }
}

```

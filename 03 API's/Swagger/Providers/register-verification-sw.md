### Validación de Registro

```json

{
  "openapi": "3.0.0",
  "info": {
    "title": "Verification API",
    "description": "API para validar la disponibilidad de credenciales (email/teléfono) generar códigos OTP para el proceso de registro.",
    "version": "1.0.0"
  },
  "paths": {
    "/verification": {
      "post": {
        "summary": "Verificar disponibilidad y generar OTP",
        "description": "Comprueba si el email o teléfono ya están registrados. Si están disponibles, envía códigos OTP vía SMS y Email.",
        "requestBody": {
          "required": true,
          "content": {
            "application/json": {
              "schema": {
                "$ref": "#/components/schemas/VerificationRequest"
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "Códigos OTP generados exitosamente",
            "content": {
              "application/json": {
                "schema": {
                  "$ref": "#/components/schemas/VerificationResponse"
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
      "VerificationRequest": {
        "type": "object",
        "required": [
          "email",
          "phone",
          "country_phone_code",
          "type"
        ],
        "properties": {
          "email": {
            "type": "string",
            "format": "email",
            "example": "new@driver.com"
          },
          "phone": {
            "type": "string",
            "example": "1234561230"
          },
          "country_phone_code": {
            "type": "string",
            "example": "+91"
          },
          "type": {
            "type": "integer",
            "description": "Tipo de usuario (ej. 0 para proveedores).",
            "example": 0
          }
        }
      },
      "VerificationResponse": {
        "type": "object",
        "properties": {
          "success": {
            "type": "boolean",
            "example": true
          },
          "otpForSMS": {
            "type": "string",
            "description": "Código de verificación enviado por mensaje de texto.",
            "example": "693140"
          },
          "otpForEmail": {
            "type": "string",
            "description": "Código de verificación enviado por correo electrónico.",
            "example": "227994"
          }
        }
      }
    }
  }
}

```

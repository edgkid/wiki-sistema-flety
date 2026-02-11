
### Verificación de Usuario

```json
{
  "openapi": "3.0.0",
  "info": {
    "title": "API -Verificación de Usuario",
    "version": "1.0.0",
    "description": "API para verificación de usuario, "
  },
  "paths": {
    "/user/requestverification": {
      "post": {
        "summary": "Solicitar OTP para registro/verificación",
        "requestBody": {
          "required": true,
          "content": {
            "application/json": {
              "schema": {
                "type": "object",
                "properties": {
                  "email": {
                    "type": "string",
                    "format": "email",
                    "description": "Correo electrónico del nuevo usuario."
                  },
                  "phone": {
                    "type": "string",
                    "description": "Número de teléfono del nuevo usuario."
                  },
                  "country_phone_code": {
                    "type": "string",
                    "description": "Código de país para el número de teléfono (Ej: +91)."
                  },
                  "type": {
                    "type": "integer",
                    "description": "Tipo de usuario o flujo (Ej: 1 para registro)."
                  }
                },
                "required": [
                  "email",
                  "phone",
                  "country_phone_code",
                  "type"
                ],
                "example": {
                  "email": "new@user.com",
                  "phone": "1234567891",
                  "country_phone_code": "+91",
                  "type": 1
                }
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "Códigos OTP generados y enviados exitosamente al teléfono y correo electrónico.",
            "content": {
              "application/json": {
                "schema": {
                  "type": "object",
                  "properties": {
                    "success": {
                      "type": "boolean",
                      "description": "Indica si la operación fue exitosa."
                    },
                    "otpForSMS": {
                      "type": "string",
                      "description": "Código OTP enviado por SMS (solo para pruebas, generalmente no se devuelve en producción)."
                    },
                    "otpForEmail": {
                      "type": "string",
                      "description": "Código OTP enviado por correo electrónico (solo para pruebas, generalmente no se devuelve en producción)."
                    }
                  },
                  "example": {
                    "success": true,
                    "otpForSMS": "154834",
                    "otpForEmail": "335708"
                  }
                }
              }
            }
          },
          "400": {
            "description": "Solicitud inválida (ej. formato de email incorrecto o número de teléfono no válido)."
          },
          "409": {
            "description": "Conflicto: El usuario (email o teléfono) ya existe."
          }
        }
      }
    }
  }
}

```
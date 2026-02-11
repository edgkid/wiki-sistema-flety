```json
{
  "openapi": "3.0.0",
  "info": {
    "title": "API - para obtener otp",
    "version": "1.0.0",
    "description": "Endpoint de obtención de código OTP."
  },
  "servers": [
    {
      "url": "{URL}",
      "description": "Servidor principal de la API. Reemplazar {URL} con la URL base real."
    }
  ],
  "paths": {
    "/get_otp": {
      "post": {
        "summary": "Solicita un código de verificación OTP por SMS.",
        "operationId": "getOtp",
        "requestBody": {
          "description": "Número de teléfono y código de país para el envío del OTP.",
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
                    "description": "Código internacional del país.",
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
            "description": "Respuesta exitosa, el OTP se ha generado y enviado (o está disponible en 'otpForSMS' para propósitos de prueba/desarrollo).",
            "content": {
              "application/json": {
                "schema": {
                  "$ref": "#/components/schemas/GetOtpSuccessResponse"
                },
                "example": {
                  "success": true,
                  "otpForSMS": "743849"
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
      "GetOtpSuccessResponse": {
        "type": "object",
        "properties": {
          "success": {
            "type": "boolean",
            "description": "Indica si la solicitud fue exitosa.",
            "example": true
          },
          "otpForSMS": {
            "type": "string",
            "description": "Código OTP generado. **Nota:** En un entorno de producción seguro, este campo generalmente no se incluiría en la respuesta, solo se enviaría por SMS.",
            "example": "743849"
          }
        },
        "required": [
          "success",
          "otpForSMS"
        ]
      }
    }
  }
}


```


### Uso de Pay Stack para Pagos

```json
{
  "openapi": "3.0.0",
  "info": {
    "title": "Paystack Verification API",
    "description": "API para enviar detalles adicionales requeridos por Paystack para procesar una transacción de pago.",
    "version": "1.0.0"
  },
  "servers": [
    {
      "url": "{{URL}}",
      "description": "Servidor de Pagos"
    }
  ],
  "paths": {
    "/send_paystack_required_detail": {
      "post": {
        "summary": "Enviar detalles requeridos para Paystack",
        "description": "Envía parámetros de validación adicionales (PIN, OTP, referencia) para completar el flujo de pago.",
        "operationId": "sendPaystackDetails",
        "requestBody": {
          "required": true,
          "content": {
            "application/json": {
              "schema": {
                "$ref": "#/components/schemas/PaystackRequiredDetailRequest"
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "Detalles procesados y saldo de billetera actualizado",
            "content": {
              "application/json": {
                "schema": {
                  "$ref": "#/components/schemas/PaystackRequiredDetailResponse"
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
      "PaystackRequiredDetailRequest": {
        "type": "object",
        "required": [
          "amount",
          "reference",
          "user_id",
          "token",
          "required_param"
        ],
        "properties": {
          "amount": {
            "type": "string",
            "description": "Monto de la transacción.",
            "example": "152"
          },
          "otp": {
            "type": "string",
            "description": "Código de un solo uso recibido por el usuario.",
            "example": "123456"
          },
          "reference": {
            "type": "string",
            "description": "Referencia única de la transacción de Paystack.",
            "example": "nb2jkipik7s5d7f"
          },
          "user_id": {
            "type": "string",
            "example": "{{USER_ID}}"
          },
          "payment_gateway_type": {
            "type": "string",
            "description": "Identificador de la pasarela (11 para Paystack).",
            "example": "11"
          },
          "token": {
            "type": "string",
            "example": "{{USER_TOKEN}}"
          },
          "pin": {
            "type": "string",
            "description": "Código PIN del usuario o de la tarjeta.",
            "example": "1234"
          },
          "type": {
            "type": "string",
            "description": "Número único de usuario o tipo de operación.",
            "example": "{{USER_UNIQUE_NUMBER}}"
          },
          "required_param": {
            "type": "string",
            "description": "Define qué tipo de parámetro se está enviando (ej. send_pin, send_otp).",
            "example": "send_pin"
          },
          "phone": {
            "type": "string",
            "description": "Número de teléfono opcional.",
            "example": ""
          }
        }
      },
      "PaystackRequiredDetailResponse": {
        "type": "object",
        "properties": {
          "success": {
            "type": "boolean",
            "example": true
          },
          "message": {
            "type": "string",
            "description": "Código de respuesta del sistema.",
            "example": "91"
          },
          "wallet": {
            "type": "number",
            "description": "Saldo actual en la billetera del usuario.",
            "example": 2675
          },
          "wallet_currency_code": {
            "type": "string",
            "description": "Código de moneda (ISO).",
            "example": "USD"
          }
        }
      }
    }
  }
}


```

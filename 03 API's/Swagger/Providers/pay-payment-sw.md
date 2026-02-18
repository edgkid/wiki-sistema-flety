
### Procesar Pago de Viaje

```json

{
  "openapi": "3.0.0",
  "info": {
    "title": "Payment Processing API",
    "description": "Endpoint encargado de procesar el pago final del viaje.",
    "version": "1.0.0"
  },
  "paths": {
    "/pay_payment": {
      "post": {
        "summary": "Procesar pago del viaje",
        "description": "Realiza el cobro final al usuario.",
        "requestBody": {
          "required": true,
          "content": {
            "application/json": {
              "schema": {
                "$ref": "#/components/schemas/PayPaymentRequest"
              }
            },
            "multipart/form-data": {
              "schema": {
                "$ref": "#/components/schemas/PayPaymentRequest"
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "Operación de pago procesada correctamente",
            "content": {
              "application/json": {
                "schema": {
                  "$ref": "#/components/schemas/PayPaymentResponse"
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
      "PayPaymentRequest": {
        "type": "object",
        "required": [
          "provider_id",
          "token",
          "trip_id"
        ],
        "properties": {
          "provider_id": {
            "type": "string",
            "description": "ID del proveedor que solicita el cobro.",
            "example": "{{PROVIDER_ID}}"
          },
          "token": {
            "type": "string",
            "description": "Token de autenticación del proveedor.",
            "example": "{{PROVIDER_TOKEN}}"
          },
          "trip_id": {
            "type": "string",
            "description": "ID único del viaje a pagar.",
            "example": "{{TRIP_ID}}"
          },
          "tip_amount": {
            "type": "number",
            "description": "Monto de la propina opcional.",
            "example": 0,
            "default": 0
          }
        }
      },
      "PayPaymentResponse": {
        "type": "object",
        "properties": {
          "success": {
            "type": "boolean",
            "example": true
          },
          "message": {
            "type": "string",
            "description": "Código de mensaje de éxito.",
            "example": "28"
          },
          "payment_status": {
            "type": "integer",
            "description": "Estado de la transacción (1: Exitoso, otros: Pendiente/Fallido).",
            "example": 1
          }
        }
      }
    }
  }
}
```
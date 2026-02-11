### Iniciar Procesamiento de Pagos

```json
{
  "openapi": "3.0.0",
  "info": {
    "title": "Tip Payment API",
    "description": "API para el procesamiento de pagos.",
    "version": "1.0.0"
  },
  "servers": [
    {
      "url": "{{URL}}",
      "description": "Servidor base"
    }
  ],
  "paths": {
    "/pay_tip_payment": {
      "post": {
        "summary": "Procesar pago de propina",
        "description": "Este API se utiliza para realizar el pago de la propina de un viaje específico.",
        "operationId": "payTipPayment",
        "requestBody": {
          "required": true,
          "content": {
            "application/json": {
              "schema": {
                "$ref": "#/components/schemas/TipPaymentRequest"
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "Operación procesada con éxito",
            "content": {
              "application/json": {
                "schema": {
                  "oneOf": [
                    { "$ref": "#/components/schemas/SuccessResponse" },
                    { "$ref": "#/components/schemas/ErrorResponse" }
                  ]
                },
                "examples": {
                  "SuccessResponse": {
                    "summary": "Pago Exitoso",
                    "value": {
                      "success": true
                    }
                  },
                  "NoTripFound": {
                    "summary": "Viaje no encontrado",
                    "value": {
                      "success": false,
                      "error_code": "437"
                    }
                  },
                  "PaymentPending": {
                    "summary": "Pago pendiente",
                    "value": {
                      "success": false,
                      "error_code": "464"
                    }
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
      "TipPaymentRequest": {
        "type": "object",
        "required": [
          "user_id",
          "token",
          "trip_id"
        ],
        "properties": {
          "user_id": {
            "type": "string",
            "description": "Id del usuario.",
            "example": "{{USER_ID}}"
          },
          "token": {
            "type": "string",
            "description": "Token único del usuario.",
            "example": "{{USER_TOKEN}}"
          },
          "trip_id": {
            "type": "string",
            "description": "Id del viaje.",
            "example": "{{TRIP_ID}}"
          }
        }
      },
      "SuccessResponse": {
        "type": "object",
        "properties": {
          "success": {
            "type": "boolean",
            "example": true
          }
        }
      },
      "ErrorResponse": {
        "type": "object",
        "properties": {
          "success": {
            "type": "boolean",
            "example": false
          },
          "error_code": {
            "type": "string",
            "description": "Código de error de negocio.",
            "example": "437"
          }
        }
      }
    }
  }
}
```

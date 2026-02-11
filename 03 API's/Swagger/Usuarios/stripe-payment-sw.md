### Método de Pago Stripe

```json
{
  "openapi": "3.0.0",
  "info": {
    "title": "Stripe Payment Intent API",
    "description": "API para procesar pagos utilizando la pasarela de Stripe.",
    "version": "1.0.0"
  },
  "servers": [
    {
      "url": "{{URL}}",
      "description": "Servidor principal"
    }
  ],
  "paths": {
    "/pay_stripe_intent_payment": {
      "post": {
        "summary": "Procesar pago con Stripe",
        "description": "Confirma y procesa la intención de pago asociada a un viaje específico.",
        "operationId": "payStripeIntent",
        "requestBody": {
          "required": true,
          "content": {
            "application/json": {
              "schema": {
                "$ref": "#/components/schemas/StripePaymentRequest"
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "Pago procesado exitosamente",
            "content": {
              "application/json": {
                "schema": {
                  "$ref": "#/components/schemas/StripePaymentResponse"
                }
              }
            }
          },
          "402": {
            "description": "Error en el pago (Pago requerido o rechazado)"
          },
          "404": {
            "description": "No se encontró el trip_id proporcionado"
          }
        }
      }
    }
  },
  "components": {
    "schemas": {
      "StripePaymentRequest": {
        "type": "object",
        "required": [
          "trip_id"
        ],
        "properties": {
          "trip_id": {
            "type": "string",
            "description": "ID del viaje para el cual se desea ejecutar el pago.",
            "example": "619f99ecc68548396ff542a4"
          }
        }
      },
      "StripePaymentResponse": {
        "type": "object",
        "properties": {
          "success": {
            "type": "boolean",
            "example": true
          }
        }
      }
    }
  }
}

```

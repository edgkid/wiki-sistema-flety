### Obtener Intent de Pago de Proveedor

```json
{
  "openapi": "3.0.0",
  "info": {
    "title": "Stripe Payment API",
    "description": "Endpoint para generar un Payment Intent de Stripe para proveedores.",
    "version": "1.0.0"
  },
  "servers": [
    {
      "url": "{{URL}}",
      "description": "Servidor de Pagos"
    }
  ],
  "paths": {
    "/get_stripe_payment_intent": {
      "post": {
        "summary": "Obtener Intent de Pago de Stripe",
        "operationId": "getStripePaymentIntent",
        "requestBody": {
          "required": true,
          "content": {
            "application/json": {
              "schema": {
                "$ref": "#/components/schemas/PaymentIntentRequest"
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "Intent creado exitosamente",
            "content": {
              "application/json": {
                "schema": {
                  "$ref": "#/components/schemas/PaymentIntentResponse"
                },
                "example": {
                  "success": true,
                  "message": "Payment intent created successfully",
                  "client_secret": "pi_3Jv..._secret_...",
                  "payment_intent_id": "pi_3Jv..."
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
      "PaymentIntentRequest": {
        "type": "object",
        "properties": {
          "type": { "type": "integer", "example": 11 },
          "payment_gateway_type": { "type": "integer", "example": 12 },
          "token": { "type": "string", "example": "{{PROVIDER_TOKEN}}" },
          "user_id": { "type": "string", "example": "{{PROVIDER_ID}}" },
          "amount": { "type": "integer", "example": 255 }
        },
        "required": ["type", "payment_gateway_type", "token", "user_id", "amount"]
      },
      "PaymentIntentResponse": {
        "type": "object",
        "properties": {
          "success": { "type": "boolean" },
          "message": { "type": "string" },
          "client_secret": { "type": "string" },
          "payment_intent_id": { "type": "string" }
        }
      }
    }
  }
}
```
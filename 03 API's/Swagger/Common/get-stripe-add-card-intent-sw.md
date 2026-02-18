### Generar Acción de Registro de Método de Pago

```json
{
  "openapi": "3.0.0",
  "info": {
    "title": "Payment Intent API",
    "description": "Endpoint para generar  registro de tarjetas de crédito/débito a través de pasarelas de pago (Stripe/Paystack).",
    "version": "1.0.0"
  },
  "paths": {
    "/get_stripe_add_card_intent": {
      "post": {
        "summary": "Crear uin intemt de añadir tarjeta",
        "description": "Inicia el proceso de vinculación de un método de pago.b.",
        "requestBody": {
          "required": true,
          "content": {
            "multipart/form-data": {
              "schema": {
                "$ref": "#/components/schemas/AddCardIntentRequest"
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "Intención creada exitosamente",
            "content": {
              "application/json": {
                "schema": {
                  "oneOf": [
                    { "$ref": "#/components/schemas/PaystackResponse" },
                    { "$ref": "#/components/schemas/StripeResponse" }
                  ]
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
      "AddCardIntentRequest": {
        "type": "object",
        "required": [
          "payment_gateway_type",
          "user_id"
        ],
        "properties": {
          "payment_gateway_type": {
            "type": "string",
            "description": "10 para Stripe, 11 para Paystack, 12 para PayU.",
            "enum": ["10", "11", "12"],
            "example": "11"
          },
          "user_id": {
            "type": "string",
            "description": "ID del usuario o proveedor que añade la tarjeta.",
            "example": "{{USER_ID}}"
          },
          "type": {
            "type": "string",
            "description": "Identificador de tipo de entidad.",
            "example": "11"
          }
        }
      },
      "PaystackResponse": {
        "type": "object",
        "properties": {
          "success": { "type": "boolean", "example": true },
          "authorization_url": { 
            "type": "string", 
            "example": "https://checkout.paystack.com/ug3u0luez856xyc" 
          },
          "access_code": { "type": "string", "example": "ug3u0luez856xyc" }
        }
      },
      "StripeResponse": {
        "type": "object",
        "properties": {
          "success": { "type": "boolean", "example": true },
          "client_secret": { 
            "type": "string", 
            "example": "seti_1JyazoGuEroovfwJuwv3QUIA_secret_KdslFSR" 
          }
        }
      }
    }
  }
}

```

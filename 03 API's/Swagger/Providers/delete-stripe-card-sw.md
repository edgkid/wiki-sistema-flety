### Eliminar Tarjeta Stripe

```json
{
  "openapi": "3.0.0",
  "info": {
    "title": "Card Management API",
    "description": "API que permitw la eliminación segura de tarjetas (Stripe) comno método de pago registradas.",
    "version": "1.0.0"
  },
  "paths": {
    "/delete_card": {
      "post": {
        "summary": "Eliminar tarjeta registrada",
        "description": "Elimina permanentemente una tarjeta.",
        "requestBody": {
          "required": true,
          "content": {
            "application/json": {
              "schema": {
                "$ref": "#/components/schemas/DeleteCardRequest"
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "Tarjeta eliminada exitosamente",
            "content": {
              "application/json": {
                "schema": {
                  "$ref": "#/components/schemas/DeleteCardResponse"
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
      "DeleteCardRequest": {
        "type": "object",
        "required": [
          "user_id",
          "token",
          "type",
          "card_id",
          "payment_gateway_type"
        ],
        "properties": {
          "user_id": {
            "type": "string",
            "example": "{{PROVIDER_ID}}"
          },
          "token": {
            "type": "string",
            "example": "{{PROVIDER_TOKEN}}"
          },
          "type": {
            "type": "string",
            "example": "{{PROVIDER_UNIQUE_NUMBER}}"
          },
          "card_id": {
            "type": "string",
            "description": "ID único de la tarjeta a eliminar.",
            "example": "619b9e9b0fb87b2eb1603faf"
          },
          "payment_gateway_type": {
            "type": "string",
            "example": "{{PAYMENT_GATEWAY_STRIPE}}"
          }
        }
      },
      "DeleteCardResponse": {
        "type": "object",
        "properties": {
          "success": {
            "type": "boolean",
            "example": true
          },
          "message": {
            "type": "string",
            "description": "Código de respuesta del servidor tras la eliminación.",
            "example": "8"
          }
        }
      }
    }
  }
}
```

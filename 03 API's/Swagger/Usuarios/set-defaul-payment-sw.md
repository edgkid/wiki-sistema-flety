### Método de Pago por Default

```json
{
  "openapi": "3.0.0",
  "info": {
    "title": "API - esteble un metodo de pago como predeterminado",
    "version": "1.0.0",
    "description": "Establece un método de como método de pago predeterminado."
  },
  "servers": [
    {
      "url": "{{URL}}",
      "description": "Servidor principal de la API"
    }
  ],
  "paths": {
    "/card_selection": {
      "post": {
        "summary": "Seleccionar y establecer un método de pago como predeterminado",
        "operationId": "selectDefaultCard",
        "tags": [
          "Payments"
        ],
        "requestBody": {
          "required": true,
          "content": {
            "application/json": {
              "schema": {
                "$ref": "#/components/schemas/CardSelectionRequest"
              },
              "example": {
                "user_id": "{{USER_ID}}",
                "token": "{{USER_TOKEN}}",
                "type": "{{USER_UNIQUE_NUMBER}}",
                "card_id": "619b8977f6eb2a0735a31047",
                "payment_gateway_type": "{{PAYMENT_GATEWAY_STRIPE}}"
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "Tarjeta seleccionada y establecida como predeterminada exitosamente. Devuelve los detalles de la tarjeta.",
            "content": {
              "application/json": {
                "schema": {
                  "$ref": "#/components/schemas/CardSelectionResponse"
                },
                "example": {
                  "success": true,
                  "card": {
                    "_id": "619b7f53b8dc6178b3d4b306",
                    "user_id": "61978529e3a07451a82404a5",
                    "type": 10,
                    "__v": 0,
                    "updated_at": "2021-11-22T11:30:27.892Z",
                    "created_at": "2021-11-22T11:30:27.892Z",
                    "payment_gateway_type": 10,
                    "is_default": 1,
                    "customer_id": "",
                    "last_four": "4242",
                    "card_type": "visa",
                    "payment_method": "pm_1Jyaj7GuEroovfwJe0BzCQa8"
                  }
                }
              }
            }
          },
          "400": {
            "description": "Error al procesar la solicitud o tarjeta no encontrada.",
            "content": {
              "application/json": {
                "schema": {
                  "type": "object",
                  "properties": {
                    "success": { "type": "boolean", "example": false },
                    "error_code": { "type": "string", "example": "442" },
                    "message": { "type": "string", "example": "Card Not Found" }
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
      "CardSelectionRequest": {
        "type": "object",
        "description": "Parámetros necesarios para seleccionar una tarjeta.",
        "properties": {
          "user_id": {
            "type": "string",
            "description": "ID del usuario."
          },
          "token": {
            "type": "string",
            "description": "Token de autenticación del usuario."
          },
          "type": {
            "type": "string",
            "description": "Número o código único del usuario/sesión."
          },
          "card_id": {
            "type": "string",
            "description": "El ID único de la tarjeta que se desea establecer como predeterminada.",
            "example": "619b8977f6eb2a0735a31047"
          },
          "payment_gateway_type": {
            "type": "string",
            "description": "Tipo o código de la pasarela de pago (e.g., Stripe)."
          }
        },
        "required": [
          "user_id",
          "token",
          "type",
          "card_id",
          "payment_gateway_type"
        ]
      },
      "CardSelectionResponse": {
        "type": "object",
        "description": "Respuesta tras la selección exitosa de una tarjeta.",
        "properties": {
          "success": {
            "type": "boolean"
          },
          "card": {
            "$ref": "#/components/schemas/CardDetail"
          }
        },
        "required": [
          "success",
          "card"
        ]
      },
      "CardDetail": {
        "type": "object",
        "description": "Detalles de la tarjeta.",
        "properties": {
          "_id": {
            "type": "string"
          },
          "user_id": {
            "type": "string"
          },
          "type": {
            "type": "integer"
          },
          "__v": {
            "type": "integer"
          },
          "updated_at": {
            "type": "string",
            "format": "date-time"
          },
          "created_at": {
            "type": "string",
            "format": "date-time"
          },
          "payment_gateway_type": {
            "type": "integer"
          },
          "is_default": {
            "type": "integer",
            "description": "Debería ser 1 si la selección fue exitosa."
          },
          "customer_id": {
            "type": "string"
          },
          "last_four": {
            "type": "string"
          },
          "card_type": {
            "type": "string"
          },
          "payment_method": {
            "type": "string"
          }
        }
      }
    }
  }
}

```

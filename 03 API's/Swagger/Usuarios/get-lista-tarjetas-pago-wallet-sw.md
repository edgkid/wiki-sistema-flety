### Listar Tarjetas O Métodos de Pago

```json
{
  "openapi": "3.0.0",
  "info": {
    "title": "api para listar tajetas de pago",
    "version": "1.0.0",
    "description": "Obtiene la lista de tarjetas de pago del usuario y la información de su billetera"
  },
  "servers": [
    {
      "url": "{{URL}}",
      "description": "Servidor principal de la API"
    }
  ],
  "paths": {
    "/cards": {
      "post": {
        "summary": "Obtener tarjetas de pago y detalles de la billetera",
        "operationId": "getCardsAndWalletDetails",
        "tags": [
          "Payments"
        ],
        "requestBody": {
          "required": true,
          "content": {
            "application/json": {
              "schema": {
                "$ref": "#/components/schemas/CardListRequest"
              },
              "example": {
                "user_id": "{{USER_ID}}",
                "token": "{{USER_TOKEN}}",
                "type": "{{USER_UNIQUE_NUMBER}}"
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "Lista de tarjetas y detalles de la billetera obtenidos exitosamente.",
            "content": {
              "application/json": {
                "schema": {
                  "$ref": "#/components/schemas/CardListResponse"
                },
                "example": {
                  "success": true,
                  "message": "7",
                  "wallet": 100,
                  "wallet_currency_code": "INR",
                  "is_use_wallet": 1,
                  "payment_gateway": [
                    {
                      "id": 10,
                      "name": "",
                      "is_add_card": true
                    }
                  ],
                  "payment_gateway_type": 10,
                  "card": [
                    {
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
      "CardListRequest": {
        "type": "object",
        "description": "Parámetros para solicitar la lista de tarjetas y la información de la billetera.",
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
            "description": "Un número único o identificador relacionado con la solicitud."
          }
        },
        "required": [
          "user_id",
          "token",
          "type"
        ]
      },
      "CardDetail": {
        "type": "object",
        "description": "Detalles de una tarjeta de pago guardada.",
        "properties": {
          "_id": {
            "type": "string",
            "description": "ID del documento de la tarjeta en la base de datos."
          },
          "user_id": {
            "type": "string",
            "description": "ID del usuario asociado a la tarjeta."
          },
          "type": {
            "type": "integer",
            "description": "Tipo o código interno."
          },
          "last_four": {
            "type": "string",
            "description": "Los últimos cuatro dígitos de la tarjeta.",
            "example": "4242"
          },
          "card_type": {
            "type": "string",
            "description": "Tipo de tarjeta (e.g., visa, mastercard).",
            "example": "visa"
          },
          "is_default": {
            "type": "integer",
            "description": "Indica si es la tarjeta por defecto (1) o no (0)."
          },
          "payment_method": {
            "type": "string",
            "description": "Token o ID del método de pago en la pasarela."
          }
        }
      },
      "PaymentGatewayDetail": {
        "type": "object",
        "description": "Detalles de una pasarela de pago disponible.",
        "properties": {
          "id": {
            "type": "integer"
          },
          "name": {
            "type": "string",
            "description": "Nombre de la pasarela de pago."
          },
          "is_add_card": {
            "type": "boolean",
            "description": "Indica si se pueden añadir tarjetas a través de esta pasarela."
          }
        }
      },
      "CardListResponse": {
        "type": "object",
        "properties": {
          "success": {
            "type": "boolean"
          },
          "message": {
            "type": "string",
            "description": "Código o mensaje interno de estado."
          },
          "wallet": {
            "type": "number",
            "description": "Saldo actual de la billetera del usuario."
          },
          "wallet_currency_code": {
            "type": "string",
            "description": "Código de moneda de la billetera (e.g., INR)."
          },
          "is_use_wallet": {
            "type": "integer",
            "description": "Indica si la billetera está activa o se puede usar (1)."
          },
          "payment_gateway": {
            "type": "array",
            "description": "Lista de pasarelas de pago disponibles.",
            "items": {
              "$ref": "#/components/schemas/PaymentGatewayDetail"
            }
          },
          "payment_gateway_type": {
            "type": "integer",
            "description": "Tipo de pasarela de pago preferida o predeterminada."
          },
          "card": {
            "type": "array",
            "description": "Lista de tarjetas de pago guardadas.",
            "items": {
              "$ref": "#/components/schemas/CardDetail"
            }
          }
        },
        "required": [
          "success",
          "wallet",
          "wallet_currency_code",
          "is_use_wallet",
          "card"
        ]
      }
    }
  }
}

```

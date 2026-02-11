### Movimientos (Historial) de Wallet
```json
{
  "openapi": "3.0.0",
  "info": {
    "title": "Wallet History API",
    "version": "1.0.0",
    "description": "API para obtener el historial de la billetera de un usuario específico."
  },
  "servers": [
    {
      "url": "{{URL}}",
      "description": "Servidor principal de la API"
    }
  ],
  "paths": {
    "/get_wallet_history": {
      "post": {
        "summary": "Obtener el historial de transacciones de la billetera",
        "operationId": "getWalletHistory",
        "tags": [
          "Wallet"
        ],
        "requestBody": {
          "required": true,
          "content": {
            "application/json": {
              "schema": {
                "type": "object",
                "properties": {
                  "user_id": {
                    "type": "string",
                    "description": "ID único del usuario.",
                    "example": "{{USER_ID}}"
                  },
                  "token": {
                    "type": "string",
                    "description": "Token de autenticación de la sesión del usuario.",
                    "example": "{{USER_TOKEN}}"
                  },
                  "type": {
                    "type": "string",
                    "description": "Número único asociado al tipo de usuario o entidad.",
                    "example": "{{USER_UNIQUE_NUMBER}}"
                  }
                },
                "required": [
                  "user_id",
                  "token",
                  "type"
                ]
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "Historial de la billetera obtenido exitosamente.",
            "content": {
              "application/json": {
                "schema": {
                  "$ref": "#/components/schemas/WalletHistoryResponse"
                },
                "example": {
                  "success": true,
                  "message": "100",
                  "wallet_history": [
                    {
                      "_id": "619662eb7bd38137e5e50f7a",
                      "unique_id": 155,
                      "user_type": 10,
                      "user_unique_id": 34,
                      "user_id": "61962d683b0daa5338204ce6",
                      "updated_at": "2021-11-18T14:27:55.616Z",
                      "created_at": "2021-11-18T14:27:55.616Z",
                      "total_wallet_amount": 300,
                      "added_wallet": 100,
                      "wallet_amount": 200,
                      "wallet_description": "Card : 4242",
                      "wallet_comment_id": 2,
                      "wallet_status": 1,
                      "current_rate": 1,
                      "to_currency_code": "INR",
                      "from_currency_code": "INR",
                      "from_amount": 100
                    }
                  ]
                }
              }
            }
          },
          "400": {
            "description": "Solicitud Inválida (ej. token inválido o parámetros faltantes)",
            "content": {
              "application/json": {
                "schema": {
                  "type": "object",
                  "properties": {
                    "success": { "type": "boolean" },
                    "error_code": { "type": "string" }
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
      "WalletHistoryResponse": {
        "type": "object",
        "properties": {
          "success": {
            "type": "boolean",
            "description": "Indica si la operación fue exitosa."
          },
          "message": {
            "type": "string",
            "description": "Código de mensaje interno o estado."
          },
          "wallet_history": {
            "type": "array",
            "description": "Lista de transacciones en la billetera.",
            "items": {
              "$ref": "#/components/schemas/WalletTransaction"
            }
          }
        },
        "required": [
          "success",
          "wallet_history"
        ]
      },
      "WalletTransaction": {
        "type": "object",
        "properties": {
          "_id": {
            "type": "string",
            "description": "ID interno de la transacción."
          },
          "unique_id": {
            "type": "integer",
            "description": "ID numérico único de la transacción."
          },
          "user_type": {
            "type": "integer",
            "description": "Tipo de usuario (e.g., 10)."
          },
          "user_unique_id": {
            "type": "integer",
            "description": "ID numérico único del usuario."
          },
          "user_id": {
            "type": "string",
            "description": "ID del usuario."
          },
          "updated_at": {
            "type": "string",
            "format": "date-time",
            "description": "Fecha y hora de la última actualización."
          },
          "created_at": {
            "type": "string",
            "format": "date-time",
            "description": "Fecha y hora de creación."
          },
          "total_wallet_amount": {
            "type": "number",
            "format": "float",
            "description": "Monto total después de la transacción."
          },
          "added_wallet": {
            "type": "number",
            "format": "float",
            "description": "Monto añadido o restado en la transacción."
          },
          "wallet_amount": {
            "type": "number",
            "format": "float",
            "description": "Balance anterior de la billetera."
          },
          "wallet_description": {
            "type": "string",
            "description": "Descripción de la transacción (e.g., método de pago)."
          },
          "wallet_comment_id": {
            "type": "integer",
            "description": "ID del comentario asociado a la transacción."
          },
          "wallet_status": {
            "type": "integer",
            "description": "Estado de la transacción (e.g., 1 para éxito)."
          },
          "current_rate": {
            "type": "number",
            "format": "float",
            "description": "Tasa de cambio actual (si aplica)."
          },
          "to_currency_code": {
            "type": "string",
            "description": "Código de la moneda de destino (e.g., INR)."
          },
          "from_currency_code": {
            "type": "string",
            "description": "Código de la moneda de origen (e.g., INR)."
          },
          "from_amount": {
            "type": "number",
            "format": "float",
            "description": "Monto de origen."
          }
        }
      }
    }
  }
}

```

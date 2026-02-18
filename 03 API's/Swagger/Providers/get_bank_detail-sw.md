### Consultar Detalle Banco

```json
{
  "openapi": "3.0.0",
  "info": {
    "title": "Banking Details API",
    "description": "API para la recuperación de información bancaria configurada por el proveedor.",
    "version": "1.0.0"
  },
  "paths": {
    "/get_bank_detail": {
      "post": {
        "summary": "Obtener detalles bancarios",
        "description": "Retorna la información de la cuenta bancaria vinculada al proveedor, incluyendo el ID de cuenta de la pasarela de pagos.",
        "requestBody": {
          "required": true,
          "content": {
            "application/json": {
              "schema": {
                "$ref": "#/components/schemas/GetBankDetailRequest"
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "Detalles bancarios recuperados con éxito",
            "content": {
              "application/json": {
                "schema": {
                  "$ref": "#/components/schemas/GetBankDetailResponse"
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
      "GetBankDetailRequest": {
        "type": "object",
        "required": [
          "provider_id",
          "token"
        ],
        "properties": {
          "provider_id": {
            "type": "string",
            "example": "{{PROVIDER_ID}}"
          },
          "token": {
            "type": "string",
            "example": "{{PROVIDER_TOKEN}}"
          }
        }
      },
      "GetBankDetailResponse": {
        "type": "object",
        "properties": {
          "success": {
            "type": "boolean",
            "example": true
          },
          "message": {
            "type": "string",
            "description": "Código de respuesta interna.",
            "example": "76"
          },
          "payment_gateway_type": {
            "type": "integer",
            "example": 10
          },
          "bankdetails": {
            "type": "object",
            "properties": {
              "account_number": {
                "type": "integer",
                "example": 6789
              },
              "routing_number": {
                "type": "integer",
                "example": 0
              },
              "account_holder_name": {
                "type": "string",
                "example": "Test"
              },
              "account_holder_type": {
                "type": "string",
                "example": "individual"
              },
              "account_id": {
                "type": "string",
                "example": "123456"
              }
            }
          }
        }
      }
    }
  }
}
```

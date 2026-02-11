### Credito y Referencia de Usuario

```json
{
  "openapi": "3.0.0",
  "info": {
    "title": "API - consulta credito total de usuario",
    "version": "1.0.0",
    "description": "Especificación para obtener el crédito total de referencia de un usuario."
  },
  "servers": [
    {
      "url": "{{URL}}",
      "description": "URL base del servicio"
    }
  ],
  "paths": {
    "/get_user_referal_credit": {
      "post": {
        "summary": "Obtener crédito de referencia",
        "description": "Consulta el crédito total acumulado por el usuario a través de referencias.",
        "operationId": "getUserReferralCredit",
        "tags": [
          "Créditos"
        ],
        "requestBody": {
          "required": true,
          "content": {
            "application/json": {
              "schema": {
                "$ref": "#/components/schemas/GetCreditRequest"
              },
              "example": {
                "user_id": "987abc123def456ghi789jkl0mn",
                "token": "a1b2c3d4e5f6g7h8i9j0k1l2m3n4o5p6"
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "Crédito de referencia obtenido exitosamente.",
            "content": {
              "application/json": {
                "schema": {
                  "$ref": "#/components/schemas/CreditResponse"
                },
                "example": {
                  "success": true,
                  "total_referral_credit": 0
                }
              }
            }
          },
          "401": {
            "description": "Token de autenticación inválido."
          }
        }
      }
    }
  },
  "components": {
    "schemas": {
      "GetCreditRequest": {
        "type": "object",
        "properties": {
          "user_id": {
            "type": "string",
            "description": "ID único del usuario.",
            "example": "{{USER_ID}}"
          },
          "token": {
            "type": "string",
            "description": "Token de sesión o autenticación del usuario.",
            "example": "{{USER_TOKEN}}"
          }
        },
        "required": [
          "user_id",
          "token"
        ]
      },
      "CreditResponse": {
        "type": "object",
        "properties": {
          "success": {
            "type": "boolean",
            "description": "Indica si la operación fue exitosa.",
            "example": true
          },
          "total_referral_credit": {
            "type": "integer",
            "format": "int32",
            "description": "Cantidad total de crédito de referencia acumulado.",
            "example": 0
          }
        },
        "required": [
          "success",
          "total_referral_credit"
        ]
      }
    }
  }
}


```

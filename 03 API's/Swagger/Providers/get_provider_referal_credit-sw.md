### Código de Referidos y Beneficios - Proveedor

```json
{
  "openapi": "3.0.0",
  "info": {
    "title": "Provider Rewards API",
    "description": "API para la gestión de incentivos, créditos y recompensas acumuladas por el programa de referidos del proveedor.",
    "version": "1.0.0"
  },
  "paths": {
    "/get_provider_referal_credit": {
      "post": {
        "summary": "Consultar créditos por referidos",
        "description": "Obtiene el monto total acumulado de créditos que el proveedor ha ganado al referir a otros usuarios.",
        "requestBody": {
          "required": true,
          "content": {
            "application/json": {
              "schema": {
                "$ref": "#/components/schemas/ReferralCreditRequest"
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "Consulta exitosa del balance de créditos",
            "content": {
              "application/json": {
                "schema": {
                  "$ref": "#/components/schemas/ReferralCreditResponse"
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
      "ReferralCreditRequest": {
        "type": "object",
        "required": [
          "provider_id",
          "token"
        ],
        "properties": {
          "provider_id": {
            "type": "string",
            "description": "Identificador único del proveedor en el sistema.",
            "example": "{{PROVIDER_ID}}"
          },
          "token": {
            "type": "string",
            "description": "Token de autenticación de la sesión activa.",
            "example": "{{PROVIDER_TOKEN}}"
          }
        }
      },
      "ReferralCreditResponse": {
        "type": "object",
        "properties": {
          "success": {
            "type": "boolean",
            "description": "Indica si la operación fue exitosa.",
            "example": true
          },
          "total_referral_credit": {
            "type": "number",
            "description": "Monto total acumulado de créditos por referidos.",
            "example": 15
          }
        }
      }
    }
  }
}
```

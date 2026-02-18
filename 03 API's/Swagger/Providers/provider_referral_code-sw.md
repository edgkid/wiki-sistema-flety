### Aplicar Código de Referido (Proveedor)

```json
{
  "openapi": "3.0.0",
  "info": {
    "title": "Referral System API",
    "description": "API para gestionar la aplicación de códigos de referido y beneficios por invitaciones entre proveedores.",
    "version": "1.0.0"
  },
  "paths": {
    "/apply_provider_referral_code": {
      "post": {
        "summary": "Aplicar código de referido",
        "description": "Permite a un nuevo proveedor aplicar el código de referido.",
        "requestBody": {
          "required": true,
          "content": {
            "application/json": {
              "schema": {
                "$ref": "#/components/schemas/ReferralRequest"
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "Operación realizada con éxito",
            "content": {
              "application/json": {
                "schema": {
                  "$ref": "#/components/schemas/ReferralResponse"
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
      "ReferralRequest": {
        "type": "object",
        "required": [
          "provider_id",
          "token",
          "is_skip"
        ],
        "properties": {
          "provider_id": {
            "type": "string",
            "example": "619ba7a6980b154c5d45f9b5"
          },
          "token": {
            "type": "string",
            "example": "4t1iFlj80nStmk80CW6mdP7UWL2ClG84"
          },
          "referral_code": {
            "type": "string",
            "description": "El código alfanumérico de referido.",
            "example": "M44W0YRU"
          },
          "is_skip": {
            "type": "integer",
            "description": "Define si se aplica el código (0) o si se omite el paso (1).",
            "enum": [0, 1],
            "example": 0
          }
        }
      },
      "ReferralResponse": {
        "type": "object",
        "properties": {
          "success": {
            "type": "boolean",
            "example": true
          },
          "message": {
            "type": "string",
            "description": "Código de éxito (12 para aplicado, 13 para omitido).",
            "example": "12"
          }
        }
      }
    }
  }
}
```

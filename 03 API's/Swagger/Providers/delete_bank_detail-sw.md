### Eliminar Detalle Banco

```json
{
  "openapi": "3.0.0",
  "info": {
    "title": "Banking Management API",
    "description": "API para la gestión y eliminación de métodos de pago y cuentas bancarias asociadas al proveedor.",
    "version": "1.0.0"
  },
  "paths": {
    "/delete_bank_detail": {
      "post": {
        "summary": "Eliminar detalles bancarios",
        "description": "Elimina de forma permanente la configuración bancaria y la vinculación con la pasarela de pagos para el proveedor especificado.",
        "requestBody": {
          "required": true,
          "content": {
            "application/json": {
              "schema": {
                "$ref": "#/components/schemas/DeleteBankDetailRequest"
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "Cuenta bancaria eliminada con éxito",
            "content": {
              "application/json": {
                "schema": {
                  "$ref": "#/components/schemas/GenericSuccessResponse"
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
      "DeleteBankDetailRequest": {
        "type": "object",
        "required": [
          "provider_id",
          "token"
        ],
        "properties": {
          "provider_id": {
            "type": "string",
            "description": "ID único del proveedor.",
            "example": "{{PROVIDER_ID}}"
          },
          "token": {
            "type": "string",
            "description": "Token de autenticación de la sesión activa.",
            "example": "{{PROVIDER_TOKEN}}"
          }
        }
      },
      "GenericSuccessResponse": {
        "type": "object",
        "properties": {
          "success": {
            "type": "boolean",
            "example": true
          }
        }
      }
    }
  }
}

```

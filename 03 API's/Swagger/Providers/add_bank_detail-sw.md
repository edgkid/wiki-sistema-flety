### Agregar Banco

```json
{
  "openapi": "3.0.0",
  "info": {
    "title": "Banking & Payouts API",
    "description": "API para la gestión de cuentas bancarias y verificación de identidad de proveedores para el procesamiento de pagos.",
    "version": "1.0.0"
  },
  "paths": {
    "/add_bank_detail": {
      "post": {
        "summary": "Agregar detalles bancarios y documentos",
        "description": "Registra la cuenta bancaria del proveedor y carga los documentos de identidad requeridos por la pasarela de pago (ej. Stripe).",
        "requestBody": {
          "required": true,
          "content": {
            "multipart/form-data": {
              "schema": {
                "$ref": "#/components/schemas/AddBankDetailRequest"
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "Cuenta bancaria y documentos registrados exitosamente",
            "content": {
              "application/json": {
                "schema": {
                  "$ref": "#/components/schemas/AddBankDetailResponse"
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
      "AddBankDetailRequest": {
        "type": "object",
        "required": [
          "provider_id",
          "token",
          "account_number",
          "routing_number",
          "password",
          "front",
          "back",
          "identity"
        ],
        "properties": {
          "provider_id": { "type": "string", "example": "{{PROVIDER_ID}}" },
          "token": { "type": "string", "example": "{{PROVIDER_TOKEN}}" },
          "account_number": { "type": "string", "example": "000123456789" },
          "address": { "type": "string", "example": "123 State St" },
          "gender": { "type": "string", "example": "male" },
          "account_holder_name": { "type": "string", "example": "Test" },
          "routing_number": { "type": "string", "example": "110000000" },
          "password": { "type": "string", "format": "password", "example": "123456" },
          "social_unique_id": { "type": "string", "example": "" },
          "account_holder_type": { "type": "string", "example": "individual" },
          "dob": { "type": "string", "description": "Fecha de nacimiento (D-MM-YYYY)", "example": "1-11-2000" },
          "state": { "type": "string", "example": "NY" },
          "postal_code": { "type": "string", "example": "12345" },
          "payment_gateway_type": { "type": "integer", "example": 10 },
          "personal_id_number": { "type": "string", "example": "0000" },
          "front": {
            "type": "string",
            "format": "binary",
            "description": "Imagen frontal de la licencia de conducir o ID"
          },
          "back": {
            "type": "string",
            "format": "binary",
            "description": "Imagen trasera de la licencia de conducir o ID"
          },
          "identity": {
            "type": "string",
            "format": "binary",
            "description": "Documento de identidad adicional o selfie de verificación"
          }
        }
      },
      "AddBankDetailResponse": {
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

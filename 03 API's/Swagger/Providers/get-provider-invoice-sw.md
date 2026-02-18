### Consultar Factura

```json
{
  "openapi": "3.0.0",
  "info": {
    "title": "Provider Invoice Retrieval API",
    "description": "Endpoint para obtener la información detallada de la factura.",
    "version": "1.0.0"
  },
  "paths": {
    "/getproviderinvoice": {
      "post": {
        "summary": "Obtener factura del proveedor",
        "description": "Recupera los datos de facturación..",
        "requestBody": {
          "required": true,
          "content": {
            "application/json": {
              "schema": {
                "$ref": "#/components/schemas/GetProviderInvoiceRequest"
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "Operación exitosa",
            "content": {
              "application/json": {
                "schema": {
                  "$ref": "#/components/schemas/GetProviderInvoiceResponse"
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
      "GetProviderInvoiceRequest": {
        "type": "object",
        "required": [
          "provider_id",
          "token",
          "trip_id"
        ],
        "properties": {
          "provider_id": {
            "type": "string",
            "description": "Identificador único del proveedor.",
            "example": "{{PROVIDER_ID}}"
          },
          "token": {
            "type": "string",
            "description": "Token de autenticación de seguridad.",
            "example": "{{PROVIDER_TOKEN}}"
          },
          "trip_id": {
            "type": "string",
            "description": "ID del viaje del cual se solicita la factura.",
            "example": "{{TRIP_ID}}"
          }
        }
      },
      "GetProviderInvoiceResponse": {
        "type": "object",
        "properties": {
          "success": {
            "type": "boolean",
            "description": "Estado de la solicitud.",
            "example": true
          }
        }
      }
    }
  }
}
```

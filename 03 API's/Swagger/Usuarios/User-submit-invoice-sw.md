### Envió de Facturas

```json
{
  "openapi": "3.0.0",
  "info": {
    "title": "API de Facturación de Viajes",
    "description": "Endpoint para que los usuarios envíen facturas asociadas a un viaje.",
    "version": "1.0.0"
  },
  "paths": {
    "/user_submit_invoice": {
      "post": {
        "summary": "Enviar factura de usuario",
        "operationId": "submitInvoice",
        "requestBody": {
          "description": "Datos necesarios para registrar la factura",
          "required": true,
          "content": {
            "application/json": {
              "schema": {
                "type": "object",
                "properties": {
                  "user_id": {
                    "type": "string",
                    "example": "USR-12345"
                  },
                  "token": {
                    "type": "string",
                    "example": "abc123456789token"
                  },
                  "trip_id": {
                    "type": "string",
                    "example": "TRIP-987"
                  }
                },
                "required": [
                  "user_id",
                  "token",
                  "trip_id"
                ]
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
          },
          "401": {
            "description": "Token inválido o no autorizado"
          },
          "400": {
            "description": "Petición mal formada o faltan campos obligatorios"
          }
        }
      }
    }
  }
}

```

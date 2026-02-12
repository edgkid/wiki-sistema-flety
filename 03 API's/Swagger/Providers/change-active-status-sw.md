### Cambio de Estatus de Disponibilidad del Proveedor

```json
{
  "openapi": "3.0.0",
  "info": {
    "title": "Provider State API",
    "description": "API para alternar el estado de disponibilidad (Online/Offline) del proveedor.",
    "version": "1.0.0"
  },
  "paths": {
    "/togglestate": {
      "post": {
        "summary": "Cambiar estado de disponibilidad",
        "description": "Permite al proveedor ponerse en línea o fuera de línea mediante el flag is_active.",
        "requestBody": {
          "required": true,
          "content": {
            "application/json": {
              "schema": {
                "$ref": "#/components/schemas/ToggleStateRequest"
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "Estado actualizado exitosamente",
            "content": {
              "application/json": {
                "schema": {
                  "$ref": "#/components/schemas/ToggleStateResponse"
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
      "ToggleStateRequest": {
        "type": "object",
        "required": [
          "provider_id",
          "token",
          "is_active"
        ],
        "properties": {
          "provider_id": {
            "type": "string",
            "example": "{{PROVIDER_ID}}"
          },
          "token": {
            "type": "string",
            "example": "{{PROVIDER_TOKEN}}"
          },
          "is_active": {
            "type": "integer",
            "enum": [0, 1],
            "description": "0 para Offline, 1 para Online",
            "example": 1
          }
        }
      },
      "ToggleStateResponse": {
        "type": "object",
        "properties": {
          "success": {
            "type": "boolean",
            "example": true
          },
          "message": {
            "type": "string",
            "example": "26"
          },
          "is_active": {
            "type": "integer",
            "example": 1
          }
        }
      }
    }
  }
}

```

### Actualizar Detalles de Configuración de Perfil de Proveedor

```json
{
  "openapi": "3.0.0",
  "info": {
    "title": "Provider Setting API",
    "description": "Permite la actualización de configuraciones del perfil de proveedor.",
    "version": "1.0.0"
  },
  "paths": {
    "/update_provider_setting": {
      "post": {
        "summary": "Actualizar idiomas del proveedor",
        "description": "Endpoint diseñado para modificar la lista de idiomas asociados al perfil de un proveedor mediante su ID y token de autenticación.",
        "requestBody": {
          "required": true,
          "content": {
            "application/json": {
              "schema": {
                "$ref": "#/components/schemas/UpdateProviderSettingRequest"
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "Configuración actualizada con éxito",
            "content": {
              "application/json": {
                "schema": {
                  "$ref": "#/components/schemas/UpdateProviderSettingResponse"
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
      "UpdateProviderSettingRequest": {
        "type": "object",
        "required": [
          "provider_id",
          "token",
          "languages"
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
          "languages": {
            "type": "array",
            "items": {
              "type": "string",
              "example": "6197a9d7a38f1f1fa6a233d7"
            }
          }
        }
      },
      "UpdateProviderSettingResponse": {
        "type": "object",
        "properties": {
          "success": {
            "type": "boolean",
            "example": true
          },
          "languages": {
            "type": "array",
            "items": {
              "type": "string",
              "example": "6197a9d7a38f1f1fa6a233d7"
            }
          }
        }
      }
    }
  }
}

```

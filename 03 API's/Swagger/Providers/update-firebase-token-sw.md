### Actualizar Token de Firebase

```json
{
  "openapi": "3.0.0",
  "info": {
    "title": "Notifications & Device API",
    "description": "API para la gestión de tokens de dispositivos y configuración de notificaciones push para proveedores.",
    "version": "1.0.0"
  },
  "paths": {
    "/updateproviderdevicetoken": {
      "post": {
        "summary": "Actualizar token de dispositivo",
        "description": "Actualiza el token del dispositivo asociado al proveedor para asegurar la entrega de notificaciones push.",
        "requestBody": {
          "required": true,
          "content": {
            "application/json": {
              "schema": {
                "$ref": "#/components/schemas/UpdateDeviceTokenRequest"
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "Token actualizado correctamente",
            "content": {
              "application/json": {
                "schema": {
                  "$ref": "#/components/schemas/UpdateDeviceTokenResponse"
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
      "UpdateDeviceTokenRequest": {
        "type": "object",
        "required": [
          "provider_id",
          "token",
          "device_token"
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
          "device_token": {
            "type": "string",
            "description": "El nuevo token generado por el servicio de notificaciones (FCM, APNs, etc.).",
            "example": "new_device_token"
          }
        }
      },
      "UpdateDeviceTokenResponse": {
        "type": "object",
        "properties": {
          "success": {
            "type": "boolean",
            "example": true
          },
          "message": {
            "type": "string",
            "description": "Código de éxito (50 indica actualización exitosa).",
            "example": "50"
          }
        }
      }
    }
  }
}

```
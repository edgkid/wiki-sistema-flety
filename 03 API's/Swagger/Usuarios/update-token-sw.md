### Actualización de Token

```json
{
  "openapi": "3.0.0",
  "info": {
    "title": "API Actualizar toke n",
    "version": "1.0.0",
    "description": "API para gestionar la información del usuario, actualización del token."
  },
  "paths": {
    "/updateuserdevicetoken": {
      "post": {
        "summary": "Actualizar el Device Token del Usuario",
        "description": "Permite actualizar el token de notificación del dispositivo (device_token) de un usuario para asegurar la entrega correcta de notificaciones push.",
        "requestBody": {
          "required": true,
          "content": {
            "application/json": {
              "schema": {
                "type": "object",
                "properties": {
                  "user_id": {
                    "type": "string",
                    "description": "ID del usuario cuya información se va a actualizar."
                  },
                  "token": {
                    "type": "string",
                    "description": "Token de autenticación o sesión del usuario."
                  },
                  "device_token": {
                    "type": "string",
                    "description": "Nuevo token único del dispositivo para notificaciones push (por ejemplo, FCM o APNS)."
                  }
                },
                "required": [
                  "user_id",
                  "token",
                  "device_token"
                ],
                "example": {
                  "user_id": "{{USER_ID}}",
                  "token": "{{USER_TOKEN}}",
                  "device_token": "new_device_token"
                }
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "El Device Token del usuario ha sido actualizado exitosamente.",
            "content": {
              "application/json": {
                "schema": {
                  "type": "object",
                  "properties": {
                    "success": {
                      "type": "boolean",
                      "description": "Indica si la operación fue exitosa."
                    },
                    "message": {
                      "type": "string",
                      "description": "Código o mensaje de respuesta. (Ej: '51')"
                    }
                  },
                  "example": {
                    "success": true,
                    "message": "51"
                  }
                }
              }
            }
          },
          "400": {
            "description": "Solicitud inválida (ej. falta un parámetro requerido)."
          },
          "401": {
            "description": "No autorizado (ej. 'token' inválido o expirado)."
          }
        }
      }
    }
  }
}

```

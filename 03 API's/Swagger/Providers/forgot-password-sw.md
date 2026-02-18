## Recuperar Contraseña

```json
{
  "openapi": "3.0.0",
  "info": {
    "title": "Authentication API",
    "description": "API para la gestión de acceso y recuperación de cuentas de usuario y proveedores.",
    "version": "1.0.0"
  },
  "paths": {
    "/forgotpassword": {
      "post": {
        "summary": "Recuperar contraseña",
        "description": "Inicia el proceso de restablecimiento de contraseña.",
        "requestBody": {
          "required": true,
          "content": {
            "application/json": {
              "schema": {
                "$ref": "#/components/schemas/ForgotPasswordRequest"
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "Solicitud procesada correctamente",
            "content": {
              "application/json": {
                "schema": {
                  "$ref": "#/components/schemas/ForgotPasswordResponse"
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
      "ForgotPasswordRequest": {
        "type": "object",
        "required": [
          "email",
          "type"
        ],
        "properties": {
          "email": {
            "type": "string",
            "format": "email",
            "example": "nick@driver.com"
          },
          "type": {
            "type": "string",
            "description": "Identificador del tipo de usuario (Proveedor/Cliente).",
            "example": "{{PROVIDER_UNIQUE_NUMBER}}"
          }
        }
      },
      "ForgotPasswordResponse": {
        "type": "object",
        "properties": {
          "success": {
            "type": "boolean",
            "example": true
          },
          "message": {
            "type": "string",
            "description": "Código de confirmación de envío (ej. '77').",
            "example": "77"
          }
        }
      }
    }
  }
}
```

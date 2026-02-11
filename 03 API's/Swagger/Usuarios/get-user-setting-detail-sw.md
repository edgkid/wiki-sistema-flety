### Detalles de Configuración de Usuario

```json
{
  "openapi": "3.0.0",
  "info": {
    "title": "User Settings and Details API",
    "version": "1.0.0",
    "description": "Obtiene la configuración de la aplicación y los detalles del perfil del usuario para la versión y dispositivo especificados."
  },
  "servers": [
    {
      "url": "{{URL}}",
      "description": "Servidor principal de la API"
    }
  ],
  "paths": {
    "/get_user_setting_detail": {
      "post": {
        "summary": "Obtener detalles de la configuración y perfil del usuario",
        "operationId": "getUserSettingDetail",
        "tags": [
          "User"
        ],
        "requestBody": {
          "required": true,
          "content": {
            "application/json": {
              "schema": {
                "type": "object",
                "properties": {
                  "user_id": {
                    "type": "string",
                    "description": "ID único del usuario.",
                    "example": "{{USER_ID}}"
                  },
                  "token": {
                    "type": "string",
                    "description": "Token de autenticación de la sesión del usuario.",
                    "example": "{{USER_TOKEN}}"
                  },
                  "app_version": {
                    "type": "string",
                    "description": "Versión de la aplicación móvil.",
                    "example": "1.0.0"
                  },
                  "device_type": {
                    "type": "string",
                    "description": "Tipo de dispositivo del usuario (e.g., android, ios).",
                    "example": "android"
                  }
                },
                "required": [
                  "user_id",
                  "token",
                  "app_version",
                  "device_type"
                ]
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "Detalles de la configuración y del usuario obtenidos exitosamente.",
            "content": {
              "application/json": {
                "schema": {
                  "$ref": "#/components/schemas/UserSettingDetailResponse"
                },
                "example": {
                  "success": true,
                  "setting_detail": {
                    "terms_and_condition_url": "https://localhost:5000/terms&condition",
                    "privacy_policy_url": "https://localhost:5000/privacy",
                    "admin_phone": "",
                    "contactUsEmail": "",
                    "android_user_app_version_code": "1.0.0"
                  },
                  "user_detail": {
                    "first_name": "Android",
                    "email": "android@user.com",
                    "token": "kE0Gx6RK2wsa3dE4X6v7L3oMqnKJIDEd"
                  }
                }
              }
            }
          },
          "401": {
            "description": "Token no válido o no autorizado (ejemplo de respuesta con error).",
            "content": {
              "application/json": {
                "schema": {
                  "type": "object",
                  "properties": {
                    "success": { "type": "boolean", "example": false },
                    "error_code": { "type": "string", "example": "451" }
                  }
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
      "UserSettingDetailResponse": {
        "type": "object",
        "properties": {
          "success": {
            "type": "boolean",
            "description": "Indica si la operación fue exitosa."
          },
          "setting_detail": {
            "type": "object",
            "description": "Configuraciones globales de la aplicación.",
            "properties": {
              "terms_and_condition_url": { "type": "string", "description": "URL de los términos y condiciones." },
              "privacy_policy_url": { "type": "string", "description": "URL de la política de privacidad." },
              "admin_phone": { "type": "string", "description": "Número de teléfono del administrador." },
              "contactUsEmail": { "type": "string", "description": "Correo electrónico de contacto." },
              "android_user_app_google_key": { "type": "string", "description": "Clave de Google Maps para la aplicación Android (si aplica)." },
              "android_user_app_version_code": { "type": "string", "description": "Código de versión de la aplicación Android." },
              "android_user_app_force_update": { "type": "boolean", "description": "Indica si se requiere una actualización forzosa." },
              "is_tip": { "type": "boolean", "description": "Indica si las propinas están habilitadas." },
              "scheduled_request_pre_start_minute": { "type": "integer", "description": "Minutos antes de que comience una solicitud programada." },
              "stripe_publishable_key": { "type": "string", "description": "Clave publicable de Stripe." },
              "userPath": { "type": "boolean", "description": "Indica si el seguimiento de ruta del usuario está activado." },
              "userSms": { "type": "boolean", "description": "Indica si las notificaciones por SMS están activadas para el usuario." },
              "userEmailVerification": { "type": "boolean", "description": "Indica si se requiere verificación por correo electrónico." },
              "twilio_call_masking": { "type": "boolean", "description": "Indica si se utiliza enmascaramiento de llamadas con Twilio." },
              "is_show_estimation_in_provider_app": { "type": "boolean", "description": "Muestra la estimación en la aplicación del proveedor." },
              "is_show_estimation_in_user_app": { "type": "boolean", "description": "Muestra la estimación en la aplicación del usuario." },
              "android_places_autocomplete_key": { "type": "string", "description": "Clave para la función de autocompletado de Places en Android." },
              "image_base_url": { "type": "string", "description": "URL base para imágenes." }
            },
            "required": [
              "terms_and_condition_url",
              "privacy_policy_url",
              "android_user_app_version_code"
            ]
          },
          "user_detail": {
            "type": "object",
            "description": "Detalles del perfil del usuario logueado.",
            "properties": {
              "first_name": { "type": "string" },
              "last_name": { "type": "string" },
              "email": { "type": "string", "format": "email" },
              "country_phone_code": { "type": "string" },
              "is_document_uploaded": { "type": "integer" },
              "address": { "type": "string" },
              "is_approved": { "type": "integer" },
              "user_id": { "type": "string" },
              "social_ids": { "type": "array", "items": { "type": "string" } },
              "social_unique_id": { "type": "string" },
              "phone": { "type": "string" },
              "login_by": { "type": "string" },
              "city": { "type": "string" },
              "country": { "type": "string" },
              "referral_code": { "type": "string" },
              "rate": { "type": "number", "format": "float" },
              "rate_count": { "type": "integer" },
              "is_referral": { "type": "integer" },
              "token": { "type": "string" },
              "picture": { "type": "string" },
              "wallet_currency_code": { "type": "string" },
              "country_detail": {
                "type": "object",
                "properties": {
                  "is_referral": { "type": "boolean" }
                }
              }
            },
            "required": [
              "user_id",
              "first_name",
              "email"
            ]
          }
        },
        "required": [
          "success",
          "setting_detail",
          "user_detail"
        ]
      }
    }
  }
}

```


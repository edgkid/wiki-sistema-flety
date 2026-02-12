
### Configuración y Perfil de Proveedor

```json
{
  "openapi": "3.0.0",
  "info": {
    "title": "Provider Settings API",
    "description": "API para obtener la configuración  y el perfil detallado del proveedor.",
    "version": "1.0.0"
  },
  "paths": {
    "/get_provider_setting_detail": {
      "post": {
        "summary": "Obtener detalles de configuración del proveedor",
        "description": "Retorna las políticas de la plataforma, llaves de configuración de apps y el estado actual del perfil del proveedor.",
        "requestBody": {
          "required": true,
          "content": {
            "application/json": {
              "schema": {
                "$ref": "#/components/schemas/SettingsRequest"
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "Configuración y detalles del proveedor obtenidos correctamente",
            "content": {
              "application/json": {
                "schema": {
                  "$ref": "#/components/schemas/SettingsResponse"
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
      "SettingsRequest": {
        "type": "object",
        "properties": {
          "provider_id": {
            "type": "string",
            "example": "{{PROVIDER_ID}}"
          },
          "token": {
            "type": "string",
            "example": "{{PROVIDER_TOKEN}}"
          }
        },
        "required": ["provider_id", "token"]
      },
      "SettingsResponse": {
        "type": "object",
        "properties": {
          "success": { "type": "boolean" },
          "setting_detail": { "$ref": "#/components/schemas/SettingDetail" },
          "phone_number_min_length": { "type": "integer", "example": 10 },
          "phone_number_length": { "type": "integer", "example": 10 },
          "provider_detail": { "$ref": "#/components/schemas/ProviderDetail" }
        }
      },
      "SettingDetail": {
        "type": "object",
        "properties": {
          "terms_and_condition_url": { "type": "string" },
          "privacy_policy_url": { "type": "string" },
          "admin_phone": { "type": "string" },
          "contactUsEmail": { "type": "string" },
          "is_tip": { "type": "boolean" },
          "is_toll": { "type": "boolean" },
          "scheduled_request_pre_start_minute": { "type": "integer" },
          "providerEmailVerification": { "type": "boolean" },
          "stripe_publishable_key": { "type": "string" },
          "providerSms": { "type": "boolean" },
          "twilio_call_masking": { "type": "boolean" },
          "is_provider_initiate_trip": { "type": "boolean" },
          "providerPath": { "type": "boolean" },
          "image_base_url": { "type": "string" },
          "is_show_estimation_in_provider_app": { "type": "boolean" },
          "is_show_estimation_in_user_app": { "type": "boolean" },
          "ios_provider_app_google_key": { "type": "string" },
          "ios_provider_app_version_code": { "type": "string" },
          "ios_provider_app_force_update": { "type": "boolean" },
          "ios_places_autocomplete_key": { "type": "string" }
        }
      },
      "ProviderDetail": {
        "type": "object",
        "properties": {
          "first_name": { "type": "string" },
          "last_name": { "type": "string" },
          "email": { "type": "string" },
          "country_phone_code": { "type": "string" },
          "is_document_uploaded": { "type": "integer" },
          "address": { "type": "string" },
          "is_approved": { "type": "integer" },
          "_id": { "type": "string" },
          "social_unique_id": { "type": "string" },
          "phone": { "type": "string" },
          "login_by": { "type": "string" },
          "is_documents_expired": { "type": "boolean" },
          "account_id": { "type": "string" },
          "bank_id": { "type": "string" },
          "city": { "type": "string" },
          "country": { "type": "string" },
          "rate": { "type": "number" },
          "rate_count": { "type": "integer" },
          "token": { "type": "string" },
          "is_vehicle_document_uploaded": { "type": "boolean" },
          "service_type": { "type": "string" },
          "admintypeid": { "type": "string" },
          "is_available": { "type": "integer" },
          "is_active": { "type": "integer" },
          "is_partner_approved_by_admin": { "type": "integer" },
          "picture": { "type": "string" },
          "wallet_currency_code": { "type": "string" },
          "is_referral": { "type": "integer" },
          "referral_code": { "type": "string" },
          "country_detail": {
            "type": "object",
            "properties": {
              "is_referral": { "type": "boolean" }
            }
          }
        }
      }
    }
  }
}
```

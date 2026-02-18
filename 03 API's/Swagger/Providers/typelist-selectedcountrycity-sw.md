### Lista de Ciudades con su Respectiva Configuración

```json
{
  "openapi": "3.0.0",
  "info": {
    "title": "Location Services API",
    "description": "Configuración dinámica de reglas de negocio, moneda y servicios según la ubicación del proveedor.",
    "version": "1.0.0"
  },
  "paths": {
    "/typelist_selectedcountrycity": {
      "post": {
        "summary": "Obtener configuración regional y servicios",
        "description": "Retorna la configuración completa de la ciudad detectada, incluyendo moneda, tipos de vehículos y pasarelas de pago.",
        "requestBody": {
          "required": true,
          "content": {
            "application/json": {
              "schema": {
                "$ref": "#/components/schemas/TypeListRequest"
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "Configuración cargada exitosamente",
            "content": {
              "application/json": {
                "schema": {
                  "$ref": "#/components/schemas/TypeListResponse"
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
      "TypeListRequest": {
        "type": "object",
        "required": ["provider_id", "token", "country", "latitude", "longitude", "country_code"],
        "properties": {
          "provider_id": { "type": "string", "example": "{{PROVIDER_ID}}" },
          "token": { "type": "string", "example": "{{PROVIDER_TOKEN}}" },
          "country": { "type": "string", "example": "India" },
          "latitude": { "type": "number", "example": 22.30035 },
          "longitude": { "type": "number", "example": 70.7989615 },
          "country_code": { "type": "string", "example": "IN" }
        }
      },
      "TypeListResponse": {
        "type": "object",
        "properties": {
          "success": { "type": "boolean", "example": true },
          "message": { "type": "string", "example": "63" },
          "currency": { "type": "string", "example": "₹" },
          "currencycode": { "type": "string", "example": "INR" },
          "city_detail": {
            "type": "object",
            "properties": {
              "_id": { "type": "string", "example": "6022777b65b27b2840e6ea1d" },
              "cityname": { "type": "string", "example": "Rajkot" },
              "timezone": { "type": "string", "example": "Asia/Kolkata" },
              "is_payment_mode_cash": { "type": "integer", "example": 1 },
              "is_payment_mode_card": { "type": "integer", "example": 1 },
              "cityRadius": { "type": "number", "example": 50 }
            }
          },
          "payment_gateway": {
            "type": "array",
            "items": {
              "type": "object",
              "properties": {
                "id": { "type": "integer", "example": 10 },
                "name": { "type": "string", "example": "Stripe" }
              }
            }
          },
          "citytypes": {
            "type": "array",
            "items": {
              "type": "object",
              "properties": {
                "_id": { "type": "string", "example": "602278c765b27b2840e6ea1e" },
                "typename": { "type": "string", "example": "Suv" },
                "base_price": { "type": "number", "example": 95 },
                "price_per_unit_distance": { "type": "number", "example": 4 },
                "type_details": {
                  "type": "object",
                  "properties": {
                    "type_image_url": { "type": "string", "example": "service_type_images/6020edb101a03b0612ffa8f9VmdE.png" }
                  }
                }
              }
            }
          },
          "server_time": { "type": "string", "format": "date-time", "example": "2021-11-23T13:40:37.277Z" }
        }
      }
    }
  }
}

```
### Detalle de ciudades y Servicios

```json
{
  "openapi": "3.0.0",
  "info": {
    "title": "API - de Selección de Ciudad y Tipos de Viaje",
    "version": "1.0.0",
    "description": "Permite obtener los detalles de la ciudad y los tipos de servicio de transporte disponibles según la ubicación proporcionada (país y coordenadas)."
  },
  "servers": [
    {
      "url": "{{URL}}",
      "description": "URL base de la API"
    }
  ],
  "paths": {
    "/typelist_selectedcountrycity": {
      "post": {
        "summary": "Obtener tipos de servicio y detalles de la ciudad",
        "operationId": "getCityTypesAndDetails",
        "tags": [
          "Ubicación y Servicios"
        ],
        "requestBody": {
          "required": true,
          "content": {
            "application/json": {
              "schema": {
                "$ref": "#/components/schemas/TypeListRequest"
              },
              "example": {
                "user_id": "{{USER_ID}}",
                "token": "{{USER_TOKEN}}",
                "country": "India",
                "latitude": 22.300350,
                "longitude": 70.7989614999999,
                "country_code": "IN"
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "Detalles de la ciudad y tipos de servicio obtenidos exitosamente.",
            "content": {
              "application/json": {
                "schema": {
                  "$ref": "#/components/schemas/TypeListResponse"
                },
                "example": {
                  "success": true,
                  "message": "63",
                  "currency": "₹",
                  "currencycode": "INR",
                  "city_detail": {
                    "_id": "6022777b65b27b2840e6ea1d",
                    "cityLatLong": [
                      22.3038945,
                      70.80215989999999
                    ],
                    "cityRadius": 50,
                    "cityname": "Rajkot",
                    "full_cityname": "Rajkot, Gujarat",
                    "is_payment_mode_card": 1,
                    "is_payment_mode_cash": 1
                  },
                  "payment_gateway": [
                    {
                      "id": 10,
                      "name": "Stripe"
                    }
                  ],
                  "citytypes": [
                    {
                      "_id": "602278c765b27b2840e6ea1e",
                      "typename": "Suv",
                      "base_price": 95,
                      "min_fare": 100,
                      "max_space": 4,
                      "price_per_unit_distance": 4
                    }
                  ],
                  "server_time": "2021-11-23T13:40:37.277Z",
                  "is_corporate_request": false
                }
              }
            }
          },
          "400": {
            "description": "Solicitud inválida o faltan parámetros."
          }
        }
      }
    }
  },
  "components": {
    "schemas": {
      "TypeListRequest": {
        "type": "object",
        "properties": {
          "user_id": {
            "type": "string",
            "description": "Identificador único del usuario."
          },
          "token": {
            "type": "string",
            "description": "Token de autenticación del usuario."
          },
          "country": {
            "type": "string",
            "description": "Nombre del país."
          },
          "latitude": {
            "type": "number",
            "format": "float",
            "description": "Latitud actual del usuario."
          },
          "longitude": {
            "type": "number",
            "format": "float",
            "description": "Longitud actual del usuario."
          },
          "country_code": {
            "type": "string",
            "description": "Código de país (ej: IN)."
          }
        },
        "required": [
          "user_id",
          "token",
          "country",
          "latitude",
          "longitude",
          "country_code"
        ]
      },
      "CityDetail": {
        "type": "object",
        "properties": {
          "_id": {
            "type": "string"
          },
          "countryid": {
            "type": "string"
          },
          "cityLatLong": {
            "type": "array",
            "items": {
              "type": "number",
              "format": "float"
            },
            "description": "Latitud y Longitud de la ciudad."
          },
          "cityRadius": {
            "type": "integer",
            "description": "Radio de la ciudad."
          },
          "cityname": {
            "type": "string"
          },
          "timezone": {
            "type": "string"
          },
          "full_cityname": {
            "type": "string"
          },
          "countryname": {
            "type": "string"
          },
          "is_payment_mode_card": {
            "type": "integer",
            "description": "1 si está habilitado el pago con tarjeta."
          },
          "is_payment_mode_cash": {
            "type": "integer",
            "description": "1 si está habilitado el pago en efectivo."
          }
        },
        "description": "Detalles de la ciudad encontrada por las coordenadas."
      },
      "PaymentGateway": {
        "type": "object",
        "properties": {
          "id": {
            "type": "integer"
          },
          "name": {
            "type": "string"
          }
        },
        "description": "Información de una pasarela de pago disponible."
      },
      "CityType": {
        "type": "object",
        "properties": {
          "_id": {
            "type": "string"
          },
          "typeid": {
            "type": "string",
            "description": "ID del tipo de servicio/vehículo."
          },
          "typename": {
            "type": "string",
            "description": "Nombre del tipo de vehículo (ej: Suv)."
          },
          "max_space": {
            "type": "integer",
            "description": "Capacidad máxima de pasajeros."
          },
          "cancellation_fee": {
            "type": "number",
            "format": "float"
          },
          "base_price": {
            "type": "number",
            "format": "float"
          },
          "price_per_unit_distance": {
            "type": "number",
            "format": "float",
            "description": "Costo por unidad de distancia."
          },
          "min_fare": {
            "type": "number",
            "format": "float",
            "description": "Tarifa mínima."
          }
        },
        "description": "Detalles y tarifas de un tipo de servicio de transporte."
      },
      "TypeListResponse": {
        "type": "object",
        "properties": {
          "success": {
            "type": "boolean",
            "description": "Indica si la solicitud fue exitosa."
          },
          "message": {
            "type": "string",
            "description": "Mensaje del servidor (a menudo puede ser un código o valor)."
          },
          "currency": {
            "type": "string",
            "description": "Símbolo de la moneda (ej: ₹)."
          },
          "currencycode": {
            "type": "string",
            "description": "Código de la moneda (ej: INR)."
          },
          "city_detail": {
            "$ref": "#/components/schemas/CityDetail"
          },
          "payment_gateway": {
            "type": "array",
            "items": {
              "$ref": "#/components/schemas/PaymentGateway"
            },
            "description": "Lista de pasarelas de pago disponibles."
          },
          "citytypes": {
            "type": "array",
            "items": {
              "$ref": "#/components/schemas/CityType"
            },
            "description": "Lista de tipos de servicio disponibles en la ciudad."
          },
          "server_time": {
            "type": "string",
            "format": "date-time",
            "description": "Hora de la respuesta del servidor."
          },
          "is_corporate_request": {
            "type": "boolean",
            "description": "Indica si está habilitada la solicitud corporativa."
          }
        },
        "required": [
          "success",
          "currency",
          "currencycode",
          "city_detail",
          "payment_gateway",
          "citytypes",
          "server_time",
          "is_corporate_request"
        ]
      }
    }
  }
}


```


### Registra Ruta de Google Maps

```json

{
  "openapi": "3.0.0",
  "info": {
    "title": "Google Map Path API",
    "description": "API para registrar rutas de Google Maps asociadas a un viaje específico.",
    "version": "1.0.0"
  },
  "servers": [
    {
      "url": "{{URL}}",
      "description": "Servidor principal"
    }
  ],
  "paths": {
    "/setgooglemappath": {
      "post": {
        "summary": "Establecer ruta de Google Maps",
        "operationId": "setGoogleMapPath",
        "requestBody": {
          "description": "Datos de la ruta de Google Maps y ID del viaje",
          "required": true,
          "content": {
            "application/json": {
              "schema": {
                "$ref": "#/components/schemas/PathRequest"
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "Ruta guardada exitosamente",
            "content": {
              "application/json": {
                "schema": {
                  "$ref": "#/components/schemas/SuccessResponse"
                },
                "example": {
                  "success": true
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
      "PathRequest": {
        "type": "object",
        "properties": {
          "trip_id": {
            "type": "string",
            "example": "619f7b2e9b1d2e0016f5a3a1"
          },
          "googlePathStartLocationToPickUpLocation": {
            "type": "object",
            "nullable": true,
            "description": "Objeto de ruta de Google desde el inicio hasta el punto de recogida"
          },
          "googlePickUpLocationToDestinationLocation": {
            "type": "object",
            "properties": {
              "geocoded_waypoints": {
                "type": "array",
                "items": {
                  "type": "object"
                }
              },
              "routes": {
                "type": "array",
                "items": {
                  "$ref": "#/components/schemas/GoogleRoute"
                }
              },
              "status": {
                "type": "string",
                "example": "OK"
              }
            }
          }
        },
        "required": [
          "trip_id"
        ]
      },
      "GoogleRoute": {
        "type": "object",
        "properties": {
          "bounds": {
            "type": "object"
          },
          "legs": {
            "type": "array",
            "items": {
              "type": "object",
              "properties": {
                "distance": {
                  "$ref": "#/components/schemas/ValueText"
                },
                "duration": {
                  "$ref": "#/components/schemas/ValueText"
                },
                "end_address": {
                  "type": "string"
                },
                "start_address": {
                  "type": "string"
                },
                "steps": {
                  "type": "array",
                  "items": {
                    "type": "object"
                  }
                }
              }
            }
          },
          "overview_polyline": {
            "type": "object",
            "properties": {
              "points": {
                "type": "string"
              }
            }
          },
          "summary": {
            "type": "string"
          }
        }
      },
      "ValueText": {
        "type": "object",
        "properties": {
          "text": {
            "type": "string"
          },
          "value": {
            "type": "integer"
          }
        }
      },
      "SuccessResponse": {
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
}```

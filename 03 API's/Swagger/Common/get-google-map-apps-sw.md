### Metadatos de Google Maps para Viajes

```json
{
  "openapi": "3.0.0",
  "info": {
    "title": "Trip Routing API",
    "description": "API para obtener el trazado de la ruta del viaje y la información en coordenadas a travez de Google Maps.",
    "version": "1.0.0"
  },
  "paths": {
    "/getgooglemappath": {
      "post": {
        "summary": "Obtener ruta de mapa",
        "description": "Recupera  los metadatos de Google Maps para dibujar el trayecto del viaje en el cliente.",
        "requestBody": {
          "required": true,
          "content": {
            "application/json": {
              "schema": {
                "type": "object",
                "required": ["trip_id"],
                "properties": {
                  "trip_id": {
                    "type": "string",
                    "example": "{{TRIP_ID}}"
                  }
                }
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "Ruta obtenida exitosamente",
            "content": {
              "application/json": {
                "schema": {
                  "$ref": "#/components/schemas/MapPathResponse"
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
      "MapPathResponse": {
        "type": "object",
        "properties": {
          "success": { "type": "boolean", "example": true },
          "triplocation": { "$ref": "#/components/schemas/TripLocation" }
        }
      },
      "TripLocation": {
        "type": "object",
        "properties": {
          "_id": { "type": "string", "example": "619f6c344ae0be5359c6cc86" },
          "tripID": { "type": "string", "example": "619f6c344ae0be5359c6cc85" },
          "trip_unique_id": { "type": "integer", "example": 310 },
          "providerStartLocation": {
            "type": "array",
            "items": { "type": "number" },
            "example": [22.3040449, 70.8022859]
          },
          "googlePickUpLocationToDestinationLocation": {
            "$ref": "#/components/schemas/GoogleMapsData"
          },
          "updated_at": { "type": "string", "format": "date-time" },
          "created_at": { "type": "string", "format": "date-time" }
        }
      },
      "GoogleMapsData": {
        "type": "object",
        "properties": {
          "geocoded_waypoints": { "type": "array", "items": { "type": "object" } },
          "routes": {
            "type": "array",
            "items": {
              "type": "object",
              "properties": {
                "bounds": { "type": "object" },
                "legs": {
                  "type": "array",
                  "items": {
                    "type": "object",
                    "properties": {
                      "distance": { "$ref": "#/components/schemas/ValueText" },
                      "duration": { "$ref": "#/components/schemas/ValueText" },
                      "start_address": { "type": "string" },
                      "end_address": { "type": "string" }
                    }
                  }
                },
                "overview_polyline": {
                  "type": "object",
                  "properties": {
                    "points": { "type": "string", "example": "qgcgCkpcoL..." }
                  }
                }
              }
            }
          },
          "status": { "type": "string", "example": "OK" }
        }
      },
      "ValueText": {
        "type": "object",
        "properties": {
          "text": { "type": "string", "example": "4.6 km" },
          "value": { "type": "integer", "example": 4634 }
        }
      }
    }
  }
}
```

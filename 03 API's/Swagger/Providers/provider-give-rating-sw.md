### Calificación a Usuario

```json
{
  "openapi": "3.0.0",
  "info": {
    "title": "Provider Rating API",
    "description": "Endpoint que permite al proveedor calificar y dejar una reseña sobre el usuario tras finalizar un viaje.",
    "version": "1.0.0"
  },
  "paths": {
    "/providergiverating": {
      "post": {
        "summary": "Calificar usuario",
        "description": "Registra la puntuación y comentarios del proveedor hacia el cliente. Solo se puede ejecutar una vez que el viaje ha finalizado.",
        "requestBody": {
          "required": true,
          "content": {
            "application/json": {
              "schema": {
                "$ref": "#/components/schemas/RatingRequest"
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "Calificación registrada exitosamente",
            "content": {
              "application/json": {
                "schema": {
                  "$ref": "#/components/schemas/RatingResponse"
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
      "RatingRequest": {
        "type": "object",
        "required": [
          "provider_id",
          "trip_id",
          "token",
          "rating"
        ],
        "properties": {
          "provider_id": {
            "type": "string",
            "description": "ID del proveedor que califica.",
            "example": "{{PROVIDER_ID}}"
          },
          "trip_id": {
            "type": "string",
            "description": "ID del viaje calificado.",
            "example": "{{TRIP_ID}}"
          },
          "token": {
            "type": "string",
            "description": "Token de seguridad del proveedor.",
            "example": "{{PROVIDER_TOKEN}}"
          },
          "review": {
            "type": "string",
            "description": "Comentario o reseña textual.",
            "example": "Usuario puntual y amable."
          },
          "rating": {
            "type": "integer",
            "minimum": 1,
            "maximum": 5,
            "description": "Puntuación numérica del 1 al 5.",
            "example": 4
          }
        }
      },
      "RatingResponse": {
        "type": "object",
        "properties": {
          "success": {
            "type": "boolean",
            "example": true
          },
          "message": {
            "type": "string",
            "description": "Código de respuesta del sistema.",
            "example": "31"
          },
          "error_code": {
            "type": "string",
            "description": "Códigos posibles: 420 (Viaje no finalizado), 437 (Viaje no encontrado), 451 (Token inválido).",
            "example": "420"
          }
        }
      }
    }
  }
}
```

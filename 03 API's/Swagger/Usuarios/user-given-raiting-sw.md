### Para Registro de Puntuación de Servicio

```json
{
  "openapi": "3.0.0",
  "info": {
    "title": "API de Calificaciones",
    "description": "Servicio para registrar la valoración y reseña de un usuario sobre un viaje específico.",
    "version": "1.0.0"
  },
  "paths": {
    "/usergiverating": {
      "post": {
        "summary": "Enviar calificación de viaje",
        "operationId": "userGiveRating",
        "requestBody": {
          "description": "Datos de la reseña y calificación del usuario",
          "required": true,
          "content": {
            "application/json": {
              "schema": {
                "type": "object",
                "properties": {
                  "user_id": {
                    "type": "string",
                    "example": "USR-789"
                  },
                  "trip_id": {
                    "type": "string",
                    "example": "TRIP-456"
                  },
                  "review": {
                    "type": "string",
                    "example": "Excelente servicio, el conductor fue muy amable."
                  },
                  "rating": {
                    "type": "integer",
                    "minimum": 1,
                    "maximum": 5,
                    "example": 4
                  },
                  "token": {
                    "type": "string",
                    "example": "JWT_TOKEN_HERE"
                  }
                },
                "required": [
                  "user_id",
                  "trip_id",
                  "review",
                  "rating",
                  "token"
                ]
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "Calificación registrada con éxito",
            "content": {
              "application/json": {
                "schema": {
                  "type": "object",
                  "properties": {
                    "success": {
                      "type": "boolean",
                      "example": true
                    },
                    "message": {
                      "type": "string",
                      "description": "ID del registro o mensaje de confirmación",
                      "example": "16"
                    }
                  }
                }
              }
            }
          },
          "400": {
            "description": "Petición inválida o faltan parámetros"
          },
          "401": {
            "description": "Token de autenticación inválido"
          }
        }
      }
    }
  }
}

```

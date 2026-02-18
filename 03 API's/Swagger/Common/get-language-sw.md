### Obtener Lista de Idiomas

```json

{
  "openapi": "3.0.0",
  "info": {
    "title": "Configuración e Idiomas API",
    "description": "Endpoint para obtener la lista de idiomas disponibles en la plataforma para la localización de la interfaz de usuario.",
    "version": "1.0.0"
  },
  "paths": {
    "/getlanguages": {
      "post": {
        "summary": "Obtener idiomas disponibles",
        "description": "Recupera todos los idiomas activos configurados en el sistema, incluyendo sus códigos ISO y nombres descriptivos.",
        "responses": {
          "200": {
            "description": "Lista de idiomas recuperada con éxito",
            "content": {
              "application/json": {
                "schema": {
                  "$ref": "#/components/schemas/GetLanguagesResponse"
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
      "LanguageItem": {
        "type": "object",
        "properties": {
          "_id": {
            "type": "string",
            "example": "6197a9d7a38f1f1fa6a233d7"
          },
          "unique_id": {
            "type": "integer",
            "example": 1
          },
          "code": {
            "type": "string",
            "description": "Código ISO del idioma (ej. en, es, fr).",
            "example": "en"
          },
          "name": {
            "type": "string",
            "description": "Nombre legible del idioma.",
            "example": "English"
          },
          "updated_at": {
            "type": "string",
            "format": "date-time",
            "example": "2021-11-19T13:42:47.214Z"
          },
          "created_at": {
            "type": "string",
            "format": "date-time",
            "example": "2021-11-19T13:42:47.214Z"
          }
        }
      },
      "GetLanguagesResponse": {
        "type": "object",
        "properties": {
          "success": {
            "type": "boolean",
            "example": true
          },
          "message": {
            "type": "string",
            "description": "Código de mensaje de éxito (101).",
            "example": "101"
          },
          "languages": {
            "type": "array",
            "items": {
              "$ref": "#/components/schemas/LanguageItem"
            }
          }
        }
      }
    }
  }
}

```

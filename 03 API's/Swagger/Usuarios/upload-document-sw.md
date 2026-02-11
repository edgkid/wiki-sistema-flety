### Cargar Documentos

```json
{
  "openapi": "3.0.0",
  "info": {
    "title": "Api de carga de documentos",
    "version": "1.0.0",
    "description": "API para subir documentos de usuario."
  },
  "servers": [
    {
      "url": "{URL}",
      "variables": {
        "URL": {
          "default": "https://api.ejemplo.com",
        }
      }
    }
  ],
  "paths": {
    "/uploaduserdocument": {
      "post": {
        "summary": "Subir un documento de usuario",
        "description": "Sube y registra la información de un documento asociado a un usuario.",
        "requestBody": {
          "required": true,
          "content": {
            "application/json": {
              "schema": {
                "$ref": "#/components/schemas/UploadDocumentRequest"
              },
              "example": {
                "user_id": "{{USER_ID}}",
                "token": "{{USER_TOKEN}}",
                "unique_code": 123456,
                "expired_date": "2017-03-20T18:30:00.000Z",
                "document_id": "61962d683b0daa5338204ce7"
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "Documento subido exitosamente",
            "content": {
              "application/json": {
                "schema": {
                  "$ref": "#/components/schemas/UploadDocumentResponse"
                },
                "example": {
                  "success": true,
                  "message": "78",
                  "document_picture": "user_document/61962d683b0daa5338204ce7mmLG.jpg",
                  "unique_code": "123456",
                  "expired_date": "2017-03-20T18:30:00.000Z",
                  "is_uploaded": 1,
                  "is_document_uploaded": 1
                }
              }
            }
          },
          "400": {
            "description": "Error en la solicitud o datos no válidos"
          },
          "500": {
            "description": "Error interno del servidor"
          }
        }
      }
    }
  },
  "components": {
    "schemas": {
      "UploadDocumentRequest": {
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
          "unique_code": {
            "type": "integer",
            "format": "int32",
            "description": "Código único para la transacción."
          },
          "expired_date": {
            "type": "string",
            "format": "date-time",
            "description": "Fecha de expiración del documento o de la sesión, en formato ISO 8601."
          },
          "document_id": {
            "type": "string",
            "description": "Identificador único del documento."
          }
        },
        "required": [
          "user_id",
          "token",
          "unique_code",
          "expired_date",
          "document_id"
        ]
      },
      "UploadDocumentResponse": {
        "type": "object",
        "properties": {
          "success": {
            "type": "boolean",
            "description": "Indica si la operación fue exitosa."
          },
          "message": {
            "type": "string",
            "description": "Mensaje de respuesta del servidor (código o texto)."
          },
          "document_picture": {
            "type": "string",
            "description": "Ruta o URL de la imagen del documento subido."
          },
          "unique_code": {
            "type": "string",
            "description": "Código único de la transacción repetido."
          },
          "expired_date": {
            "type": "string",
            "format": "date-time",
            "description": "Fecha de expiración repetida."
          },
          "is_uploaded": {
            "type": "integer",
            "format": "int32",
            "description": "Indicador binario de si la subida se realizó (1=subido)."
          },
          "is_document_uploaded": {
            "type": "integer",
            "format": "int32",
            "description": "Otro indicador binario de si el documento ha sido subido (1=subido)."
          }
        }
      }
    }
  }
}


```

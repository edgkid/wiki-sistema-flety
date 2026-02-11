### Consulta de Documentos de Usuario

```json
{
  "openapi": "3.0.0",
  "info": {
    "title": "API para consultar docuemntos de usuairos",
    "version": "1.0.1",
    "description": "API para obtener los documentos de un usuario, utilizando POST para enviar credenciales."
  },
  "servers": [
    {
      "url": "{URL}",
      "variables": {
        "URL": {
          "default": "https://api.ejemplo.com",
          "description": "URL base de la API, reemplaza con tu dominio real."
        }
      }
    }
  ],
  "paths": {
    "/getuserdocument": {
      "post": {
        "summary": "Obtener documentos de usuario",
        "description": "Recupera la lista de documentos subidos por un usuario. El método se cambia a POST para enviar credenciales en el cuerpo de la solicitud.",
        "requestBody": {
          "required": true,
          "content": {
            "application/json": {
              "schema": {
                "$ref": "#/components/schemas/GetDocumentRequest"
              },
              "example": {
                "user_id": "{{USER_ID}}",
                "token": "{{USER_TOKEN}}"
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "Lista de documentos y/o estados de error.",
            "content": {
              "application/json": {
                "schema": {
                  "type": "array",
                  "items": {
                    "oneOf": [
                      {
                        "$ref": "#/components/schemas/SuccessResponse"
                      },
                      {
                        "$ref": "#/components/schemas/ErrorResponse"
                      }
                    ]
                  }
                },
                "example": [
                  {
                    "success": true,
                    "message": "79",
                    "userdocument": [
                      {
                        "_id": "61962d683b0daa5338204ce7",
                        "user_id": "61962d683b0daa5338204ce6",
                        "document_id": "6023962ed51a7042436be45b",
                        "__v": 0,
                        "updated_at": "2021-11-18T10:39:36.425Z",
                        "created_at": "2021-11-18T10:39:36.425Z",
                        "is_document_expired": false,
                        "is_expired_date": true,
                        "is_unique_code": true,
                        "expired_date": "2017-03-20T18:30:00.000Z",
                        "unique_code": "123456",
                        "is_uploaded": 1,
                        "document_picture": "user_document/61962d683b0daa5338204ce7buMa.jpg",
                        "option": 0,
                        "name": "Photo_ID"
                      }
                    ]
                  }
                ]
              }
            }
          },
          "400": {
            "description": "Solicitud Inválida"
          },
          "401": {
            "description": "No Autorizado (Token Inválido)"
          }
        }
      }
    }
  },
  "components": {
    "schemas": {
      "GetDocumentRequest": {
        "type": "object",
        "properties": {
          "user_id": {
            "type": "string",
            "description": "Identificador único del usuario."
          },
          "token": {
            "type": "string",
            "description": "Token de autenticación del usuario."
          }
        },
        "required": [
          "user_id",
          "token"
        ]
      },
      "UserDocument": {
        "type": "object",
        "properties": {
          "_id": {
            "type": "string",
            "description": "ID interno del documento de usuario."
          },
          "user_id": {
            "type": "string",
            "description": "ID del usuario asociado al documento."
          },
          "document_id": {
            "type": "string",
            "description": "ID del tipo de documento."
          },
          "__v": {
            "type": "integer",
            "description": "Versión del documento (típico de MongoDB)."
          },
          "updated_at": {
            "type": "string",
            "format": "date-time"
          },
          "created_at": {
            "type": "string",
            "format": "date-time"
          },
          "is_document_expired": {
            "type": "boolean",
            "description": "Indica si el documento ha expirado."
          },
          "is_expired_date": {
            "type": "boolean"
          },
          "is_unique_code": {
            "type": "boolean"
          },
          "expired_date": {
            "type": "string",
            "format": "date-time",
            "description": "Fecha de expiración real del documento."
          },
          "unique_code": {
            "type": "string",
            "description": "Código único asociado al documento."
          },
          "is_uploaded": {
            "type": "integer",
            "format": "int32",
            "description": "Indicador binario de si la imagen está subida (1=sí)."
          },
          "document_picture": {
            "type": "string",
            "description": "Ruta de la imagen del documento."
          },
          "option": {
            "type": "integer"
          },
          "name": {
            "type": "string",
            "description": "Nombre o tipo del documento (ej. Photo_ID)."
          }
        }
      },
      "SuccessResponse": {
        "type": "object",
        "properties": {
          "success": {
            "type": "boolean",
            "enum": [
              true
            ]
          },
          "message": {
            "type": "string",
            "description": "Código de mensaje o estado de éxito."
          },
          "userdocument": {
            "type": "array",
            "items": {
              "$ref": "#/components/schemas/UserDocument"
            }
          }
        },
        "required": [
          "success",
          "userdocument"
        ]
      },
      "ErrorResponse": {
        "type": "object",
        "properties": {
          "success": {
            "type": "boolean",
            "enum": [
              false
            ]
          },
          "error_code": {
            "type": "string",
            "description": "Código de error específico."
          }
        },
        "required": [
          "success",
          "error_code"
        ]
      }
    }
  }
}


```

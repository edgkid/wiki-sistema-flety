### Consulta de Documentos de Proveedor

```json

{
  "openapi": "3.0.0",
  "info": {
    "title": "Provider Document Management API - get Document",
    "description": "API para la consulta de documentos cargados por proveedores.",
    "version": "1.0.0"
  },
  "servers": [
    {
      "url": "{{URL}}",
      "description": "Servidor base"
    }
  ],
  "paths": {
    "/getproviderdocument": {
      "post": {
        "tags": [
          "Documentos"
        ],
        "summary": "Obtener documentos del proveedor",
        "description": "Recupera la lista de documentos asociados a un proveedor específico mediante su ID y token de autenticación.",
        "requestBody": {
          "required": true,
          "content": {
            "multipart/form-data": {
              "schema": {
                "$ref": "#/components/schemas/GetDocumentRequest"
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "Lista de documentos obtenida con éxito.",
            "content": {
              "application/json": {
                "schema": {
                  "$ref": "#/components/schemas/GetDocumentResponse"
                }
              }
            }
          },
          "401": {
            "description": "No autorizado - Token inválido o expirado."
          },
          "404": {
            "description": "No encontrado - El proveedor o sus documentos no existen."
          }
        }
      }
    }
  },
  "components": {
    "schemas": {
      "GetDocumentRequest": {
        "type": "object",
        "required": [
          "provider_id",
          "token"
        ],
        "properties": {
          "provider_id": {
            "type": "string",
            "description": "Identificador único del proveedor.",
            "example": "{{PROVIDER_ID}}"
          },
          "token": {
            "type": "string",
            "description": "Token de seguridad del proveedor.",
            "example": "{{PROVIDER_TOKEN}}"
          }
        }
      },
      "GetDocumentResponse": {
        "type": "object",
        "properties": {
          "success": {
            "type": "boolean",
            "example": true
          },
          "message": {
            "type": "string",
            "description": "Código de mensaje o contador.",
            "example": "47"
          },
          "providerdocument": {
            "type": "array",
            "items": {
              "$ref": "#/components/schemas/ProviderDocument"
            }
          }
        }
      },
      "ProviderDocument": {
        "type": "object",
        "properties": {
          "_id": {
            "type": "string",
            "example": "61979073da10546535a80fc2"
          },
          "provider_id": {
            "type": "string",
            "example": "61979073da10546535a80fc1"
          },
          "document_id": {
            "type": "string",
            "example": "60239647d51a7042436be462"
          },
          "__v": {
            "type": "integer",
            "example": 0
          },
          "updated_at": {
            "type": "string",
            "format": "date-time",
            "example": "2021-11-19T11:54:27.114Z"
          },
          "created_at": {
            "type": "string",
            "format": "date-time",
            "example": "2021-11-19T11:54:27.114Z"
          },
          "is_document_expired": {
            "type": "boolean",
            "example": false
          },
          "is_expired_date": {
            "type": "boolean",
            "example": true
          },
          "is_unique_code": {
            "type": "boolean",
            "example": true
          },
          "expired_date": {
            "type": "string",
            "format": "date-time",
            "example": "2021-11-30T23:59:00.197Z"
          },
          "unique_code": {
            "type": "string",
            "example": "1234"
          },
          "is_uploaded": {
            "type": "integer",
            "example": 1
          },
          "document_picture": {
            "type": "string",
            "description": "Ruta relativa a la imagen del documento.",
            "example": "provider_document/61979073da10546535a80fc2A0Zd.jpg"
          },
          "option": {
            "type": "integer",
            "example": 0
          },
          "name": {
            "type": "string",
            "example": "Provider_ID"
          }
        }
      }
    }
  }
}

```

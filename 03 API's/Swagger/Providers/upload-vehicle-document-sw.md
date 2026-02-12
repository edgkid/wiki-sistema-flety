### Cargar Documentación de Vehículos

```json
{
  "openapi": "3.0.0",
  "info": {
    "title": "Vehicle Document API",
    "description": "API para la carga  de documentos de vehículos.",
    "version": "1.0.0"
  },
  "paths": {
    "/upload_vehicle_document": {
      "post": {
        "summary": "Subir documento de vehículo",
        "description": "Permite cargar un documento físico (imagen) y registrar sus metadatos como fecha de expiración y código único.",
        "requestBody": {
          "required": true,
          "content": {
            "multipart/form-data": {
              "schema": {
                "$ref": "#/components/schemas/UploadDocumentRequest"
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
      "UploadDocumentRequest": {
        "type": "object",
        "properties": {
          "provider_id": {
            "type": "string",
            "example": "{{PROVIDER_ID}}"
          },
          "token": {
            "type": "string",
            "example": "{{PROVIDER_TOKEN}}"
          },
          "document_id": {
            "type": "string",
            "example": "61979c72e096a97e07f0df07"
          },
          "unique_code": {
            "type": "string",
            "example": "1111"
          },
          "vehicle_id": {
            "type": "string",
            "example": "61979c72e096a97e07f0df06"
          },
          "expired_date": {
            "type": "string",
            "format": "date-time",
            "example": "2021-11-30T23:59:00.119Z"
          },
          "pictureData": {
            "type": "string",
            "format": "binary",
            "description": "Archivo de imagen del documento"
          }
        },
        "required": [
          "provider_id",
          "token",
          "document_id",
          "vehicle_id",
          "pictureData"
        ]
      },
      "UploadDocumentResponse": {
        "type": "object",
        "properties": {
          "success": {
            "type": "boolean"
          },
          "document_detail": {
            "type": "object",
            "properties": {
              "_id": { "type": "string" },
              "vehicle_id": { "type": "string" },
              "provider_id": { "type": "string" },
              "document_id": { "type": "string" },
              "__v": { "type": "integer" },
              "updated_at": { "type": "string", "format": "date-time" },
              "created_at": { "type": "string", "format": "date-time" },
              "is_document_expired": { "type": "boolean" },
              "is_expired_date": { "type": "boolean" },
              "is_unique_code": { "type": "boolean" },
              "expired_date": { "type": "string", "format": "date-time" },
              "unique_code": { "type": "string" },
              "is_uploaded": { "type": "integer" },
              "document_picture": { "type": "string" },
              "option": { "type": "integer" },
              "name": { "type": "string" }
            }
          }
        }
      }
    }
  }
}

```

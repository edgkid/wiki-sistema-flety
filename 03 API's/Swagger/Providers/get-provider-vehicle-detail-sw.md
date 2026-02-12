### Detalle Vehículo Proveedor

```json
{
  "openapi": "3.0.0",
  "info": {
    "title": "Provider Vehicle API",
    "description": "API para la gestión y consulta de detalles de vehículos de proveedores.",
    "version": "1.0.0"
  },
  "paths": {
    "/get_provider_vehicle_detail": {
      "post": {
        "summary": "Obtener detalles del vehículo del proveedor",
        "description": "Retorna la información técnica,  lista de documentos asociados a un vehículo específico.",
        "requestBody": {
          "required": true,
          "content": {
            "application/json": {
              "schema": {
                "$ref": "#/components/schemas/VehicleRequest"
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "Operación exitosa",
            "content": {
              "application/json": {
                "schema": {
                  "$ref": "#/components/schemas/VehicleResponse"
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
      "VehicleRequest": {
        "type": "object",
        "properties": {
          "provider_id": {
            "type": "string",
            "example": "61979073da10546535a80fc1"
          },
          "token": {
            "type": "string",
            "example": "PROVIDER_TOKEN_EXAMPLE"
          },
          "vehicle_id": {
            "type": "string",
            "example": "61979c72e096a97e07f0df06"
          }
        },
        "required": ["provider_id", "token", "vehicle_id"]
      },
      "VehicleResponse": {
        "type": "object",
        "properties": {
          "success": {
            "type": "boolean"
          },
          "vehicle_detail": {
            "type": "object",
            "properties": {
              "is_document_uploaded": { "type": "boolean" },
              "is_selected": { "type": "boolean" },
              "is_documents_expired": { "type": "boolean" },
              "admin_type_id": { "type": "string", "nullable": true },
              "service_type": { "type": "string", "nullable": true },
              "passing_year": { "type": "string" },
              "color": { "type": "string" },
              "model": { "type": "string" },
              "plate_no": { "type": "string" },
              "accessibility": {
                "type": "array",
                "items": { "type": "string" }
              },
              "name": { "type": "string" },
              "_id": { "type": "string" },
              "type_image_url": { "type": "string" }
            }
          },
          "document_list": {
            "type": "array",
            "items": {
              "$ref": "#/components/schemas/Document"
            }
          }
        }
      },
      "Document": {
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
          "expired_date": { "type": "string", "nullable": true },
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

```

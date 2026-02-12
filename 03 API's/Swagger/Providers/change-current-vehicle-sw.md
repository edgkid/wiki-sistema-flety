### Actualizar Vehículo Activo de Proveedor

```json
{
  "openapi": "3.0.0",
  "info": {
    "title": "Vehicle Management API",
    "description": "API para Actualiza el vehículo activos de proveedores.",
    "version": "1.0.0"
  },
  "paths": {
    "/change_current_vehicle": {
      "post": {
        "summary": "Cambiar vehículo actual",
        "description": "Actualiza el vehículo activo para el proveedor especificado.",
        "requestBody": {
          "required": true,
          "content": {
            "application/json": {
              "schema": {
                "$ref": "#/components/schemas/ChangeVehicleRequest"
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "Cambio realizado con éxito",
            "content": {
              "application/json": {
                "schema": {
                  "$ref": "#/components/schemas/SimpleSuccessResponse"
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
      "ChangeVehicleRequest": {
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
          "vehicle_id": {
            "type": "string",
            "example": "61979c72e096a97e07f0df06"
          }
        },
        "required": [
          "provider_id",
          "token",
          "vehicle_id"
        ]
      },
      "SimpleSuccessResponse": {
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
}
```

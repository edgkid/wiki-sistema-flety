
### Dirección de Usuario

```json

{
  "openapi": "3.0.3",
  "info": {
    "title": "Set Home Address API",
    "version": "1.0.0"
  },
  "paths": {
    "/set_home_address": {
      "post": {
        "summary": "Establecer dirección de casa y trabajo",
        "requestBody": {
          "required": true,
          "content": {
            "application/json": {
              "schema": {
                "type": "object",
                "properties": {
                  "user_id": {
                    "type": "string",
                    "example": "{{USER_ID}}"
                  },
                  "token": {
                    "type": "string",
                    "example": "{{USER_TOKEN}}"
                  },
                  "home_address": {
                    "type": "string",
                    "example": "Rajkot"
                  },
                  "home_latitude": {
                    "type": "number",
                    "format": "double",
                    "example": 22.285966470985127
                  },
                  "home_longitude": {
                    "type": "number",
                    "format": "double",
                    "example": 70.7709223249316
                  },
                  "work_address": {
                    "type": "string",
                    "example": "Rajkot"
                  },
                  "work_latitude": {
                    "type": "number",
                    "format": "double",
                    "example": 22.3039
                  },
                  "work_longitude": {
                    "type": "number",
                    "format": "double",
                    "example": 70.8022
                  }
                },
                "required": [
                  "user_id",
                  "token",
                  "home_address",
                  "home_latitude",
                  "home_longitude",
                  "work_address",
                  "work_latitude",
                  "work_longitude"
                ]
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "Respuesta exitosa al establecer dirección",
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
                      "example": "98"
                    }
                  },
                  "required": [
                    "success",
                    "message"
                  ]
                }
              }
            }
          }
        }
      }
    }
  }
}


```

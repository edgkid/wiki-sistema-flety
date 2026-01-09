Esta sección tiene como objetivo principal servir de referencia técnica y funcional completa de las interfaces de programación de aplicaciones (API) del proyecto.

Dada la arquitectura subyacente del sistema, y para mayor compresión y orden de todos los elementos existentes actualmente, la documentación se enfocó en un esquema de  microservicios en lugar de una estructura monolítica y se ha optado por documentar cada endpoint de forma individual.

Para lograr una descripción clara y estandarizada, se utiliza la especificación OpenAPI 3.0.0 (anteriormente conocida como Swagger). Esta especificación permite definir de manera precisa la superficie de cada API, incluyendo todos los endpoints, modelos de datos, parámetros y respuestas a fin de facilitar la integración, el desarrollo y el mantenimiento de todos los servicios existentes.
#### Descripción General de encabezado de  API´s

|                       |                                         |
| --------------------- | --------------------------------------- |
| Path:                 | {IP:Puerto}/<EndPoint de microservicio> |
| Versión del Contrato: | 1.0                                     |
| Estatus:              | Documentación Open API 3                |
| Alcance:              | Documentación                           |
| Tipo:                 | Microservicio                           |
| Protocolo             | REST                                    |

####Definición general de los servicios

Estructura general formato open API 3

{

  "openapi": "3.0.0",

  "info": {

    "title": "Definicion de nombre de la API",

    "version": "1.0.0",

    "description": "Descripcion funcional de la API."

  },

  "servers": [

    {

      "url": "https://api.ejemplo.com:443/v1",

      "description": "Servidor principal de la API"

    }

  ],

  "paths": {

    "/endpoint/ejemplo": {

      "post": {

        "summary": "Resumen de la API.",

        "operationId": "identificador de la API",

        "tags": [

          "listado tag del servicio"

        ],

        "requestBody": {

          "required": true,

          "content": {

            "application/json": {

              "schema": {

                "$ref": "#/components/schemas/TypeListRequest"

              },

              "example": {

                "campoA": "valor",

                "CampoB": "valor",

                .

                .

                .

                .

                "campo N": "valor"

              }

            }

          }

        },

        "responses": {

          "200": {

            "description": "Descripcion de la respueta obtenida bajo el codigo de respuesta Http 200 OK.",

            "content": {

              "application/json": {

                "schema": {

                  "$ref": "#/components/schemas/TypeListResponse"

                },

                "example": {

                  "success": true,

                  "message": "63",

                  "campoA": "valor",

                  "campoB": "valor",

                  .

                  .

                  .

                  .

                  "campoN": "valor"

                }

              }

            }

          },

          "400": {

            "message": "Descripcion del mensaje de error."

            "code": "<codigo definido de error>"

            "success": false

          }

        }

      }

    }

  },

  "components": {

    "schemas": {

      "TypeListRequest": {

        "type": "object",

        "properties": {

          "campoA": {

            "type": "string",

            "description": "descripcion del tipo de cada campo"

          },

          .

          .

          .

          "campoN": {

            "type": "string",

            "description": "descripcion del tipo de cada campo"

          },

        },

        "required": [

          "campoA",

          "campoB",

          .

          .

          .

          "campoN"

        ]

      },

      "campoA": {

        "type": "object",

        "properties": {

          "_id": {

            "type": "string"

          },

          "campoB": {

            "type": "string"

          },

        .

        .

        .

        .

      "campoN": {

        "type": "object",

        "properties": {

          "success": {

            "type": "boolean",

            "description": "Indica si la solicitud fue exitosa."

          },

          "message": {

            "type": "string",

            "description": "Mensaje de error del servidor."

          },

        },

        "required": [

          "success",

          "campoA",

          "campoB",

          .

          .

          .

          "campoN"

        ]

      }

    }

  }

}

Nota: Cada definición de servicio podrá ser encontrada en la dentro del directorio swagger de los insumos que se entreguen como parte de la documentación de las condiciones actuales del proyecto.

Las Respuesta de error está siendo manejadas de la siguiente manera; dentro del cuerpo del response, según código de error se cuenta con el siguiente objeto:

![](data:image/png;base64,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)

### Catálogo de Endpoints (Swagger)

A continuación se detallan las especificaciones técnicas de los endpoints disponibles:

* [🔐 Ver Swagger: Autenticación de Usuario (Login)](03%20API's/Login%20Swagger.md)
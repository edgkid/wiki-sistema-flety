# Archivo: `Service_Type.js`

## Descripción General
Este controlador gestiona las categorías de vehículos y servicios de la plataforma. 

---

## Funciones del Controlador

### Gestión de Catálogo

| Función             | Tipo  | Entrada                 | Salida     | Descripción                                                     |
| :------------------ | :---- | :---------------------- | :--------- | :-------------------------------------------------------------- |
| `service_types`     | Sync  | `req.body.search_value` | Vista HTML | Lista los tipos de servicios existentes                         |
| `add_service_form`  | Async | N/A                     | Vista HTML | Renderiza el formulario para crear un nuevo tipo de servicio    |
| `edit_service_form` | Async | `req.body.id`           | Vista HTML | Carga la información de un servicio específico para su edición. |

### Operaciones 

| Función                 | Tipo | Entrada                 | Salida      | Descripción                         |
| :---------------------- | :--- | :---------------------- | :---------- | :---------------------------------- |
| `add_service_detail`    | Sync | `req.body`, `req.files` | Redirección | Crea un nuevo registro de servicio. |
| `update_service_detail` | Sync | `req.body`, `req.files` | Redirección | Actualiza los datos                 |

### Validaciones de Negocio
| Función                         | Tipo  | Entrada             | Salida | Descripción                                                                    |
| :------------------------------ | :---- | :------------------ | :----- | :----------------------------------------------------------------------------- |
| `check_type_available`          | Sync  | `req.body.typename` | JSON   | Valida si un nombre de servicio ya existe .                                    |
| `check_type_sequence_available` | Async | `req.body.sequence` | JSON   | Comprueba si un número de orden en la lista ya está ocupado por otro servicio. |
| `check_type_priority_available` | Sync  | `req.body.priority` | JSON   |                                                                                |

### Consumo Interno
| Función                  | Tipo  | Entrada              | Salida | Descripción                                                                |
| :----------------------- | :---- | :------------------- | :----- | :------------------------------------------------------------------------- |
| `fetch_servicetype_list` | Async | `req.body.countryid` | JSON   | Retorna todos los tipos de servicios configurados para un país específico. |
| `fetch_corporate_list`   | Async | `req.body.countryid` | JSON   |                                                                            |
| `fetch_truck_type_list`  | Async | N/A                  | JSON   | Devuelve listas de modelos, servicios y capacidades para un servicio       |
| `type_list`              | Sync  | N/A                  | JSON   |                                                                            |
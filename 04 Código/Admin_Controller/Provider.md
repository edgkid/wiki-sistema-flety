# Archivo: `provider.js`

## Descripción General
Este archivo contiene la lógica para el control de ciclo de vida del proveedor. 

---

## Funciones del Controlador

### 1. Reportes y Gestión de Referidos
| Función | Tipo | Entrada | Descripción |
| :--- | :--- | :--- | :--- |
| `referral_report` | Async | `req.session` | Genera un reporte de los proveedores que han referido a otros usuarios. |
| `referral_history` | Async | `provider_id` | Muestra el historial detallado de ganancias por referidos de un proveedor. |

### 2. Administración de Perfil y Listados
| Función                         | Tipo  | Entrada        | Descripción                                                                      |
| :------------------------------ | :---- | :------------- | :------------------------------------------------------------------------------- |
| `list`                          | Async | Filtros        | Lista principal de todos los proveedores                                         |
| `edit`                          | Async | `id`           | Carga el formulario con los datos de un proveedor para su modificación.          |
| `update`                        | Async | `req.body`     | Procesa y guarda los cambios realizados en el perfil del proveedor.              |
| `profile_is_approved`           | Sync  | `id`, `status` | Cambia el estado de aprobación del perfil                                        |
| `update_profile_approve_status` | Sync  | `id`           | Actualiza el flag de aprobación tras validar que los documentos están correctos. |
| `unfreeze_provider`             | Async | `id`           | Desbloquea a un proveedor que ha sido suspendido automáticamente.                |
| `admin_delete_provider`         | Sync  | `id`           | Elimina al proveedor                                                             |

### 3. Gestión Documental del Proveedor
| Función                     | Tipo  | Entrada     | Descripción                                                       |
| :-------------------------- | :---- | :---------- | :---------------------------------------------------------------- |
| `documents`                 | Sync  | `id`        | Lista los documentos cargados por el proveedor                    |
| `provider_documents_edit`   | Sync  | `doc_id`    | Carga la interfaz para revisar o editar un documento específico.  |
| `provider_documents_update` | Async | `req.files` | Sube y actualiza el archivo físico de un documento del proveedor. |
| `provider_documents_delete` | Async | `doc_id`    | Elimina un documento del perfil del proveedor.                    |

### 4. Gestión de Flota y Vehículos
| Función                        | Tipo   | Entrada       | Descripción                                                           |
| :----------------------------- | :----- | :------------ | :-------------------------------------------------------------------- |
| `provider_vehicle_list`        | Sync   | `provider_id` | Muestra todos los vehículos registrados por un conductor.             |
| `add_provider_vehicle`         | Render | N/A           | Renderiza la vista para añadir un nuevo vehículo al sistema.          |
| `add_provider_vehicle_data`    | Async  | `req.body`    | Registra un nuevo vehículo vinculándolo al ID del proveedor.          |
| `delete_vehicle_detail`        | Sync   | `vehicle_id`  | Elimina un vehículo y sus documentos                                  |
| `edit_vehicle_detail`          | Sync   | `vehicle_id`  | Carga los datos técnicos de un vehículo para edición (placa, modelo). |
| `update_vehicle_detail`        | Sync   | `req.body`    | Guarda los cambios técnicos realizados sobre un vehículo.             |
| `update_provider_vehicle_type` | Async  | `type_id`     | Cambia la categoría de servicio del vehículo                          |
| `available_type`               | Sync   | `city_id`     | Retorna los tipos de vehículos disponibles                            |

### 5. Documentación de Vehículos
| Función                             | Tipo  | Entrada      | Descripción                                                |
| :---------------------------------- | :---- | :----------- | :--------------------------------------------------------- |
| `vehicle_document_list`             | Sync  | `vehicle_id` | Lista los documentos específicos de un vehículo            |
| `provider_vehicle_documents_edit`   | Sync  | `doc_id`     | Interfaz para editar documentos vinculados al vehículo.    |
| `provider_vehicle_documents_update` | Async | `req.files`  | Actualiza el archivo de imagen del documento del vehículo. |

### 6. Finanzas y Actividad
| Función                       | Tipo  | Entrada       | Descripción                                                                       |
| :---------------------------- | :---- | :------------ | :-------------------------------------------------------------------------------- |
| `history`                     | Async | `provider_id` | Muestra el historial completo de viajes realizados por el conductor.              |
| `admin_add_provider_wallet`   | Async | `amount`      | Permite al admin añadir o quitar saldo manualmente de la billetera del conductor. |
| `admin_get_provider_partners` | Async | `provider_id` | Retorna la lista de socios (partners) asociados a ese conductor.                  |

### 7. Utilidades y Exportación
| Función                           | Tipo    | Entrada         | Descripción                                                             |
| :-------------------------------- | :------ | :-------------- | :---------------------------------------------------------------------- |
| `generate_provider_excel`         | Async   | Filtros         | Prepara los datos para la exportación masiva de proveedores a Excel.    |
| `generate_excel`                  | Interna | Array, Timezone | Exporta datos en archivo `.xlsx`.                                       |
| `generate_provider_history_excel` | Sync    | `filters`       | Exporta el historial de viajes de un conductor específico a Excel.      |
| `providerListSearchQueries`       | Interna | Name, Item      | Construye las queries de búsqueda para filtrar la lista de proveedores. |
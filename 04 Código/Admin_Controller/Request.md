# Archivo: `Request.js`

## Descripción General
Este controlador se encarga de la gestión, supervisión y corrección de las solicitudes de viajes. 

---

## Funciones del Controlador

### 1. Gestión de Vistas
| Función                   | Tipo  | Entrada              | Salida     | Descripción                                                                          |
| :------------------------ | :---- | :------------------- | :--------- | :----------------------------------------------------------------------------------- |
| `list`                    | Async | `req.body` (filtros) | Vista HTML | Recupera y muestra la lista de solicitudes activas                                   |
| `admin_incoming_requests` | Async | `req.session`        | Vista HTML | Filtra y muestra solo las solicitudes que están en proceso de búsqueda de conductor. |
| `history`                 | Async | `req.body` (filtros) | Vista HTML | Consulta la colección `Trip_history` para mostrar viajes finalizados o cancelados.   |
| `trip_map`                | Async | `req.body.id`        | Vista HTML | Carga la interfaz de mapa con la ruta                                                |
| `other_user_track_trip`   | Async | `req.body.id`        | Vista HTML | Genera una vista de rastreo público para seguir el progreso del viaje .              |

### 2. Operaciones 

| Función               | Tipo  | Entrada            | Salida      | Descripción                                                                       |
| :-------------------- | :---- | :----------------- | :---------- | :-------------------------------------------------------------------------------- |
| `admin_complete_trip` | Async | `req.body.id`      | Redirección | Cierra  un viaje, calcula costos y lo mueve al historial.                         |
| `reset_trip_status`   | Async | `req.body.id`      | Redirección | Reinicia los flags de un viaje al estado inicial para permitir un nuevo despacho. |
| `trip_refund_amount`  | Sync  | `req.body` (monto) | Redirección | Ejecuta la devolución de un monto a la billetera del usuario                      |
| `delete_pod`          | Async | `req.body.id`      | Redirección |                                                                                   |
| `admin_add_note`      | Async | `trip_id`, `note`  | Redirección | Inserta un comentario u observación administrativa en el expediente del viaje.    |
| `admin_delete_note`   | Async | `trip_id`, `id`    | Redirección | Remueve una nota administrativa previamente guardada en el viaje.                 |

### 3. Asignación 

| Función                    | Tipo  | Entrada           | Salida      | Descripción                                                          |
| :------------------------- | :---- | :---------------- | :---------- | :------------------------------------------------------------------- |
| `get_partner_for_trip`     | Async | `req.body.id`     | JSON        | Busca asociado cuya área operativa coincida con el origen del viaje. |
| `assign_trip_to_partner`   | Async | `trip_id`, `p_id` | Redirección | Vincula una solicitud a un asociado                                  |
| `unassign_trip_to_partner` | Async | `req.body.id`     | Redirección | Elimina la vinculación con un asociado                               |

### 4. Gestion de Status de Viaje

| Función                        | Tipo  | Entrada       | Salida | Descripción                                             |
| :----------------------------- | :---- | :------------ | :----- | :------------------------------------------------------ |
| `requsest_status_ajax`         | Sync  | `req.body.id` | JSON   | Retorna el estado numérico y datos básicos de un viaje. |
| `change_trip_paid_status`      | Async | `req.body`    | JSON   | Actualiza el estado de pago de viajes .                 |
| `admin_change_preqliuidation`  | Async | `req.body`    | JSON   |                                                         |
| `admin_get_provider_documents` | Async | `req.body.id` | JSON   | Obtiene los documentos del conductor asignado           |

### 5. Utilitarios

| Función                  | Tipo    | Entrada    | Salida        | Descripción                                                                  |
| :----------------------- | :------ | :--------- | :------------ | :--------------------------------------------------------------------------- |
| `getSearchParams`        | Interna | `req`      | Objeto        | Extrae y limpia parámetros de búsqueda, ordenamiento y fechas.               |
| `getStatusCondition`     | Interna | `status`   | Query Obj     | Traduce el nombre del estado (                                               |
| `getDateTypeQuery`       | Interna | `type`     | String        | Determina si el filtro de fecha aplica a la creación o al inicio del viaje.  |
| `genetare_request_excel` | Async   | `req.body` | Archivo Excel | Procesa los datos de las solicitudes y genera un reporte en formato `.xlsx`. |

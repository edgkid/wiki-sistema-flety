# Archivo: `inbox_notifications.js`

## Descripción General
Este controlador administra las Notificaciones de Bandeja de Entrada, permite que los administradores envíen mensajes directos, avisos o alertas. a través del presente controlador se  permite crear mensajes masivos o específicos, listar las notificaciones enviadas con soporte para búsqueda avanzada y gestionar la eliminación de las mismas.

---

## Funciones del Controlador

### Gestión de Mensajería y Vistas
| Función                     | Tipo   | Entrada                | Salida      | Descripción                                                                                                              |
| :-------------------------- | :----- | :--------------------- | :---------- | :----------------------------------------------------------------------------------------------------------------------- |
| `inbox_notifications`       | Async  | `req.session`, filtros | Vista HTML  | Renderiza la lista principal de notificaciones enviadas.                                                                 |
| `add_inbox_notifications`   | Render | N/A                    | Vista HTML  | Muestra el formulario administrativo para redactar y configurar una nueva notificación (Asunto, Mensaje, Destinatarios). |
| `create_inbox_notification` | Async  | `req.body` (mensaje)   | Redirección | Procesa y guarda la nueva notificación en la base de datos                                                               |
| `delete_inbox_notification` | Async  | `req.body.id`          | JSON        | Elimina una notificación específica                                                                                      |

### Segmentación de Destinatarios
| Función                       | Tipo  | Entrada               | Salida | Descripción                                                                                    |
| :---------------------------- | :---- | :-------------------- | :----- | :--------------------------------------------------------------------------------------------- |
| `get_partners_and_corporates` | Async | `req.body.country_id` | JSON   | Retorna la lista de usuarios asociados a un país para facilitar la selección de destinatarios. |

### Utilidades de Búsqueda y Filtrado (Lógica Interna)
| Función             | Tipo    | Entrada         | Salida         | Descripción                                                                                 |
| :------------------ | :------ | :-------------- | :------------- | :------------------------------------------------------------------------------------------ |
| `getSearchParams`   | Interna | `req`           | Objeto         | Extrae y limpia los parámetros de búsqueda  de la solicitud HTTP.                           |
| `getSearchHandlers` | Interna | `value`         | Objeto         | Define como filtrar las notificaciones por contenido de mensaje u otros campos específicos. |
| `handleSearch`      | Interna | `item`, `value` | Objeto (Query) | Genera dinámicamente el objeto de consulta para MongoDB .                                   |
| `handleDateFilter`  | Interna | `start`, `end`  | Objeto (Query) | Construye el filtro de rango de fechas para limitar los resultados a un periodo de tiempo   |
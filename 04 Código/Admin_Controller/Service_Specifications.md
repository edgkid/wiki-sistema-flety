# Archivo: `Service_Specifications.js`

## Descripción General
Este controlador gestiona las especificaciones de servicio, que actúan como atributos o características adicionales asignables a los vehículos.

---

## Funciones del Controlador

| Función                                | Tipo  | Entrada              | Salida        | Descripción                                                                                  |
| :------------------------------------- | :---- | :------------------- | :------------ | :------------------------------------------------------------------------------------------- |
| `service_specification_list`           | Async | `req.body` (filtros) | Vista HTML    | Recupera y muestra la lista completa de especificaciones registradas.                        |
| `generate_service_specification_excel` | Async | `req.body` (filtros) | Archivo Excel | Exporta el catálogo de especificaciones de servicio a un archivo `.xlsx`                     |
| `edit`                                 | Async | `req.body.id`        | Vista HTML    | Busca una especificación por su ID y carga el formulario para modificar sus datos actuales.  |
| `update`                               | Async | `req.body` (datos)   | Redirección   | Procesa y guarda los cambios realizados en una especificación existente en la base de datos. |
| `act`                                  | Async | `id`, `state`        | Redirección   | Alterna el esattus de activación de una especificación para habilitarla o no en la app.      |
| `add_service_specification_form`       | Sync  | N/A                  | Vista HTML    | Renderiza el formulario en blanco para la creación de una nueva especificación de servicio.  |
| `add_service_specification`            | Async | `req.body` (nombre)  | Redirección   | Registra una nueva especificación en el sistema                                              |
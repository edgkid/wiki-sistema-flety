# Archivo: `Type_Services.js`

## Descripción General
Este controlador gestiona el catálogo de tipos de servicios t

---

## Funciones del Controlador

### 1. Gestión de Datos

| Función                 | Tipo  | Entrada              | Salida     | Descripción                                                                                              |
| :---------------------- | :---- | :------------------- | :--------- | :------------------------------------------------------------------------------------------------------- |
| `type_service_list`     | Async | `req.body` (filtros) | Vista HTML | Recupera y muestra el listado de servicios                                                               |
| `add_type_service_form` | Async | N/A                  | Vista HTML | Renderiza el formulario de creación                                                                      |
| `edit`                  | Async | `req.body.id`        | Vista HTML | Carga los datos de un servicio y la lista de especificaciones disponibles para permitir su modificación. |

| `add_type_service` | Async | `req.body` (nombre) | Redirección | Registra un nuevo tipo de servicio            |
| :----------------- | :---- | :------------------ | :---------- | :-------------------------------------------- |
| `update`           | Async | `req.body` (datos)  | Redirección | Guarda los cambios realizados en un servicio, |
| `act`              | Async | `id`, `state`       | Redirección | Modifica el estatus  de un servicio           |

### 3. Reportes 

| Función                       | Tipo  | Entrada              | Salida        | Descripción                                                               |
| :---------------------------- | :---- | :------------------- | :------------ | :------------------------------------------------------------------------ |
| `generate_type_service_excel` | Async | `req.body` (filtros) | Archivo Excel | Procesa el catálogo de servicios  y genera un reporte en formato `.xlsx`. |
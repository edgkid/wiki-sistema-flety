# Archivo: `Type_Capacity.js`

## Descripción General
Este controlador gestiona la capacidad de carga de los vehículos. 

---

## Funciones del Controlador

### 1. Gestión de Catálogo de Capacidades

| Función                  | Tipo  | Entrada              | Salida     | Descripción                                                                    |
| :----------------------- | :---- | :------------------- | :--------- | :----------------------------------------------------------------------------- |
| `type_capacity_list`     | Async | `req.body` (filtros) | Vista HTML | Recupera y muestra el listado de capacidades registradas                       |
| `add_type_capacity_form` | Sync  | N/A                  | Vista HTML | Renderiza el formulario en blanco para registrar una nueva capacidad de carga. |
| `edit`                   | Async | `req.body.id`        | Vista HTML | Carga el formulario de edición con los detalles de una capacidad específica    |

### 2. Operaciones de  Persistencia
| Función             | Tipo  | Entrada            | Salida      | Descripción                                                     |
| :------------------ | :---- | :----------------- | :---------- | :-------------------------------------------------------------- |
| `add_type_capacity` | Async | `req.body`         | Redirección | Registra una nueva capacidad.                                   |
| `update`            | Async | `req.body` (datos) | Redirección | Guarda las modificaciones realizadas en una capacidad existente |
| `act`               | Async | `id`, `state`      | Redirección | Para modificar estatus de una capacidad específica.             |

### 3. Reportes

| Función                        | Tipo  | Entrada              | Salida        | Descripción                                                                |
| :----------------------------- | :---- | :------------------- | :------------ | :------------------------------------------------------------------------- |
| `generate_type_capacity_excel` | Async | `req.body` (filtros) | Archivo Excel | Procesa las capacidades filtradas y genera un reporte  en formato `.xlsx`. |

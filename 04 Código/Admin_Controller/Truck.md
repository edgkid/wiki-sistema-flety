# Archivo: `Truck.js`

## Descripción General
Este controlador permite la gestión de la flota de vehículos.

---

## Funciones del Controlador

### 1. Supervisión de Flota
| Función | Tipo | Entrada | Salida | Descripción |
| :--- | :--- | :--- | :--- | :--- |
| `truck_list` | Async | `req.body` (filtros) | Vista HTML | Recupera el listado completo de camiones con información del propietario, modelo y estado de aprobación. |
| `admin_get_vehicle_docs` | Async | `req.body.id` | JSON | Consulta y retorna la lista de documentos (seguros, revisiones) asociados específicamente al vehículo. |

### 2. Control Operativo y Edición
| Función | Tipo | Entrada | Salida | Descripción |
| :--- | :--- | :--- | :--- | :--- |
| `admin_change_vehicle_status`| Async | `id`, `is_approved` | JSON | Activa o desactiva la aprobación de un vehículo. Si se desactiva, el conductor no puede recibir servicios. |
| `admin_edit_vehicle_detail` | Sync | `req.body.id` | Vista HTML | Carga el formulario de edición con los datos técnicos actuales del vehículo y del conductor asociado. |
| `admin_update_vehicle_detail` | Async | `req.body` (datos) | Redirección | Guarda los cambios realizados en la información del vehículo (placa, modelo, año) en la base de datos. |

### 3. Reportes y Utilidades
| Función | Tipo | Entrada | Salida | Descripción |
| :--- | :--- | :--- | :--- | :--- |
| `generate_trucks_excel` | Async | `req.body` (filtros) | Archivo Excel | Procesa la lista de camiones según los filtros aplicados y dispara la generación del reporte `.xlsx`. |
| `generate_excel` | Interna | `array`, `cities` | Archivo Excel | **Utilidad:** Función auxiliar que construye la estructura del archivo Excel y lo escribe en el almacenamiento temporal. |
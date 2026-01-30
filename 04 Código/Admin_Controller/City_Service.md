# Archivo: `city_service.js`

## Descripción General
Este controlador gestiona la lógica de configuración de servicios y tarifas por ciudad. Es la herramienta principal para definir la oferta comercial, estableciendo qué vehículos están disponibles en cada zona y cuáles son sus parámetros de cobro (matriz de precios).

---

## Funciones del Controlador

### Gestión de Vistas y Configuración
| Función | Tipo | Entrada | Salida | Descripción |
| :--- | :--- | :--- | :--- | :--- |
| `city_type` | Async | `country_id`, `city_id` | Vista HTML | Renderiza la interfaz principal donde se listan todos los tipos de servicios vinculados a una ciudad. |
| `add_city_type_form` | Async | `city_id` | Vista HTML | Prepara y muestra el formulario para añadir un nuevo tipo de servicio a una ciudad específica. |
| `add_city_type_detail` | Async | `req.body` | Redirección | Procesa el registro inicial de un nuevo servicio en la ciudad. |
| `edit_city_type` | Async | `req.body.id` | Vista HTML | Carga la configuración completa de un servicio específico para su edición. |
| `update_city_type` | Async | `req.body` (tarifas) | Redirección | Actualiza los valores de precios, parámetros de visibilidad y estado activo/inactivo. |

### API y Consultas de Datos
| Función | Tipo | Entrada | Salida | Descripción |
| :--- | :--- | :--- | :--- | :--- |
| `fetch_city_type` | Async | `city_id` | JSON | Retorna de forma rápida la lista de servicios activos en una ciudad específica. |
| `get_city_service_list` | Async | `city_id`, `corporate_id` | JSON | Filtra y entrega los tipos de servicios disponibles, considerando restricciones para cuentas corporativas. |
| `check_city_type_priority` | Async | `city_id`, `priority` | JSON | Valida que no existan conflictos de prioridad de visualización entre los diferentes servicios de una misma zona. |

### Matriz de Precios

| Función | Tipo | Entrada | Salida | Descripción |
| :--- | :--- | :--- | :--- | :--- |
| `get_modelpricing_data` | Async | `city_type_id` | JSON | Recupera el desglose detallado de la matriz de precios (tarifa base, por km, por minuto, etc.). |
| `add_modelpricing_data` | Async | `req.body` (tarifas) | JSON | Guarda o actualiza la matriz de precios compleja de un servicio específico. |
| `delete_modelpricing_data` | Async | `req.body.id` | JSON | Elimina la configuración de precios y el registro del servicio de la ciudad seleccionada. |
# Archivo: `Map_View.js`

## Descripción General
Este controlador permite proporcionar una vista panorámica del estado de la flota y los viajes. Permite rastrear la ubicación de los proveedores activos, y detalles específicos de un conductor  directamente desde la interfaz del mapa. 

---

## Funciones del Controlador

### Rastreo de Flota
| Función                 | Tipo  | Entrada                  | Salida     | Descripción                                                  |
| :---------------------- | :---- | :----------------------- | :--------- | :----------------------------------------------------------- |
| `map`                   | Async | `req.session.userid`     | Vista HTML | Carga la vista de mapa global inicial                        |
| `provider_track`        | Async | `req.session`            | Vista HTML | Interfaz específica para el rastreo de proveedores,          |
| `fetch_provider_data`   | Async | `req.body` (filtros)     | JSON       | Retorna coordenadas y estados (libre, ocupado, desconectado) |
| `map_get_provider_data` | Async | `trip_id`, `provider_id` | JSON       | Retorna el "info-window" detallado de un conductor:          |

### Monitorización de Viajes Activos
| Función                | Tipo  | Entrada              | Salida     | Descripción                                                                  |
| :--------------------- | :---- | :------------------- | :--------- | :--------------------------------------------------------------------------- |
| `trips_map`            | Async | `req.session.userid` | Vista HTML | Renderiza una vista  para visualizar la distribución de los viajes actuales. |
| `fetch_trip_data`      | Async | `req.body` (filtros) | JSON       | Recupera la ubicación en tiempo real de todos los viajes activos             |
| `fetch_trips_map_data` | Async | `req.body`           | JSON       | Proporciona la información mínima para la renderización de los viajes        |
| `trips_map_view`       | Async | `req.body` (filtros) | Vista/JSON | Procesa actualizaciones de datos para el mapa de viajes                      |
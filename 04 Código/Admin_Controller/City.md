# Archivo: `city.js`

## Descripción General
Este controlador gestiona la creación de ciudades operativas, la delimitación de  coordenadas, la configuración de zonas  y las reglas de negocio financieras (métodos de pago) aplicables por ciudad.

---

## Funciones del Controlador

### Gestión de Vistas y Listados
| Función | Tipo | Entrada | Salida | Descripción |
| :--- | :--- | :--- | :--- | :--- |
| `all_city` | Async | `session.admin` | Vista HTML | Renderiza un mapa global con todas las ciudades activas y su ubicación central. |
| `fetch_all_city` | Async | N/A | JSON | Retorna un listado simple de todas las ciudades con sus coordenadas para uso en mapas. |
| `city` | Async | `filters`, `page` | Vista HTML | Panel administrativo con paginación, búsqueda y filtrado de ciudades por nombre o país. |
| `genetare_city_excel` | Async | `filters` | Archivo .xlsx | Genera un reporte descargable con los datos de ciudades, códigos y estado de negocio. |

### Configuración de Zonas y Valores
| Función | Tipo | Entrada | Salida | Descripción |
| :--- | :--- | :--- | :--- | :--- |
| `zonevalueajax` | Async | `zone1`, `zone2`, `amount` | JSON | Crea una relación de tarifa fija entre dos zonas específicas de una ciudad. |
| `updatezonevalueajax` | Async | `id`, `amount` | JSON | Actualiza los costos, comisiones de socios y cargos adicionales (ayudantes, paradas) de una zona. |
| `deletezonevalueajax` | Async | `id` | JSON | Elimina la configuración de tarifa fija entre zonas. |

### Perímetros y Áreas Geográficas
| Función | Tipo | Entrada | Salida | Descripción |
| :--- | :--- | :--- | :--- | :--- |
| `update_city_zone` | Async | `city_id`, `zone_array`| JSON | Gestiona los polígonos de las zonas de la ciudad (creación, edición y eliminación de KML). |
| `update_city_red_zone` | Async | `city_id`, `red_zone` | JSON | Define áreas de riesgo o restringidas ("Zonas Rojas") mediante coordenadas geográficas. |
| `update_airport` | Async | `city_id`, `airport_data`| JSON | Gestiona los perímetros y la configuración de aeropuertos dentro de la ciudad. |

### Formularios y Detalle de Ciudad
| Función | Tipo | Entrada | Salida | Descripción |
| :--- | :--- | :--- | :--- | :--- |
| `add_city_form` | Async | N/A | Vista HTML | Carga el formulario de creación de ciudad con los métodos de pago disponibles. |
| `edit_city_form` | Async | `id` | Vista HTML | Carga toda la configuración de una ciudad (zonas, aeropuertos, destinos) para edición. |
| `add_city_detail` | Async | `req.body` | Redirección | Procesa el guardado de una nueva ciudad, incluyendo límites perimetrales y reglas de wallet. |
| `update_city_detail` | Async | `req.body` | Redirección | Actualiza la configuración de negocio, zonas de destino y parámetros operativos de la ciudad. |

### Servicios de Interconexión y API
| Función | Tipo | Entrada | Salida | Descripción |
| :--- | :--- | :--- | :--- | :--- |
| `fetch_destination_city_list`| Async | `cityid` | JSON | Obtiene la lista de aeropuertos y ciudades destino vinculadas a una ciudad origen. |
| `fetch_destination_city_value`| Async | `cityid`, `service` | JSON | Retorna las tarifas configuradas para viajes entre ciudades (City-to-City). |
| `fetch_airport_value` | Async | `cityid`, `service` | JSON | Retorna las tarifas configuradas para traslados desde/hacia aeropuertos. |
| `check_city_available` | Async | `cityname`, `coords`| JSON | Valida si una ciudad ya está registrada por nombre o por coordenadas para evitar duplicados. |
| `autocomplete_cityname` | Async | `country_id` | JSON | Provee sugerencias de ciudades basadas en el país seleccionado. |
| `fetch_city_list` | Async | `country_id/name` | JSON | Retorna las ciudades que tienen el parámetro `isBusiness` activo para su uso en las Apps. |
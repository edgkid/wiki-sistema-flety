# Archivo: `citytype.js`

## Descripción General
Este controlador es el responsable de gestionar los tipos de servicios y vehículos disponibles en cada ubicación geográfica. Define la relación entre las ciudades y las categorías de transporte (ej: Económico, XL, Entrega), junto con sus respectivos parámetros de tarificación.

---

## Funciones del Controlador

| Función | Tipo | Entrada | Salida | Descripción |
| :--- | :--- | :--- | :--- | :--- |
| `list` | Async | `country`, `city`, `latitude`, `longitude` | Array de `citytypes` con precios | Función principal que lista todos los tipos de servicios disponibles para un usuario según su ubicación actual y calcula precios dinámicos. |
| `get_city_type_list` | Async | `city_id` | Array de tipos de vehículos | Retorna una lista de los servicios configurados y habilitados para una ciudad específica. |
| `get_city_type_services` | Async | `city_type_id` | Detalles del servicio | Recupera la configuración técnica específica de un tipo de servicio (capacidad, iconos, descripción). |
| `check_city_type_priority` | Sync | `city_id`, `type_id` | Nivel de prioridad | Determina el orden jerárquico de visualización de los vehículos en el carrusel de la aplicación móvil. |
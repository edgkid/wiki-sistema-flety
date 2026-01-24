# Archivo: `country.js`

## Descripción General
Este controlador actúa como el gestor principal del modelo **Country**. Su propósito es administrar la jerarquía geográfica del sistema, permitiendo que las aplicaciones móviles y el panel administrativo conozcan la disponibilidad de servicios por región.

---

## Funciones del Controlador

| Función | Tipo | Entrada | Salida | Descripción |
| :--- | :--- | :--- | :--- | :--- |
| `get_country_city_list` | Async | N/A | JSON con Países + Ciudades | Consulta y lista todos los países activos junto con sus respectivas ciudades habilitadas en una sola respuesta estructurada. |
| `countries_list` | Async | N/A | JSON con detalles de país | Retorna la configuración técnica completa de los países (moneda, código de teléfono, banderas, etc.). |
| `cities_list` | Async | `countryId` | JSON con lista de ciudades | Recupera todas las ciudades vinculadas a un ID de país específico para filtrar la operación. |
| `get_country_list` | Async | N/A | JSON con lista de países | Retorna una lista optimizada y ligera de los países donde la plataforma está operativa. |
# Archivo: `City.js`

## Descripción General
Este controlador gestiona el catálogo de ciudades operativas dentro de la plataforma. Es el encargado de filtrar las ubicaciones geográficas donde el servicio está habilitado, permitiendo segmentar la configuración por país.

---

## Funciones del Controlador

| Función | Tipo | Entrada (req.body) | Salida | Descripción |
| :--- | :--- | :--- | :--- | :--- |
| `citylist` | Async | `country` (Nombre del país) | JSON con array `city` | Busca y retorna todas las ciudades de un país específico que se encuentran registradas y activas en el sistema. |
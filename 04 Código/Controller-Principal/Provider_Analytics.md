# Archivo: `provider_analytics.js`

## Descripción General
Este archivo funge como la sección principal para gestionar los datos estadísticos del proveedor. Su función es capturar cada evento importante (viaje recibido, aceptado, rechazado o cancelado) y el tiempo de conexión para generar métricas precisas de desempeño.

---

## Funciones del Controlador

| Función | Tipo | Entrada | Salida | Descripción |
| :--- | :--- | :--- | :--- | :--- |
| `insert_daily_provider_analytics_with_date` | Sync | `date_now`, `city_timezone`, `provider_id`, `trip_status`, `start_time` | Registro en DB | Es la función principal que busca o crea el registro analítico del día y actualiza los contadores (recibidos, aceptados, rechazados, cancelados) y ratios basándose en el estado del viaje. |
| `insert_daily_provider_analytics` | Sync | `city_timezone`, `provider_id`, `trip_status`, `start_time` | Llamada interna | Actúa como un wrapper o acceso directo que toma la fecha actual del servidor y la delega a la función principal para procesar el evento analítico de forma simplificada. |
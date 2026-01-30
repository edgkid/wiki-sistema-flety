# Archivo: `Provider_Daily_Earning.js`

## Descripción General
Este controlador permite al conductor visualizar el desglose de lo que ha ganado día tras día, filtrando por fechas y ciudades si ha operado en varias. 

---

## Funciones del Controlador

| Función | Tipo | Entrada | Salida | Descripción |
| :--- | :--- | :--- | :--- | :--- |
| `provider_daily_earning` | Async | `req.session.provider`, filtros | Vista HTML | Recupera el historial de viajes del proveedor para el periodo seleccionado y calcula los totales diarios de ganancias, distancia recorrida y tiempo en línea. |
| `provider_daily_earning_export_excel` | Async | `req.body` (filtros) | Archivo Excel | Genera y descarga un archivo `.xlsx` con el reporte detallado de los ingresos diarios para que el proveedor pueda llevar su contabilidad personal. |
| `get_city_list` | Async | `req.body.country` | JSON | API de utilidad que lista las ciudades disponibles en un país para que el proveedor pueda filtrar sus métricas de ganancias por zona geográfica. |
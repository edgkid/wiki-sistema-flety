# Archivo: `Trip_Earning.js`

## Descripción General
Este controlador se encarga de la gestión y visualización de las ganancias por viaje desde la perspectiva administrativa.

---

## Funciones del Controlador

| Función                       | Tipo | Entrada                             | Salida        | Descripción                                                                        |
| :---------------------------- | :--- | :---------------------------------- | :------------ | :--------------------------------------------------------------------------------- |
| `trip_earning`                | Sync | `req.body` (filtros), `req.session` | Vista HTML    | Recupera el historial de ingresos de viajes finalizado                             |
| `generate_trip_earning_excel` | Sync | `req.body` (filtros)                | Archivo Excel | Procesa el desglose económico de los viajes filtrados y genera un reporte `.xlsx`  |
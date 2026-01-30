# Archivo: `Shedule.js`

## Descripción General
Este controlador se encarga de la gestión de los viajes programados . Su función principal es administrar las solicitudes de servicios que los usuarios han reservado  y que aún no han sido convertidas en viajes activos.

---

## Funciones del Controlador

| Función                            | Tipo  | Entrada                             | Salida        | Descripción                                                                            |
| :--------------------------------- | :---- | :---------------------------------- | :------------ | :------------------------------------------------------------------------------------- |
| `Schedules_list`                   | Async | `req.body` (filtros), `req.session` | Vista HTML    | Recupera el listado de viajes programados que aún no se han ejecutado.                 |
| `genetare_schedules_request_excel` | Async | `req.body` (filtros)                | Archivo Excel | Procesa la lista de reservas futuras filtradas y genera un reporte en formato `.xlsx`. |
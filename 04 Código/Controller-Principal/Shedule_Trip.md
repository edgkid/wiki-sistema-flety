# Archivo: `sheduledtrip.js`

## Descripción General
Este controlador gestiona la lógica de los servicios que los usuarios reservan con antelación. Su función principal es servir como un panel de consulta y gestión para que el usuario pueda ver sus viajes pendientes y, en caso de ser necesario, cancelarlos antes de que el sistema asigne un conductor de forma automática.

---

## Funciones del Controlador

| Función            | Tipo  | Entrada (req.body)                     | Salida                                           | Descripción                                                                                                                                            |
| :----------------- | :---- | :------------------------------------- | :----------------------------------------------- | :----------------------------------------------------------------------------------------------------------------------------------------------------- |
| `getfuturetrip`    | Async | `user_id`, `token`                     | JSON con arrays `running_trips` y `future_trips` | Recupera tanto los viajes que están ocurriendo en el momento como los viajes programados para el futuro que aún no han sido cancelados ni completados. |
| `cancelfuturetrip` | Async | `user_id`, `token`, `scheduledtrip_id` | JSON con estado de cancelación                   | Permite al usuario cancelar una reserva futura siempre y cuando el viaje aún no haya sido iniciado o asignado a un conductor.                          |

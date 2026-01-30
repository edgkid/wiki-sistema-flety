# Archivo: `Send_Mass_Notifications.js`

## Descripción General
Este controlador gestiona las notificaciones masivas de la plataforma. 

---

## Funciones del Controlador

| Función                  | Tipo  | Entrada                         | Salida      | Descripción                                                                       |
| :----------------------- | :---- | :------------------------------ | :---------- | :-------------------------------------------------------------------------------- |
| `sms_notification`       | Async | `req.session.userid`            | Vista HTML  | Renderiza la interfaz principal para el envío de notificaciones.                  |
| `fetch_user_list`        | Async | `req.body.country`              | JSON        | Filtra y retorna la lista de todos los usuarios registrados en un país específico |
| `fetch_providers_list`   | Async | `req.body.country`              | JSON        | Filtra y retorna la lista de todos los proveedores registrados en un país         |
| `send_mass_notification` | Async | `req.body` (mensaje, IDs, tipo) | Redirección | Procesa el envío masivo.                                                          |
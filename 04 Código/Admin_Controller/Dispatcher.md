# Archivo: `Dispatcher.js`

## Descripción General
Este controlador gestiona la asignación de viajes manualmente, permite crear solicitudes de servicio en nombre de los usuarios,  permite la gestión de viajes programados y la supervisión del historial de operaciones.

---

## Funciones del Controlador

### Autenticación 

| Función                            | Tipo  | Entrada                   | Salida      | Descripción                                 |
| :--------------------------------- | :---- | :------------------------ | :---------- | :------------------------------------------ |
| `loginRender`                      | Sync  | `req.session`             | Vista HTML  | Muestra la pantalla de inicio               |
| `dispatcher_login`                 | Async | `email`, `password`       | Redirección | Valida credenciales y crea la sesión        |
| `dispatcher_forgot_password_email` | Async | `email`                   | Redirección | Envía el link de recuperación.              |
| `dispatcher_update_psw`            | Async | `id`, `token`, `password` | Redirección | Valida el token y actualiza la contraseña . |
| `dispatcher_logout`                | Sync  | `req.session`             | Redirección | Finaliza la sesión.                         |

### Operaciones de Despacho (Logística)
| Función                     | Tipo  | Entrada       | Salida     | Descripción                                       |
| :-------------------------- | :---- | :------------ | :--------- | :------------------------------------------------ |
| `dispatcher_create_trip`    | Async | `req.session` | Vista HTML | Interfaz para crear un nuevo viaje manualmente    |
| `fetch_user_detail`         | Async | `phone`       | JSON       | Busca y retorna los datos de un usuario           |
| `dispatcher_track_trip`     | Async | `trip_id`     | Vista HTML | Interfaz de seguimiento en tiempo real            |
| `dispatcher_cancel_trip`    | Async | `trip_id`     | JSON       | Permite al operador cancelar una solicitud activa |
| `dispatcher_future_request` | Async | `req.session` | Vista HTML | Lista de viajes programados                       |

### Gestión de Usuarios

| Función                     | Tipo  | Entrada                 | Salida      | Descripción                        |
| :-------------------------- | :---- | :---------------------- | :---------- | :--------------------------------- |
| `dispatcher_user_list`      | Async | `req.session`           | Vista HTML  | Directorio de usuarios registrados |
| `dispatcher_profile`        | Async | `req.session`           | Vista HTML  | Muestra la información de perfil   |
| `dispatcher_update_profile` | Async | `req.body`, `req.files` | Redirección | Actualiza los datos personales     |

### Administración de Despachadores

| Función                     | Tipo  | Entrada              | Salida      | Descripción                                                  |
| :-------------------------- | :---- | :------------------- | :---------- | :----------------------------------------------------------- |
| `dispatcher`                | Async | `req.session.userid` | Vista HTML  | Lista todos los despachadores creado                         |
| `add_dispatcher_detail`     | Async | `req.body`           | Redirección | Procesa el registro de un nuevo despachado                   |
| `dispatcher_active_decline` | Async | `id`, `is_approved`  | JSON        | Permite al administrador aprobar o suspender un despachador. |
| `admin_delete_dispatcher`   | Async | `dispatcher_id`      | Redirección | Elimina permanentemente                                      |




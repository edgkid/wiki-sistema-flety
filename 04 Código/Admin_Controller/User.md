# Archivo: `User.js`

## Descripción General
Este controlador gestiona usuarios de la plataforma, administra el ciclo de vida  desde su registro y validación de documentos s, hasta la gestión de su billetera virtual, historial de viajes y sistema de referidos. 

---

## Funciones del Controlador

### 1. Gestión de usuario

| Función               | Tipo  | Entrada              | Salida      | Descripción                                                                           |
| :-------------------- | :---- | :------------------- | :---------- | :------------------------------------------------------------------------------------ |
| `list`                | Async | `req.body` (filtros) | Vista HTML  | Lista todos los usuarios registrados                                                  |
| `edit`                | Async | `req.body.id`        | Vista HTML  | Carga la información completa del perfil de un usuario para permitir su modificación. |
| `update`              | Sync  | `req.body` (datos)   | Redirección | Guarda los cambios realizados en el perfil                                            |
| `profile_is_approved` | Sync  | `id`, `state`        | JSON        | Aprueba o desaprueba el perfil de un usuario .                                        |
| `admin_delete_user`   | Async | `req.body.user_id`   | Redirección | Elimina al usuario de forma segura                                                    |

### 2. Documentación 

| Función          | Tipo | Entrada       | Salida     | Descripción                                  |
| :--------------- | :--- | :------------ | :--------- | :------------------------------------------- |
| `user_documents` | Sync | `req.body.id` | Vista HTML | Lista los documentos cargados por el usuario |
| `history`        | Sync | `req.body.id` | Vista HTML | Recupera y muestra el historial de viajes    |

### 3. Referidos
| Función             | Tipo | Entrada              | Salida      | Descripción                                                |
| :------------------ | :--- | :------------------- | :---------- | :--------------------------------------------------------- |
| `add_wallet_amount` | Sync | `id`, `amount`       | Redirección | Permite añadir o deducir saldo manualmente de la billetera |
| `referral_report`   | Sync | `req.body` (filtros) | Vista HTML  | Genera un reporte de los usuarios que han referido a otros |
| `referral_history`  | Sync | `req.body.id`        | Vista HTML  | Muestra el detalle de a quiénes ha referido un usuario     |

### 4. Reportes

| Función                       | Tipo    | Entrada              | Salida        | Descripción                                                               |
| :---------------------------- | :------ | :------------------- | :------------ | :---------------------------------------------------------------------- |
| `generate_user_excel`         | Async   | `req.body` (filtros) | Archivo Excel | Procesa la lista de usuarios  repo                                        |
| `generate_user_history_excel` | Sync    | `req.body.id`        | Archivo Excel | Exporta el historial de viajes de un usuario específico para audi ía.     |
| `generate_excel`              | Interna | `array`, `timezone`  | Archivo                                                                         usuarios. |
|                               |         |                      |                                                                                           |
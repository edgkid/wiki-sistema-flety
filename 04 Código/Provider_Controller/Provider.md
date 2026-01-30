# Archivo: `Provider.js`

## Descripción General
Este controlador permite la gestión de proveedores; registro, autenticación, recuperación de contraseñas y la actualización de perfiles.

---

## Funciones del Controlador

### 1. Autenticación 

| Función                     | Tipo | Entrada              | Salida      | Descripción                                              |
| :-------------------------- | :--- | :------------------- | :---------- | :------------------------------------------------------- |
| `provider_register`         | Sync | `req.session`        | Vista HTML  | Renderiza la página de registro para nuevos proveedores. |
| `provider_register_post`    | Sync | `req.body` (datos)   | Redirección | Procesa el  nuevo registro.                              |
| `provider_login`            | Sync | N/A                  | Vista HTML  | Muestra el formulario de inicio de sesión.               |
| `provider_login_post`       | Sync | `email`, `password`  | Redirección | Valida credenciales, gestiona sesiones                   |
| `provider_social_login_web` | Sync | `req.body.social_id` | Redirección | Gestiona el acceso mediante redes sociales               |
| `provider_sign_out`         | Sync | `req.session`        | Redirección | Destruye la sesión actual y redirige al inicio.          |

### 2. Recuperación de Credenciales
| Función            | Tipo | Entrada             | Salida      | Descripción                                                    |
| :----------------- | :--- | :------------------ | :---------- | :------------------------------------------------------------- |
| `forgot_password`  | Sync | N/A                 | Vista HTML  | Muestra la interfaz para solicitar recuperación de contraseña. |
| `forgot_psw_email` | Sync | `req.body.email`    | Redirección | Genera un token y envía el correo de recuperación.             |
| `edit_psw`         | Sync | `req.params.token`  | Vista HTML  | Valida el token y muestra el formulario de cambio de clave.    |
| `update_psw`       | Sync | `req.body.password` | Redirección | Actualiza la nueva contraseña                                  |

### 3. Gestión de Perfil 

| Función                     | Tipo | Entrada             | Salida      | Descripción                                                |
| :-------------------------- | :--- | :------------------ | :---------- | :--------------------------------------------------------- |
| `provider_profile`          | Sync | `req.session`       | Vista HTML  | Carga la información del perfil                            |
| `provider_profile_update`   | Sync | `req.body`, `files` | Redirección | Actualiza datos del perfil .                               |
| `provider_document_panel`   | Sync | `req.session`       | Vista HTML  | Lista los documentos personales cargados y pendientes.     |
| `provider_documents_edit`   | Sync | `req.body.id` (doc) | Vista HTML  | Muestra el formulario de carga para un documento personal. |
| `provider_documents_update` | Sync | `req.files`, `body` | Redirección | Sube el archivo y marca el documento como "subido".        |

### 4. Gestión Vehículos

| Función                             | Tipo | Entrada             | Salida      | Descripción                                                  |
| :---------------------------------- | :--- | :------------------ | :---------- | :----------------------------------------------------------- |
| `provider_vehicle`                  | Sync | `req.session`       | Vista HTML  | Lista los vehículos registrados en la cuenta del proveedor.  |
| `provider_add_vehicle`              | Sync | N/A                 | Vista HTML  | Muestra el formulario para registrar un nuevo vehículo.      |
| `provider_add_vehicle_details`      | Sync | `req.body`, `files` | Redirección | Crea el registro del vehículo l.                             |
| `edit_vehicle_detail`               | Sync | `req.body.v_id`     | Vista HTML  | Carga el formulario para editar datos técnicos del vehículo. |
| `update_vehicle_detail`             | Sync | `req.body` (datos)  | Redirección | Guarda cambios técnicos del vehiculo                         |
| `vehicle_document_list`             | Sync | `req.body.v_id`     | Vista HTML  | Lista los documentos asociados a un vehículo.                |
| `provider_vehicle_documents_edit`   | Sync | `req.body.id`       | Vista HTML  | Formulario de carga para documento de vehículo.              |
| `provider_vehicle_documents_update` | Sync | `files`, `body`     | Redirección | Sube el archivo del documento del vehículo.                  |

### 5. Utilitarios

| Función             | Tipo | Entrada            | Salida     | Descripción                                                  |
| :------------------ | :--- | :----------------- | :--------- | :----------------------------------------------------------- |
| `provider_trip_map` | Sync | `req.body.trip_id` | Vista HTML | Muestra el mapa con ruta y ubicación de un viaje específico. |
| `terms`             | Sync | N/A                | Vista HTML | Muestra los términos y condiciones para proveedores.         |
| `privacy`           | Sync | N/A                | Vista HTML | Muestra la política de privacidad para proveedores.          |
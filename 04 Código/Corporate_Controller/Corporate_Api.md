# Archivo: `Corporate_api.js`

## Descripción General
Este controlador actúa como una interfaz de programación de aplicaciones (API) interna para el panel corporativo. Permite la gestión administrativa del perfil empresarial, el control de acceso de los usuarios vinculados y la exportación de reportes operativos de servicios solicitados.

---

## Funciones del Controlador

| Función | Tipo | Entrada | Salida | Descripción |
| :--- | :--- | :--- | :--- | :--- |
| `corporate_edit_profile` | Async | `req.body`, `session` | JSON | Actualiza la información básica y de contacto del perfil corporativo. |
| `corporate_check_password` | Async | `password`, `session` | JSON | Valida que la contraseña actual sea correcta antes de realizar cambios sensibles. |
| `corporate_update_password` | Async | `password`, `session` | JSON | Procesa el cambio y encriptación de la nueva contraseña de la cuenta corporativa. |
| `get_corporate_user_list` | Async | `session` | JSON | Recupera la lista completa de empleados o usuarios asociados a una empresa específica. |
| `add_corporate_user` | Async | `req.body` | JSON | Registra y vincula un nuevo usuario bajo el régimen de facturación de la cuenta corporativa. |
| `delete_corporate_user` | Async | `user_id` | JSON | Elimina de forma lógica o permanente a un usuario asociado a la corporación. |
| `get_corporate_requests` | Async | `session`, `filters` | JSON | Obtiene el historial de solicitudes de servicio realizadas por los usuarios de la empresa. |
| `export_requests_excel` | Async | `req.body` (filtros) | URL (JSON) | Genera un archivo Excel descargable con el detalle técnico de las solicitudes corporativas. |
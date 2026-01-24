# Archivo: `emergency_contact.js`

## Descripción General
Este controlador administra la funcionalidad de **"Contactos de Emergencia"**. Permite realizar las operaciones CRUD (Crear, Consultar y Eliminar) sobre los contactos de seguridad vinculados a la cuenta del usuario, además de gestionar el envío de alertas SOS.

---

## Funciones del Controlador

| Función | Tipo | Entrada | Salida | Descripción |
| :--- | :--- | :--- | :--- | :--- |
| `add_emergency_contact` | Async | `user_id`, `phone`, `name` | JSON con el nuevo contacto | Registra un nuevo contacto de emergencia en la base de datos asociado al usuario. |
| `get_emergency_contact` | Async | `user_id` | Array de contactos | Recupera la lista completa de contactos de confianza registrados por el usuario. |
| `delete_emergency_contact` | Async | `user_id`, `emergency_contact_id` | JSON de éxito | Elimina un contacto de emergencia específico del perfil del usuario. |
| `send_sms_to_emergency_contact` | Async | `user_id`, `map` (URL) | JSON de confirmación | Envía un SMS masivo a todos los contactos registrados incluyendo la ubicación actual (URL del mapa) en caso de emergencia. |
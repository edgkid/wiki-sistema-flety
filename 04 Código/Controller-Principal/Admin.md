# Archivo: `Admin.js`

## Descripción General
Este controlador está diseñado para interactuar exclusivamente con el **Panel Administrativo (CMS)**. Proporciona los recursos necesarios para la configuración global del sistema, la gestión de llaves de aplicaciones y la supervisión técnica de los servicios.

---

## Funciones del Controlador

| Función | Tipo | Entrada | Salida | Descripción |
| :--- | :--- | :--- | :--- | :--- |
| `getlanguages` | Async | N/A | Array de idiomas | Recupera la lista de todos los lenguajes configurados y habilitados en el sistema. |
| `getsettingdetail` | Async | N/A | Objeto Settings | Obtiene la configuración global del servidor (parámetros de comisión, versiones, etc.). |
| `get_app_keys` | Async | `app_type` | Keys de Google / iOS | Retorna las llaves de configuración específicas (Maps, Firebase) que las Apps móviles necesitan para inicializarse. |
| `uploadProofRender` | Async | `id` (trip), `provider_id` | Vista HTML | Renderiza la interfaz visual para que un administrador pueda subir imágenes de soporte para un viaje específico. |
| `uploadProofImages` | Async | `id` (trip), `files` | JSON de éxito | Procesa la carga de imágenes al servidor y actualiza el campo `proof_images` en el historial del viaje. |
| `check_auth` | Sync | `req.session` | Redirección / Next | Middleware de validación que verifica si el usuario tiene una sesión activa y autorizada de administrador. |
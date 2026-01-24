# Archivo: `Providerdocument.js`

## Descripción General
Este controlador gestiona el ciclo de vida de la documentación legal y operativa de los proveedores. Permite la consulta de requisitos documentales y la carga de archivos necesarios para la validación y activación del conductor en la plataforma.

---

## Funciones del Controlador

| Función | Tipo | Entrada (req.body) | Salida | Descripción |
| :--- | :--- | :--- | :--- | :--- |
| `getproviderdocument` | Async | `provider_id`, `token` | JSON con array `providerdocument` | Recupera la lista completa de documentos obligatorios y cargados (licencias, seguros, etc.) asociados al perfil del proveedor. |
| `uploadproviderdocument` | Async | `provider_id`, `document_id`, `token`, `file` (imagen) | JSON con el objeto `provider_detail` actualizado | Procesa la carga de archivos físicos del proveedor, actualiza el estado del documento y vincula la URL del archivo al perfil. |
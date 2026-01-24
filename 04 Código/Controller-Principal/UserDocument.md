# Archivo: `user_document.js`

## Descripción General
Este controlador se encarga de la gestión de la documentación de los usuarios en el sistema.

---

## Funciones del Controlador

| Función                | Tipo  | Entrada (req.body)                                    | Salida                                        | Descripción                                                        |
| :--------------------- | :---- | :---------------------------------------------------- | :-------------------------------------------- | :----------------------------------------------------------------- |
| `userdocument_list`    | Async | `user_id`, `token` (opcional)                         | JSON con array `userdocument`                 | permite consultar una lista de los documentos asociados al usuario |
| `upload_user_document` | Async | `user_id`, `document_id`, `token`, `file` (multipart) | JSON con el objeto `userdocument` actualizado | Procesa la carga de archivos (Documentos) de los usuarios          |

# Archivo: `Sms_Detail.js`

## Descripción General
Este controlador gestiona las plantillas de mensajes SMS del sistema. 

---

## Funciones del Controlador

| Función             | Tipo | Entrada            | Salida      | Descripción                                           |
| :------------------ | :--- | :----------------- | :---------- | :---------------------------------------------------- |
| `sms`               | Sync | `req.session`      | Vista HTML  | Recupera todas las plantillas de SMS configuradas e   |
| `get_sms_data`      | Sync | `req.body.id`      | JSON        | Busca y retorna los datos detallados de una plantilla |
| `update_sms_detail` | Sync | `req.body` (datos) | Redirección | Actualiza el contenido del mensaje de una plantilla   |

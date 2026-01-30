
# Archivo: `Email_Detail.js`

## Descripción General
Este controlador permite gestionar las plantillas de correo electrónico y su envió.

---

## Funciones del Controlador

| Función               | Tipo  | Entrada                  | Salida      | Descripción                                                                                            |
| :-------------------- | :---- | :----------------------- | :---------- | :----------------------------------------------------------------------------------------------------- |
| `email`               | Async | `req.session.userid`     | Vista HTML  | Recupera todas las plantillas de correo registradas en la base de datos y renderiza la vista principal |
| `get_email_data`      | Async | `req.body.id`            | JSON        | API que busca una plantilla específica por su ID y retorna sus datos (asunto, contenido).              |
| `update_email_detail` | Async | `req.body` (datos email) | Redirección | Procesa y guarda los cambios realizados en una plantilla (asunto y cuerpo HTML)                        |
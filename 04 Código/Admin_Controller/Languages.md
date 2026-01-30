# Archivo: `Languages.js`

## Descripción General
Este controlador permite gestionar los Idiomas, define qué lenguajes están disponibles en el sistema.

---

## Funciones del Controlador

| Función                   | Tipo   | Entrada                     | Salida     | Descripción                                                                                    |
| :------------------------ | :----- | :-------------------------- | :--------- | :--------------------------------------------------------------------------------------------- |
| `languages`               | Async  | `req.session.userid`        | Vista HTML | Recupera el listado completo de idiomas registrados en la base de datos                        |
| `add_languages`           | Render | N/A                         | Vista HTML | Renderiza el formulario de creación                                                            |
| `add_languages_detail`    | Async  | `req.body` (nombre, código) | JSON       | Procesa el registro del nuevo idioma                                                           |
| `edit_languages`          | Async  | `req.body.id`               | Vista HTML | Busca un idioma específico por su identificador único y carga sus datos en la vista de edición |
| `update_languages_detail` | Async  | `req.body.id`, `data`       | JSON       | Actualiza la información de un idioma existente                                                |
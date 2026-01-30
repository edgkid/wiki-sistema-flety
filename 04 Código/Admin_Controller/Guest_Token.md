# Archivo: `Guest_Token.js`

## Descripción General
Este controlador permite al administrador gestionar los Tokens de Invitado.. El módulo permite crear, editar, listar y controlar el estado de activación de cada token.

---

## Funciones del Controlador

### Gestión de Listados y Vistas
| Función                | Tipo   | Entrada                       | Salida     | Descripción                                                                              |
| :--------------------- | :----- | :---------------------------- | :--------- | :--------------------------------------------------------------------------------------- |
| `guest_token_list`     | Async  | `req.session.userid`, filtros | Vista HTML | Recupera y muestra la lista de todos los tokens                                          |
| `add_guest_token_form` | Render | N/A                           | Vista HTML | Renderiza el formulario administrativo                                                   |
| `edit`                 | Async  | `req.body.id`                 | Vista HTML | Busca un token específico por su ID y carga sus datos en una vista para su modificación. |

### Operaciones de Datos (CRUD)
| Función              | Tipo  | Entrada                   | Salida      | Descripción                                                                                        |
| :------------------- | :---- | :------------------------ | :---------- | :------------------------------------------------------------------------------------------------- |
| `add_guest_token`    | Async | `req.body`                | Redirección | Crea un nuevo registro de token                                                                    |
| `update`             | Async | `req.body.id`, `req.body` | Redirección | Procesa los cambios realizados en un token (nombre o parámetros) y los guarda en la base de datos. |
| `delete_guest_token` | Async | `req.body.id`             | Redirección | Elimina permanentemente el token                                                                   |

### Control de Estado
| Función | Tipo  | Entrada       | Salida      | Descripción                               |
| :------ | :---- | :------------ | :---------- | :---------------------------------------- |
| `act`   | Async | `id`, `state` | Redirección | Cambia el estado de activación del token. |
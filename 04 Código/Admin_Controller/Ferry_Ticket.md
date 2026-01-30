# Archivo: `Ferry_Ticket.js`

## Descripción General
Este controlador se administra y valida los Tickets de Ferry adquiridos a través de la plataforma, proporciona una interfaz de auditoría para listar y filtrar todos los tickets vendidos.

---

## Funciones del Controlador

| Función               | Tipo  | Entrada                      | Salida      | Descripción                                                  |
| :-------------------- | :---- | :--------------------------- | :---------- | :----------------------------------------------------------- |
| `ferry_tickets`       | Async | `req.session.admin`, filtros | Vista HTML  | Recupera el listado de tickets de ferry de la base de datos. |
| `upload_ferry_ticket` | Async | `req.files`, `id` (ticket)   | Redirección | Gestiona la carga del archivo físico del boleto.             |
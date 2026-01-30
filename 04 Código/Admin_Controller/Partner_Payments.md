# Archivo: `Partner_Payments.js`

## Descripción General
Este controlador gestiona la pasarela de pagos y la billetera digital de los asociados. 

---

## Funciones del Controlador

### Gestión de Billetera y Vistas
| Función                     | Tipo  | Entrada                      | Salida      | Descripción                              |
| :-------------------------- | :---- | :--------------------------- | :---------- | :--------------------------------------- |
| `partner_payments`          | Async | `req.session.partner`        | Vista HTML  | Renderiza la pantalla principal de pagos |
| `partner_add_wallet_amount` | Async | `req.body.payment_intent_id` | Redirección | Procesa la recarga de la billetera.      |

### Administración de Métodos de Pago (Cards)
| Función                    | Tipo  | Entrada                  | Salida      | Descripción                                 |
| :------------------------- | :---- | :----------------------- | :---------- | :------------------------------------------ |
| `partner_add_card`         | Async | `req.body.payment_token` | Redirección | Registra un nuevo método de pago            |
| `partner_delete_card`      | Async | `req.body.card_id`       | Redirección | Elimina un método de pago                   |
| `partner_set_default_card` | Async | `req.body.card_id`       | Redirección | Permite cambiar el método de pago principal |
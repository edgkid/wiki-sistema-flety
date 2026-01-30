# Archivo: `payment.js`

## Descripción General
Este controlador gestiona el pagos y billetera de proveedores.

---

## Funciones del Controlador

| Función                      | Tipo | Entrada                | Salida      | Descripción                                                                                        |
| :--------------------------- | :--- | :--------------------- | :---------- | :------------------------------------------------------------------------------------------------- |
| `provider_payments`          | Sync | `req.session.provider` | Vista HTML  | Renderiza la interfaz de pagos del proveedor.                                                      |
| `add_card`                   | Sync | `req.body` (token)     | Redirección | Registra un nuevo método de pago en la pasarela de pagos.                                          |
| `delete_card`                | Sync | `req.body.card_id`     | Redirección | Elimina un método de pago registrado.                                                              |
| `card_selection`             | Sync | `req.body.card_id`     | Redirección | Cambia el metodo de pago configurado como predeterminado .                                         |
| `provider_add_wallet_amount` | Sync | `req.body` (monto)     | Redirección | Procesa la recarga de saldo intent. En caso de éxito, actualiza el saldo y registra el movimiento. |
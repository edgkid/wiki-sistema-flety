# Archivo: `corporate_payments.js`

## Descripción General
Este controlador permite gestionar la configuración financiera del cliente corporativo. Centraliza la administración de métodos de pago electrónicos, el control del historial de la billetera virtual y la gestión de cuentas bancarias para reembolsos o transferencias.

---

## Funciones del Controlador

| Función                           | Tipo  | Entrada                              | Salida      | Descripción                                                                                        |
| :-------------------------------- | :---- | :----------------------------------- | :---------- | :------------------------------------------------------------------------------------------------- |
| `corporate_payments`              | Async | `req.session.corporate`              | Vista HTML  | Recupera y muestra los métodos de pago vinculados actualmente a la cuenta corporativa.             |
| `corporate_add_card`              | Async | `payment_token`                      | JSON        | Recibe el token de la pasarela de pago para registrar una nueva tarjeta corporativa.               |
| `corporate_delete_card`           | Async | `card_id`                            | JSON        | Elimina un método de pago específico de los registros de la empresa.                               |
| `corporate_set_default_card`      | Async | `card_id`                            | JSON        | Actualiza el estado del método de pago para marcarlo como la opción principal de cobro.            |
| `corporate_wallet_history`        | Async | `req.session.corporate`              | Vista HTML  | Consulta y lista todos los movimientos (ingresos y egresos) de la billetera corporativa.           |
| `corporate_add_wallet_amount`     | Async | `amount`, `card_id`                  | JSON        | Procesa el cobro a través de un método de pago para recargar el saldo de la billetera corporativa. |
| `corporate_add_bank_detail`       | Async | `bank_holder_name`, `account_number` | JSON        | Registra la información bancaria oficial de la empresa para trámites administrativos.              |
| `corporate_delete_bank_detail`    | Async | `req.session.corporate`              | JSON        | Elimina la cuenta bancaria vinculada a la entidad corporativa.                                     |
| `corporate_export_wallet_history` | Async | `req.body` (filtros)                 | CSV / Excel | Genera y descarga un reporte exportable con los movimientos financieros de la empresa.             |

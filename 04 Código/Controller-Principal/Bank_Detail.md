# Archivo: `Bank_Detail.js`

## Descripción General
Este controlador administra las cuentas bancarias de los **Proveedores** y **Partners**. Es el componente encargado de gestionar la información necesaria para que la plataforma pueda realizar las transferencias de ganancias (payouts) de forma automatizada hacia las instituciones financieras externas.

---

## Funciones del Controlador

| Función              | Tipo  | Entrada                                      | Salida                   | Descripción                                                                                                                      |
| :------------------- | :---- | :------------------------------------------- | :----------------------- | :------------------------------------------------------------------------------------------------------------------------------- |
| `add_bank_detail`    | Async | `provider_id`, `account_number`, `bank_code` | JSON (Bank Object)       | Registra y valida la cuenta bancaria del proveedor en el sistema.                                                                |
| `get_bank_detail`    | Async | `provider_id`, `token`, `type`               | JSON con datos bancarios | Recupera la información de la cuenta activa vinculada al conductor o socio comercial.                                            |
| `delete_bank_detail` | Async | `provider_id`, `token`                       | JSON de éxito            | Elimina de forma segura la información bancaria del perfil del proveedor.                                                        |
| `get_bank_list`      | Async | `country_id`                                 | Array de Bancos          | Retorna la lista de bancos soportados por el sistema para un país específico, facilitando la selección de la entidad financiera. |
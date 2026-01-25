# Archivo: `card.js`

## Descripción General
Este controlador gestiona el ciclo de vida completo de los métodos de pago electrónicos disponibles en la plataforma. Se encarga de la comunicación segura con pasarelas externas (como Paystack o Stripe), permitiendo a los usuarios tokenizar tarjetas y gestionar sus preferencias de facturación.

---

## Funciones del Controlador

| Función | Tipo | Entrada | Salida | Descripción |
| :--- | :--- | :--- | :--- | :--- |
| `paystack_add_card_callback` | Async | `reference` (vía URL) | Redirección/JSON | Verifica con la API de Paystack si una transacción de vinculación de tarjeta fue exitosa tras el flujo web. |
| `add_card` | Async | `user_id`, `token`, `payment_token` | JSON (Card Detail) | Registra una nueva tarjeta en el sistema vinculándola de forma segura al perfil del usuario. |
| `cards_list` | Async | `user_id`, `token` | Array de tarjetas | Recupera todas las tarjetas guardadas del usuario, ocultando datos sensibles (PCI DSS). |
| `delete_card` | Async | `user_id`, `card_id` | JSON de éxito | Elimina una tarjeta del registro de la base de datos. |
| `selection_card` | Async | `user_id`, `card_id` | JSON de éxito | Marca una tarjeta específica como la "Predeterminada" para futuros cobros automáticos. |
| `get_card_selection` | Async | `user_id` | Objeto Card | Consulta rápida para identificar el método de pago activo del usuario. |
| `change_payment_mode` | Async | `user_id`, `trip_id`, `payment_mode` | JSON de éxito | Permite al usuario alternar entre Efectivo (Cash) y Tarjeta (Card) durante un viaje activo. |
| `check_card_status` | Sync | `card_id` | Boolean | Verifica si una tarjeta está activa o si ha expirado según los metadatos registrados. |
| `get_payment_gateway_token` | Async | `user_id` | Token de pasarela | Obtiene las llaves públicas o tokens efímeros necesarios para inicializar el SDK de pagos en la App móvil. |
| `verify_payment_status` | Async | `transaction_id` | Estado de pago | Consulta al proveedor de pagos el resultado final (éxito/fallo) de un intento de cobro específico. |
| `update_card_expiry` | Async | `card_id`, `month`, `year` | JSON de éxito | Permite actualizar la fecha de vencimiento de una tarjeta existente sin necesidad de re-vincularla. |
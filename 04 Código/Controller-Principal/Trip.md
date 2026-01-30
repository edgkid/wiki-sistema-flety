# Archivo: `trip.js`

## Descripción General
En el presente controlador se define las bases principales de lógica de negocio para la gestión transaccional de los servicios en la plataforma. Se gestiona el ciclo de vida completo de un servicio (viaje), donde los principales actores corresponden al **Cliente** y al **Proveedor (Conductor)**.

> **Nota:** Todas las funciones operan sobre un entorno **Express**, por lo que su detalle de salida principal es una respuesta JSON enviada al cliente (`res.json`).

---

## Lógica del Controlador Trip.js

| Función                         | Tipo  | Entrada                        | Salida                | Descripción                                                         |
| :------------------------------ | :---- | :----------------------------- | :-------------------- | :------------------------------------------------------------------ |
| `create_trip`                   | Async | user_data, trip_type, req_data | trip, multiple_trips  | Método principal para la creación de solicitudes de viaje.          |
| `responds_trip`                 | Async | trip_id, provider_id, status   | JSON éxito/error      | Procesa la aceptación o rechazo de un viaje por el proveedor.       |
| `trip_cancel_by_user`           | Async | trip_id, user_id, token        | Estado de reembolso   | Gestiona la cancelación del usuario y libera al conductor.          |
| `trip_cancel_by_provider`       | Async | trip_id, provider_id           | Confirmación éxito    | El conductor cancela el viaje y se reasigna o finaliza.             |
| `trip_cancel_by_admin`          | Async | trip_id (admin auth)           | Confirmación éxito    | Cancelación forzosa desde el panel administrativo.                  |
| `provider_set_trip_status`      | Async | trip_id, status, lat/long      | Trip actualizado      | Cambia el estado (Arrived, Started) y notifica vía socket.          |
| `check_destination`             | Async | trip_id, latitude, longitude   | Zona de destino       | Valida si el destino está en zona con tarifa fija o aeropuerto.     |
| `provider_complete_trip`        | Async | trip_id, provider_id           | trip_history          | Finaliza el viaje, calcula la factura final y procesa el pago.      |
| `user_setdestination`           | Async | trip_id, destination_address   | Éxito                 | Permite al usuario actualizar el destino durante el viaje.          |
| `pay_by_other_payment_mode`     | Async | trip_id, payment_mode          | JSON éxito            | Cambia el método de pago antes de cerrar la factura.                |
| `complete_card_payment_trip`    | Async | trip_id                        | JSON éxito            | Procesa el cobro a la tarjeta vinculada para un viaje completado.   |
| `upload_pod_per_stop`           | Async | trip_id, files (imágenes)      | URLs de archivos      | Sube pruebas de entrega (Proof of Delivery) por cada parada.        |
| `get_trip_status`               | Async | trip_id, token                 | Datos del viaje       | Devuelve el estado actual y ubicación del proveedor en tiempo real. |
| `get_nearby_provider`           | Async | latitude, longitude, city      | Lista conductores     | Filtra conductores cercanos para mostrar en el mapa del usuario.    |
| `provider_set_otp`              | Async | trip_id, otp                   | Validación            | Compara el código OTP para permitir el inicio del viaje.            |
| `send_emergency_contact_detail` | Async | trip_id, user_id               | Confirmación          | Envía SMS/Notificación con ubicación a contactos de confianza.      |
| `user_rating_to_provider`       | Async | trip_id, rating, review        | JSON éxito            | Registra la calificación que el usuario da al conductor.            |
| `provider_rating_to_user`       | Async | trip_id, rating, review        | JSON éxito            | Registra la calificación que el conductor da al usuario.            |
| `get_trip_history`              | Async | user_id/provider_id            | Array de viajes       | Recupera el historial de viajes finalizados o cancelados.           |
| `get_trip_detail`               | Async | trip_id                        | Objeto trip           | Obtiene toda la información técnica y de costos de un viaje.        |
| `get_invoice`                   | Async | trip_id                        | Desglose factura      | Genera el detalle de costos (distancia, tiempo, impuestos).         |
| `set_trip_stop_status`          | Async | trip_id, stop_id, status       | Éxito                 | Marca una parada intermedia como visitada o completada.             |
| `check_trip_status`             | Sync  | trip_id                        | Status string         | Verifica de forma rápida el estado interno para validaciones.       |
| `update_trip_location`          | Async | trip_id, lat, long             | Éxito                 | Actualiza la trayectoria del viaje en la tabla de rutas.            |
| `add_trip_toll_price`           | Async | trip_id, toll_amount           | Trip actualizado      | Suma montos de peajes manuales a la tarifa final.                   |
| `chat_history`                  | Async | trip_id                        | Array mensajes        | Recupera la conversación entre usuario y conductor.                 |
| `apply_promo_code`              | Async | user_id, promo_code            | Descuento aplicado    | Valida y aplica un cupón de descuento a la solicitud.               |
| `get_fare_estimate`             | Async | pickup, destination, type      | Estimación costo      | Calcula el precio aproximado antes de pedir el viaje.               |
| `check_provider_status`         | Async | provider_id                    | Status booleano       | Verifica si el conductor sigue disponible para asignar.             |
| `set_waiting_time`              | Async | trip_id, time                  | Éxito                 | Registra tiempo de espera adicional para cobro posterior.           |
| `refund_trip_payment`           | Async | trip_id, amount                | Éxito                 | Ejecuta el reembolso a través de la pasarela de pagos.              |
| `get_provider_location`         | Async | trip_id                        | Lat/Long              | Retorna solo las coordenadas actuales del conductor.                |
| `notify_user_arrived`           | Async | trip_id                        | Notificación          | Envía push manual indicando que el conductor está afuera.           |
| `change_trip_type`              | Async | trip_id, new_type              | Éxito                 | Cambia categoría (ej: de entrega normal a express).                 |
| `verify_trip_otp`               | Sync  | trip_id, otp_code              | Boolean               | Validación lógica interna del código de seguridad.                  |
| `get_trip_path`                 | Async | trip_id                        | Polilínea / Puntos    | Recupera el dibujo de la ruta seguida durante el servicio.          |
| `add_favourite_driver`          | Async | user_id, provider_id           | Éxito                 | Marca a un conductor para futuras asignaciones preferentes.         |
| `remove_favourite_driver`       | Async | user_id, provider_id           | Éxito                 | Elimina a un conductor de la lista de preferidos.                   |
| `get_favourite_drivers`         | Async | user_id                        | Lista conductores     | Lista todos los conductores preferidos del usuario.                 |
| `user_get_trip_vehicle_docs`    | Async | user_id, vehicles              | Array documentos      | Consulta documentos legales del vehículo.                           |
| `check_city_business`           | Async | lat, long, city_id             | Disponibilidad        | Valida si el servicio opera en las coordenadas dadas.               |
| `dispatch_trip`                 | Async | trip_id, manual_assign         | Éxito                 | Función interna para despachar el viaje a la cola de búsqueda.      |
| `get_active_trips`              | Async | user_id/provider_id            | Lista activos         | Retorna viajes en curso para reconexión de la App.                  |
| `cancel_waiting_trip`           | Async | trip_id                        | Éxito                 | Cancela solicitudes que no encontraron conductor a tiempo.          |
| `update_payment_id`             | Async | trip_id, payment_id            | Éxito                 | Actualiza la referencia de transacción de la pasarela.              |
| `split_payment_request`         | Async | trip_id, other_user_id         | Notificación          | Envía solicitud de pago compartido a otro usuario.                  |
| `accept_split_payment`          | Async | trip_id, user_id               | Éxito                 | Procesa la aceptación del pago compartido.                          |
| `reject_split_payment`          | Async | trip_id, user_id               | Éxito                 | Rechaza la división del costo por parte de un invitado.             |
| `get_service_types`             | Async | city_id                        | Array servicios       | Lista tipos de vehículos disponibles en esa ciudad.                 |
| `validate_zone_fare`            | Async | pickup_loc, dest_loc           | Tarifa fija           | Determina si el viaje califica para precio por zona.                |
| `set_trip_description`          | Async | trip_id, comment               | Éxito                 | Permite añadir notas especiales al viaje.                           |
| `get_airport_list`              | Async | city_id                        | Array aeropuertos     | Lista aeropuertos configurados con tarifas especiales.              |
| `check_airport_ride`            | Sync  | lat, long, city_id             | Airport ID            | Identifica si un punto geográfico está en un aeropuerto.            |
| `set_trip_tips`                 | Async | trip_id, tip_amount            | Éxito                 | Añade propina al conductor después de finalizar.                    |
| `get_trip_receipt`              | Async | trip_id                        | PDF / Datos Recibo    | Genera la información para el comprobante de pago legal.            |
| `provider_start_waiting`        | Async | trip_id                        | Timestamp             | Inicia el cronómetro de tiempo de espera cobrable.                  |
| `user_track_provider`           | Async | trip_id                        | Lat/Long/Bearing      | Seguimiento preciso para el movimiento del icono en el mapa.        |
| `get_country_city_list`         | Async | N/A                            | Lista países/ciudades | Obtiene la configuración regional para el registro inicial.         |
| `verify_user_for_trip`          | Async | user_id, token                 | Boolean               | Validación de seguridad previa a la creación del viaje.             |
| `log_trip_event`                | Sync  | trip_id, event_name            | Éxito                 | Registra hitos en los logs (ej: "Pago fallido").                    |
| `update_trip_promo`             | Async | trip_id, new_promo             | Éxito                 | Permite cambiar el código promocional antes de finalizar.           |
| `calculate_distance_matrix`     | Async | origin, destination            | Distancia/Tiempo      | Consulta a Google Maps para obtener datos de ruta.                  |
| `get_corporate_trips`           | Async | corporate_id                   | Lista viajes          | Recupera historial de servicios facturados a empresas.              |
| `assign_manual_provider`        | Async | trip_id, provider_id           | Éxito                 | Asignación directa desde el panel de despacho.                      |
| `get_trip_logs`                 | Async | trip_id                        | Array de logs         | Histórico de todas las acciones realizadas en ese viaje.            |
| `validate_payment_intent`       | Async | trip_id                        | Status pago           | Verifica con la pasarela si el pago está autorizado.                |
| `send_invoice_email`            | Async | trip_id, email                 | Éxito                 | Envía el resumen del viaje al correo del usuario.                   |
| `check_ride_share_capacity`     | Sync  | trip_id, capacity              | Boolean               |                                                                     |
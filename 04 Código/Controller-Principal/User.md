# Archivo: `User.js`

## Descripción General
Controlador encargado de gestionar las peticiones de usuario, su información de perfil, autenticación, métodos de pago y solicitudes relacionadas con los servicios de la plataforma.

---

## Funciones del Controlador

| Función | Tipo | Entrada (request.body) | Salida | Descripción |
| :--- | :--- | :--- | :--- | :--- |
| `user_register` | Async | first_name, email, phone, password | Datos + Token | Registra un nuevo usuario, valida duplicados y sube imagen de perfil. |
| `user_login` | Async | email, password, device_token | Perfil usuario | Autentica al usuario y actualiza token de notificaciones. |
| `user_login_social` | Async | social_id, login_by | Perfil usuario | Gestiona acceso vía Facebook, Google u otros proveedores. |
| `user_update` | Async | user_id, first_name, image | Usuario actualizado | Permite modificar información personal y foto de perfil. |
| `user_get_detail` | Async | user_id, token | Objeto user | Retorna la información del perfil validando la sesión. |
| `forgot_password` | Async | type (user), email | Mensaje éxito | Envía correo con enlace/código para resetear contraseña. |
| `check_user_registered` | Async | email, phone | Boolean / Info | Verifica si el correo o teléfono ya existe en el sistema. |
| `update_device_token` | Async | user_id, device_token | Éxito | Actualiza el token de Firebase/Push para alertas. |
| `user_logout` | Async | user_id | Éxito | Limpia el token de dispositivo y cierra la sesión. |
| `get_fare_estimate_all_type` | Async | pickup_lat/long, dest_lat/long | Lista tipos + precios | Calcula costo estimado para todos los servicios de una zona. |
| `get_fare_estimate` | Async | service_type_id, distance, time | Objeto de costos | Desglose detallado de tarifa para un servicio específico. |
| `apply_promo_code` | Async | promo_code, user_id | Valor descuento | Valida si un cupón es apto para el usuario y el viaje. |
| `add_card` | Async | payment_token, user_id | Datos tarjeta | Vincula método de pago vía Stripe/Paystack. |
| `get_card_list` | Async | user_id | Array de tarjetas | Lista tarjetas guardadas ocultando datos sensibles. |
| `delete_card` | Async | card_id, user_id | Éxito | Elimina un método de pago de la cuenta. |
| `select_card` | Async | card_id, user_id | Éxito | Marca una tarjeta como predeterminada. |
| `user_referral_details` | Async | user_id | Código referido | Retorna código de referido y estadísticas de uso. |
| `get_wallet_history` | Async | user_id | Array transacciones | Muestra ingresos y egresos de la billetera virtual. |
| `add_wallet_amount` | Async | amount, card_id | Nuevo balance | Recarga saldo mediante tarjeta registrada. |
| `change_password` | Async | old_password, new_password | Éxito | Cambia la contraseña validando la anterior. |
| `verify_referral_code` | Async | referral_code | Datos referente | Valida un código de referido (registro o post-registro). |
| `get_user_setting` | Async | user_id | Configuración | Retorna las preferencias del usuario. |
| `update_user_setting` | Async | user_id, settings | Éxito | Actualiza las preferencias globales del usuario. |
| `get_nearby_providers` | Async | lat, long, service_id | Lista conductores | Busca conductores activos en el radio cercano para el mapa. |
| `add_emergency_contact` | Async | name, phone | Contacto creado | Registra un nuevo contacto para funciones SOS. |
| `get_emergency_contact` | Async | user_id | Lista contactos | Retorna los contactos de emergencia guardados. |
| `delete_emergency_contact` | Async | contact_id | Éxito | Elimina un contacto de la lista de emergencia. |
| `user_forgot_password_verify` | Async | email, otp | Éxito | Verifica que el código OTP del correo sea correcto. |
| `user_reset_password` | Async | new_password, email | Éxito | Establece nueva contraseña tras recuperación. |
| `user_otp_verification` | Async | otp, phone | Éxito | Valida el teléfono del usuario mediante SMS OTP. |
| `resend_user_otp` | Async | phone, email | Mensaje enviado | Reenvía el código de verificación por SMS o Email. |
| `get_user_document_list` | Async | user_id | Lista documentos | Lista documentos requeridos para validación de identidad. |
| `upload_user_document` | Async | document_id, file | Documento guardado | Sube archivos de identidad al servidor. |
| `get_city_list` | Async | country_id | Array ciudades | Lista ciudades operativas por país. |
| `get_country_list` | Async | N/A | Array países | Lista todos los países habilitados en el sistema. |
| `get_service_list` | Async | city_id | Tipos servicios | Retorna vehículos/servicios disponibles en una ciudad. |
| `add_favourite_address` | Async | address_name, lat, long | Dirección guardada | Guarda lugares frecuentes (Casa, Oficina, etc.). |
| `delete_favourite_address` | Async | address_id | Éxito | Elimina una dirección favorita. |
| `get_favourite_address` | Async | user_id | Lista direcciones | Retorna todas las direcciones guardadas del usuario. |
| `user_submit_invoice` | Async | trip_id, tip | Éxito | Procesa factura pendiente o añade propina. |
| `check_destination_zone` | Async | lat, long | ID de Zona | Verifica si un punto pertenece a una zona tarifaria especial. |
| `get_split_payment_users` | Async | phone_numbers | Lista usuarios | Busca usuarios registrados para dividir pago (Split). |
| `send_split_request` | Async | trip_id, users | Notificación | Envía invitaciones de pago compartido. |
| `pay_wallet_payment` | Async | amount, user_id | Resultado pago | Procesa pago exclusivo con saldo de billetera. |
| `get_courier_estimation` | Async | details, stops | Estima Courier | Cálculo para mensajería con múltiples paradas. |
| `user_get_messages` | Async | trip_id | Array mensajes | Recupera chat entre cliente y soporte/conductor. |
| `set_home_work_address` | Async | type, address, lat | Éxito | Configuración rápida de Casa o Trabajo. |
| `get_promotions` | Async | city_id | Lista promociones | Muestra banners o campañas activas en la ciudad. |
| `check_user_status` | Sync | user_id | Status Code | Verifica si el usuario está aprobado o bloqueado. |
| `update_user_location` | Async | lat, long, user_id | Éxito | Actualiza posición GPS previo al viaje. |
| `get_all_reviews` | Async | user_id | Array reviews | Lista comentarios y estrellas recibidos por el usuario. |
| `toggle_marketing_email` | Async | status, user_id | Éxito | Suscripción o baja de correos de marketing. |
| `get_invoice_detail` | Async | trip_id | Objeto factura | Desglose legal de impuestos y cargos. |
| `validate_user_token` | Sync | user_id, token | Boolean | Validación interna de seguridad de sesión. |
| `get_total_stats` | Async | user_id | Estadísticas | Retorna total viajes, km recorridos y gasto total. |
| `getNewPricing` | Async | body, city_type | Modelo precio | Determina modelo de cobro (mensajería vs viaje). |
| `calculateCityWisePricing`| Async | params | Precio final | Ajusta precio basado en la ciudad detectada. |
| `getCoordinatesPickDest`| Sync | flow_type, coords | Lat/Lng | Extrae coordenadas según el tipo de flujo. |
| `get_user_referral_code`| Async | user_id | Código | Recupera específicamente el código alfanumérico. |
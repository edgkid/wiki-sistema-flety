# Archivo: `Util.js`

## Descripción General
Este controlador centraliza los recursos utilitarios que permiten la comunicación, validación y procesamiento en general (y en segundo plano) necesarios para llevar a cabo la lógica de la plataforma.

---

## 1. Validaciones y Seguridad

| Función                          | Tipo  | Entrada            | Salida          | Descripción                                                           |
| :------------------------------- | :---- | :----------------- | :-------------- | :-------------------------------------------------------------------- |
| `check_request_params`           | Sync  | body, params_array | Callback        | Valida campos requeridos en `req.body` antes de procesar una ruta.    |
| `check_request_params_async`     | Async | body, params_array | Response        | Versión asíncrona de la validación de parámetros.                     |
| `check_request_params_for_admin` | Sync  | body, params       | Boolean         | Validación de parámetros específica para el panel web administrativo. |
| `encryptPassword`                | Sync  | password           | Hash String     | Encripta contraseñas usando algoritmos de hash seguros.               |
| `generate_token`                 | Sync  | length             | Alphanumeric    | Genera tokens aleatorios para sesiones.                               |
| `create_admin_token`             | Sync  | admin_data         | JWT Token       | Genera tokens JSON Web para la autenticación del administrador.       |
| `verify_admin_token`             | Sync  | token              | Decoded Payload | Valida la autenticidad y expiración de un token de admin.             |
| `verify_user_token`              | Async | user_id, token     | Boolean         | Valida la vigencia del token de un usuario.                           |
| `verify_provider_token`          | Async | provider_id, token | Boolean         | Valida la vigencia del token de un conductor.                         |
| `validate_email_format`          | Sync  | email              | Boolean         | Validación por Regex del formato de correo electrónico.               |
| `validate_user_token`            | Sync  | user_id, token     | Boolean         | Función interna de seguridad de sesión.                               |

## 2. Comunicaciones y Notificaciones

| Función                        | Tipo  | Entrada        | Salida       | Descripción                                                      |
| :----------------------------- | :---- | :------------- | :----------- | :--------------------------------------------------------------- |
| `sendEmail`                    | Async | options        | Info envío   | Configura y envía correos electrónicos (Nodemailer).             |
| `send_email_with_attachment`   | Async | options, file  | Info envío   | Envía correos electrónicos con archivos adjuntos.                |
| `sendSMS`                      | Async | phone, message | Status       | Envía mensajes de texto a través de proveedores (ej. Twilio).    |
| `send_direct_sms`              | Async | phone, content | Status       | Envío directo de SMS saltando colas de procesamiento.            |
| `sendPushNotification`         | Async | token, payload | Confirmación | Envía notificaciones push a dispositivos Android e iOS.          |
| `send_notification_to_all`     | Async | title, message | Éxito        | Envía notificación push masiva a todos los usuarios/conductores. |
| `send_web_push`                | Async | sub, msg       | Status       | Envía notificaciones push específicas para navegadores web.      |
| `send_expo_push_notification`  | Async | token, data    | Status       | Envía notificaciones a través del servicio de Expo.              |
| `send_socket_message`          | Sync  | event, data    | Emit         | Envía mensajes personalizados a través de WebSockets.            |
| `update_request_status_socket` | Sync  | trip_id        | Emit Event   | Notifica cambios de estado de viaje en tiempo real vía Socket.   |

## 3. Geolocalización y Mapas

| Función | Tipo | Entrada | Salida | Descripción |
| :--- | :--- | :--- | :--- | :--- |
| `check_city_with_location` | Async | lat, long | Objeto City | Identifica en qué ciudad se encuentran las coordenadas dadas. |
| `get_nearby_city` | Async | lat, lng | City | Busca la ciudad más cercana si no hay coincidencia exacta. |
| `check_zone_with_location` | Async | lat, lng, city_id | Objeto Zone | Determina si un punto está dentro de una zona específica. |
| `get_distance_time` | Async | origin, dest | {dist, time} | Consulta Google Maps Matrix API para distancia y tiempo. |
| `get_google_path` | Async | origin, dest | Poliline | Obtiene la ruta trazada punto a punto (Google API). |
| `get_google_address` | Async | lat, lng | Address | Realiza geocodificación inversa (Coordenadas a Dirección). |
| `is_point_in_polygon` | Sync | point, polygon | Boolean | Algoritmo geométrico para validar ubicación en una zona. |
| `get_distance_between_points` | Sync | p1, p2 | Metros/KM | Cálculo de distancia lineal entre dos puntos. |

## 4. Gestión de Archivos e Imágenes

| Función | Tipo | Entrada | Salida | Descripción |
| :--- | :--- | :--- | :--- | :--- |
| `upload_image` | Async | path, name | URL | Gestiona la carga de archivos al servidor o a AWS S3. |
| `delete_image` | Sync | image_url | Éxito/Error | Elimina físicamente archivos para ahorrar espacio. |
| `image_resize` | Async | path, size | Resized Image | Optimiza el tamaño de fotos de perfil. |
| `get_file_extension` | Sync | filename | Extension | Extrae la extensión de un archivo (jpg, png, etc). |
| `check_file_exists` | Sync | path | Boolean | Verifica la existencia de un recurso físico en disco. |
| `copy_file` | Sync | source, dest | Éxito | Duplica archivos en el sistema. |
| `move_file` | Sync | source, dest | Éxito | Mueve archivos entre directorios. |

## 5. Finanzas y Wallet

| Función | Tipo | Entrada | Salida | Descripción |
| :--- | :--- | :--- | :--- | :--- |
| `add_wallet_history` | Async | user_id, amount | Registro | Registra transacciones en la billetera del usuario. |
| `add_wallet_history_for_admin` | Async | admin_id, data | Registro | Registra movimientos manuales hechos por el administrador. |
| `get_user_wallet_balance` | Async | user_id | Amount | Consulta rápida del saldo del usuario. |
| `get_provider_wallet_balance`| Async | provider_id | Amount | Consulta rápida del saldo del conductor. |
| `calculate_tax` | Sync | amount, percent | Tax Value | Calcula el impuesto sobre la tarifa base. |
| `save_transfer_history` | Async | data | Record | Registra transferencias bancarias en el sistema. |
| `format_currency` | Sync | amount, symbol | String | Formatea moneda según configuración local. |

## 6. Otros Utilitarios (Helpers)

| Función | Tipo | Entrada | Salida | Descripción |
| :--- | :--- | :--- | :--- | :--- |
| `error_response` | Sync | res, code | JSON | Estandariza la respuesta de error para el cliente. |
| `success_response` | Sync | res, code | JSON | Estandariza la respuesta de éxito para el cliente. |
| `generate_otp` | Sync | N/A | 4-6 Digit Code | Crea códigos de un solo uso para validación telefónica. |
| `convert_timezone` | Sync | date, timezone | Date String | Ajusta fecha/hora a la zona horaria local. |
| `get_date_format` | Sync | date | Formatted Str | Formatea fechas para facturas y reportes. |
| `convert_to_pdf` | Async | html_content | PDF Buffer | Transforma plantillas HTML en archivos PDF (Facturación). |
| `parse_json_safe` | Sync | string | Object | Parsea JSON evitando excepciones si es inválido. |
| `get_unique_id` | Sync | N/A | Unique String | Genera un identificador único universal (UUID). |
| `get_random_id` | Sync | N/A | Number | Genera un ID numérico aleatorio. |
| `log_system_error` | Sync | error, module | File Log | Escribe errores en los logs del sistema para depuración. |
| `check_app_version` | Sync | type, version | Status | Valida si la app requiere actualización obligatoria. |
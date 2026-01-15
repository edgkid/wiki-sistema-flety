La capa de **Models** ( `models/` ) encapsula la estructura de los datos y  definición de  entidades del sistema. Su función principal es establecer el esquema de las colecciones en MongoDB a través de Mongoose, aquí se soporta la integridad y persistencia de la información.

### Responsabilidades clave:

- **Definición de Esquemas:** Se establecen los campos, tipos de datos y estructuras de los documentos.
- **Validación de Integridad:** Garantiza que los datos cumplan con las reglas de formato (requeridos, únicos y tipos) antes de ser persistidos.
- **Abstracción de Datos:** Permite que los **Services** interactúen con la base de datos mediante objetos de JavaScript, ocultando la complejidad de las consultas directas.
- **Relaciones entre colecciones:** Gestiona los vínculos entre entidades 

A continuación se describen los modelos existentes en la fuente del sistema.

### Modelo - Admin_settings.js

**Descripción:**
Este modelo representa la entidad central de configuración del sistema (Settings). Su objetivo es almacenar todas las variables globales, llaves de APIs de terceros (Google, AWS, Stripe, Twilio), configuraciones de negocio y preferencias de la plataforma.

| Campo                                        | Tipo     | Default            | Descripción                        |
| :------------------------------------------- | :------- | :----------------- | :--------------------------------- |
| `provider_timeout`                           | Number   | 60                 | Tiempo de espera del proveedor     |
| `countryname`                                | String   | ""                 | Nombre del país                    |
| `adminCurrencyCode`                          | String   | ""                 | Código de moneda del admin         |
| `adminCurrency`                              | String   | ""                 | Símbolo de moneda del admin        |
| `adminTimeZone`                              | String   | ""                 | Zona horaria del administrador     |
| `sms_notification`                           | Boolean  | false              | Notificaciones por SMS activas     |
| `email_notification`                         | Boolean  | false              | Notificaciones por Email activas   |
| `push_notification`                          | Boolean  | false              | Notificaciones Push activas        |
| `get_referral_profit_on_card_payment`        | Boolean  | false              | Ganancia referido en pago tarjeta  |
| `get_referral_profit_on_cash_payment`        | Boolean  | false              | Ganancia referido en pago efectivo |
| `userEmailVerification`                      | Boolean  | false              | Verificar email de usuario         |
| `providerEmailVerification`                  | Boolean  | false              | Verificar email de proveedor       |
| `userSms`                                    | Boolean  | false              | SMS para usuarios                  |
| `providerSms`                                | Boolean  | false              | SMS para proveedores               |
| `admin_phone`                                | String   | ""                 | Teléfono del administrador         |
| `contactUsEmail`                             | String   | ""                 | Email de contacto                  |
| `twilio_call_masking`                        | Boolean  | false              | Enmascaramiento de llamadas Twilio |
| `access_key_id`                              | String   | ""                 | AWS Access Key ID                  |
| `secret_key_id`                              | String   | ""                 | AWS Secret Key ID                  |
| `aws_bucket_name`                            | String   | ""                 | Nombre del bucket de AWS           |
| `is_use_aws_bucket`                          | Boolean  | false              | Uso de bucket AWS activo           |
| `image_base_url`                             | String   | ""                 | URL base para imágenes             |
| `is_ride_share`                              | Boolean  | false              | Viajes compartidos activos         |
| `is_split_payment`                           | Boolean  | false              | Pago dividido activo               |
| `max_split_user`                             | Number   | 5                  | Máximo de usuarios en split        |
| `admin_email`                                | String   | ""                 | Correo del administrador           |
| `default_Search_radious`                     | Number   | 100                | Radio de búsqueda por defecto      |
| `scheduled_request_pre_start_minute`         | Number   | 30                 | Minutos antes de viaje programado  |
| `scheduled_request_day_limit`                | Number   | 3                  | Límite de días para programar      |
| `number_of_try_for_scheduled_request`        | Number   | 1                  | Intentos para viajes programados   |
| `is_public_demo`                             | Boolean  | false              | Modo demo pública                  |
| `is_provider_initiate_trip`                  | Boolean  | false              | Proveedor inicia el viaje          |
| `stripe_secret_key`                          | String   | ""                 | Clave secreta de Stripe            |
| `stripe_publishable_key`                     | String   | ""                 | Clave pública de Stripe            |
| `paystack_secret_key`                        | String   | ""                 | Clave secreta de Paystack          |
| `paystack_publishable_key`                   | String   | ""                 | Clave pública de Paystack          |
| `payu_key`                                   | String   | ""                 | Clave de PayU                      |
| `payu_salt`                                  | String   | ""                 | Salt de PayU                       |
| `payment_gateway_type`                       | Number   | 10                 | Tipo de pasarela de pago           |
| `email`                                      | String   | ""                 | Correo base                        |
| `password`                                   | String   | ""                 | Contraseña base                    |
| `domain`                                     | String   | -                  | Dominio                            |
| `provider_offline_min`                       | Number   | 30                 | Minutos para offline de proveedor  |
| `smtp_host`                                  | String   | ""                 | Host del servidor SMTP             |
| `smtp_port`                                  | String   | ""                 | Puerto del servidor SMTP           |
| `is_show_estimation_in_provider_app`         | Boolean  | false              | Mostrar estimado en App Proveedor  |
| `is_show_estimation_in_user_app`             | Boolean  | false              | Mostrar estimado en App Usuario    |
| `twilio_account_sid`                         | String   | ""                 | Twilio Account SID                 |
| `twilio_auth_token`                          | String   | ""                 | Twilio Auth Token                  |
| `twilio_number`                              | String   | ""                 | Número de Twilio                   |
| `twiml_url`                                  | String   | ""                 | URL de TwiML                       |
| `userPath`                                   | Boolean  | false              | Ruta de usuario activa             |
| `providerPath`                               | Boolean  | false              | Ruta de proveedor activa           |
| `android_client_app_url`                     | String   | ""                 | URL Play Store Cliente             |
| `android_driver_app_url`                     | String   | ""                 | URL Play Store Conductor           |
| `ios_client_app_url`                         | String   | ""                 | URL App Store Cliente              |
| `ios_driver_app_url`                         | String   | ""                 | URL App Store Conductor            |
| `find_nearest_driver_type`                   | Number   | 1                  | Algoritmo búsqueda conductor       |
| `request_send_to_no_of_providers`            | Number   | 2                  | Cantidad proveedores a notificar   |
| `android_user_app_gcm_key`                   | String   | ""                 | GCM Key Android Usuario            |
| `android_provider_app_gcm_key`               | String   | ""                 | GCM Key Android Proveedor          |
| `android_user_app_google_key`                | String   | ""                 | Google Key Android Usuario         |
| `android_provider_app_google_key`            | String   | ""                 | Google Key Android Proveedor       |
| `ios_user_app_google_key`                    | String   | ""                 | Google Key iOS Usuario             |
| `ios_provider_app_google_key`                | String   | ""                 | Google Key iOS Proveedor           |
| `web_app_google_key`                         | String   | ""                 | Google Key Web App                 |
| `road_api_google_key`                        | String   | ""                 | Google Road API Key                |
| `backend_google_key`                         | String   | ""                 | Google Backend Key                 |
| `user_passphrase`                            | String   | ""                 | Frase de paso Usuario              |
| `provider_passphrase`                        | String   | ""                 | Frase de paso Proveedor            |
| `ios_certificate_mode`                       | String   | ""                 | Modo certificado iOS               |
| `hotline_app_id`                             | String   | ""                 | Hotline App ID                     |
| `hotline_app_key`                            | String   | ""                 | Hotline App Key                    |
| `google_map_lic_key`                         | String   | ""                 | Google Maps License Key            |
| `is_google_map_lic_key_expired`              | Number   | 0                  | Estado expiración licencia mapas   |
| `server_url`                                 | String   | ""                 | URL del servidor                   |
| `app_name`                                   | String   | "FLETY"            | Nombre de la aplicación            |
| `partner_panel_name`                         | String   | "Partner Panel"    | Nombre panel de socios             |
| `dispatcher_panel_name`                      | String   | "Dispatcher Panel" | Nombre panel de despachador        |
| `hotel_panel_name`                           | String   | "Hotel Panel"      | Nombre panel de hoteles            |
| `corporate_panel_name`                       | String   | "Corporate Panel"  | Nombre panel corporativo           |
| `is_tip`                                     | Boolean  | false              | Propinas activas                   |
| `is_toll`                                    | Boolean  | false              | Peajes activos                     |
| `timezone_for_display_date`                  | String   | ""                 | Zona horaria para visualización    |
| `android_user_app_version_code`              | String   | ""                 | Versión App Android Usuario        |
| `android_user_app_force_update`              | Boolean  | false              | Forzar actualización Android User  |
| `android_provider_app_version_code`          | String   | ""                 | Versión App Android Proveedor      |
| `android_provider_app_force_update`          | Boolean  | false              | Forzar actualización Android Prov  |
| `ios_user_app_version_code`                  | String   | ""                 | Versión App iOS Usuario            |
| `ios_user_app_force_update`                  | Boolean  | false              | Forzar actualización iOS User      |
| `ios_provider_app_version_code`              | String   | ""                 | Versión App iOS Proveedor          |
| `ios_provider_app_force_update`              | Boolean  | false              | Forzar actualización iOS Prov      |
| `is_debug_log`                               | Boolean  | true               | Logs de depuración activos         |
| `location`                                   | [Number] | index 2d           | Coordenadas geoespaciales          |
| `firebase_apiKey`                            | String   | ""                 | Firebase API Key                   |
| `firebase_authDomain`                        | String   | ""                 | Firebase Auth Domain               |
| `firebase_databaseURL`                       | String   | ""                 | Firebase Database URL              |
| `firebase_projectId`                         | String   | ""                 | Firebase Project ID                |
| `firebase_storageBucket`                     | String   | ""                 | Firebase Storage Bucket            |
| `firebase_messagingSenderId`                 | String   | ""                 | Firebase Messaging Sender ID       |
| `user_terms_and_condition`                   | String   | ""                 | Términos y condiciones Usuario     |
| `provider_terms_and_condition`               | String   | ""                 | Términos y condiciones Proveedor   |
| `user_privacy_policy`                        | String   | ""                 | Política de privacidad Usuario     |
| `provider_privacy_policy`                    | String   | ""                 | Política de privacidad Proveedor   |
| `android_places_autocomplete_key`            | String   | ""                 | Key Autocomplete Android           |
| `ios_places_autocomplete_key`                | String   | ""                 | Key Autocomplete iOS               |
| `team_id`                                    | String   | ""                 | Team ID (Apple)                    |
| `key_id`                                     | String   | ""                 | Key ID (Apple)                     |
| `provider_bundle_id`                         | String   | ""                 | Bundle ID Proveedor                |
| `user_bundle_id`                             | String   | ""                 | Bundle ID Usuario                  |
| `type`                                       | String   | ""                 | Tipo (Firebase Security)           |
| `private_key_id`                             | String   | ""                 | Private Key ID Firebase            |
| `private_key`                                | String   | ""                 | Private Key Firebase               |
| `client_email`                               | String   | ""                 | Client Email Firebase              |
| `client_id`                                  | String   | ""                 | Client ID Firebase                 |
| `auth_uri`                                   | String   | ""                 | Auth URI Firebase                  |
| `token_uri`                                  | String   | ""                 | Token URI Firebase                 |
| `auth_provider_x509_cert_url`                | String   | ""                 | Cert URL Auth Firebase             |
| `client_x509_cert_url`                       | String   | ""                 | Cert URL Client Firebase           |
| `is_user_social_login`                       | Boolean  | true               | Login social usuario activo        |
| `is_provider_social_login`                   | Boolean  | true               | Login social proveedor activo      |
| `is_guest_token`                             | Boolean  | false              | Token de invitado activo           |
| `is_otp_verification_start_trip`             | Boolean  | false              | Verificar viaje con OTP            |
| `is_receive_new_request_near_destination`    | Boolean  | false              | Recibir pedidos cerca de destino   |
| `near_destination_radius`                    | Number   | 2000               | Radio cerca de destino (metros)    |
| `is_driver_go_home`                          | Boolean  | false              | Función "Ir a casa" activa         |
| `is_driver_go_home_change_address`           | Boolean  | false              | Cambiar dirección de casa          |
| `driver_go_home_radius`                      | Number   | 2000               | Radio para "Ir a casa"             |
| `is_allow_multiple_stop`                     | Boolean  | false              | Múltiples paradas permitidas       |
| `is_multiple_stop_waiting_free_on_each_stop` | Boolean  | false              | Espera gratis en cada parada       |
| `multiple_stop_count`                        | Number   | 3                  | Cantidad de paradas máximas        |
| `is_allow_ride_share`                        | Boolean  | false              | Permitir compartir viaje           |
| `ride_share_pickup_radius`                   | Number   | 3                  | Radio recogida compartido          |
| `ride_share_destination_radius`              | Number   | 3                  | Radio destino compartido           |
| `minimum_phone_number_length`                | Number   | 8                  | Largo mín. de teléfono             |
| `maximum_phone_number_length`                | Number   | 14                 | Largo máx. de teléfono             |
| `email_list_trip_notifiy`                    | Array    | []                 | Lista correos notif. viajes        |
| `base_url`                                   | String   | ""                 | URL base del sistema               |
| `webpush_public_key`                         | String   | ""                 | Webpush Public Key                 |
| `webpush_private_key`                        | String   | ""                 | Webpush Private Key                |
| `server_type`                                | Number   | 2                  | 1-Live, 2-Dev                      |
| `connectium_key`                             | String   | ""                 | Connectium Key                     |
| `connectium_base_url`                        | String   | ""                 | Connectium Base URL                |
| `connectium_short_code`                      | String   | ""                 | Connectium Short Code              |
| `connectium_dlr`                             | String   | ""                 | Connectium DLR                     |
| `connectium_dlr_level`                       | Number   | -                  | Connectium DLR Level               |
| `connectium_dlr_webhook_url`                 | String   | ""                 | Webhook DLR Connectium             |
| `stop_threshold`                             | Number   | 50                 | Umbral de parada                   |
| `emails_notify_registration_data`            | Array    | []                 | Emails para datos diarios reg.     |
| `tracking_link_sms`                          | Boolean  | false              | Link de rastreo por SMS            |
| `landing_page_url`                           | String   | ""                 | URL Landing Page                   |
| `user_app_insta_ad_url`                      | String   | ""                 | URL Ad Instagram Usuario           |
| `driver_app_insta_ad_url`                    | String   | ""                 | URL Ad Instagram Conductor         |
| `advertise_urls`                             | Array    | []                 | URLs de publicidad                 |
### Modelo - Admin.js

**Descripción:**
Este modelo representa la entidad que registra los usuarios con privilegios administrativos.

| Campo                | Tipo     | Default  | Descripción                                                              |
| :------------------- | :------- | :------- | :----------------------------------------------------------------------- |
| `username`           | String   | ""       | Nombre de usuario.                                                       |
| `password`           | String   | ""       | Contraseña                                                               |
| `email`              | String   | ""       | Correo electrónico                                                       |
| `token`              | String   | ""       | Token de sesión para la autenticación en peticiones API.                 |
| `type`               | Number   | 0        | Identificador numérico del rol                                           |
| `url_array`          | Array    | []       | Lista de rutas o permisos específicos a los que el usuario tiene acceso. |
| `created_at`         | Date     | Date.now | Fecha y hora de creación del registro.                                   |
| `updated_at`         | Date     | Date.now | Fecha y hora de la última modificación del registro.                     |
| `uid`                | String   | -        |                                                                          |
| `country_phone_code` | String   | ""       | Código telefónico del país                                               |
| `country_id`         | ObjectId | -        |                                                                          |
| `super_admin`        | Number   | -        | Flag numérico para identificar si posee privilegios de Super Usuario.    |

### Modelo - Airport.js

**Descripción:**
Este modelo define la estructura de zonas dentro de la plataforma y permite que el sistema reconozca cuándo un viaje inicia o termina dentro del perímetro  comercial de un aeropuerto para aplicar tarifas.

| Campo            | Tipo     | Default  | Descripción                                                                                             |
| :--------------- | :------- | :------- | :------------------------------------------------------------------------------------------------------ |
| `city_id`        | ObjectId | -        | Referencia al modelo City                                                                               |
| `title`          | String   | ""       | Nombre                                                                                                  |
| `kmlzone`        | Array    | -        | Arreglo de coordenadas que definen el polígono de la geocerca. Indexado en 3d para cálculos espaciales. |
| `styleUrl`       | String   | ""       | Referencia del estilo visual del mapa                                                                   |
| `styleHash`      | String   | ""       |                                                                                                         |
| `description`    | String   | ""       | Información adicional                                                                                   |
| `stroke`         | String   | ""       |                                                                                                         |
| `stroke_opacity` | Number   | 0        |                                                                                                         |
| `stroke_width`   | Number   | 0        |                                                                                                         |
| `fill`           | String   | ""       |                                                                                                         |
| `fill_opacity`   | Number   | 0        |                                                                                                         |
| `created_at`     | Date     | Date.now | Fecha de registro                                                                                       |
| `updated_at`     | Date     | Date.now | Fecha de la última actualización                                                                        |
### Modelo - AirportToCity.js

**Descripción:**
Este modelo representa una entidad para la gestión de tarifas planas. 

| Campo             | Tipo     | Default  | Descripción                                                         |
| :---------------- | :------- | :------- | :------------------------------------------------------------------ |
| `city_id`         | ObjectId | -        | Referencia al identificador único de la ciudad.                     |
| `airport_id`      | ObjectId | -        | Referencia al identificador único del aeropuerto.                   |
| `price`           | Number   | 0        | Precio del trayecto o servicio entre el aeropuerto y la ciudad.     |
| `service_type_id` | ObjectId | -        | Referencia al tipo de servicio asociado (ej: estándar, lujo, etc.). |
| `created_at`      | Date     | Date.now | Fecha y hora en la que se creó el registro de vinculación.          |
| `updated_at`      | Date     | Date.now | Fecha y hora de la última actualización del registro.               |
### Modelo - Api_Partners.js

**Descripción:**
Este modelo define la estructura encargada de soportar el acceso de terceros mediante API, a través de la vinculación de un tercero  con un token de autenticación único.

| Campo       | Tipo     | Requerido | Descripción                                                              |
| :---------- | :------- | :-------- | :----------------------------------------------------------------------- |
| `_id`       | ObjectId | **Sí**    | Identificador único del registro                                         |
| `name`      | String   | **Sí**    | Nombre identificador de tercero                                          |
| `token`     | String   | **Sí**    | Llave de acceso secreta y única para autenticar las peticiones a la API. |
| `createdAt` | Date     | -         | Fecha de creación del registro                                           |
| `updatedAt` | Date     | -         | Fecha de la última modificación                                          |
### Modelo - Bank_Detail.js

**Descripción:**
Este modelo define la estructura para almacenar información alusiva a banca.

| Campo                      | Tipo     | Descripción                                       |
| :------------------------- | :------- | :------------------------------------------------ |
| `bank_holder_type`         | Number   | Define  dueño de la cuenta                        |
| `bank_holder_id`           | ObjectId | Referencia al ID del modelo correspondiente       |
| `unique_id`                | Number   | Identificador numérico incremental                |
| `bank_name`                | String   | Nombre de la institución financiera.              |
| `bank_branch`              | String   | Sucursal  bancaria donde está radicada la cuenta. |
| `bank_account_number`      | String   | Número de cuenta bancaria.                        |
| `bank_account_holder_name` | String   | Nombre del titular de la cuenta                   |
| `bank_beneficiary_address` | String   | Dirección física del beneficiario                 |
| `bank_unique_code`         | String   | Código de identificación bancaria nacional        |
| `bank_swift_code`          | String   | Código internacional                              |
| `is_updated`               | Number   |                                                   |
| `created_at`               | Date     | Fecha de registro.                                |
| `updated_at`               | Date     | Fecha de la última actualización.                 |
### Modelo - Card.js

**Descripción:**
Este modelo representa los la entidad de método  vinculados a los usuarios. 

| Campo                  | Tipo     | Default  | Descripción                                                                |
| :--------------------- | :------- | :------- | :------------------------------------------------------------------------- |
| `payment_method`       | String   | ""       | Token o ID del método de pago devuelto por la pasarela (ej: Stripe Token). |
| `card_type`            | String   | ""       | Franquicia de la tarjeta (ej: Visa, MasterCard, American Express).         |
| `user_id`              | ObjectId | -        | Referencia al ID del modelo User propietario de la tarjeta.                |
| `last_four`            | String   | ""       | Los últimos 4 dígitos de la tarjeta para visualización segura.             |
| `customer_id`          | String   | ""       | Identificador del cliente en la pasarela de pago (ej: Stripe Customer ID). |
| `is_default`           | Number   | 0        | Flag para indicar si es la tarjeta principal (1 = Predeterminada, 0 = No). |
| `payment_gateway_type` | Number   | 10       | Define la pasarela asociada (ej: 10 para Stripe, según Settings).          |
| `type`                 | Number   | -        | Define el rol del dueño de la tarjeta (ej: Usuario o Proveedor).           |
| `created_at`           | Date     | Date.now | Fecha de vinculación del método de pago.                                   |
| `updated_at`           | Date     | Date.now | Fecha de la última actualización del registro.                             |
### Modelo - City.js

**Descripción:**
Este modelo gestiona la entidad de ciudades. la información presente  permite determinar;  qué métodos de pago están permitidos y qué tipos de servicios están activos.

| Campo                        | Tipo       | Default  | Descripción                                                         |
| :--------------------------- | :--------- | :------- | :------------------------------------------------------------------ |
| `countryid`                  | ObjectId   | -        | Referencia al modelo Country.                                       |
| `countryname`                | String     | ""       | Nombre del país al que pertenece la ciudad.                         |
| `cityname`                   | String     | ""       | Nombre corto de la ciudad.                                          |
| `full_cityname`              | String     | ""       | Nombre completo (incluyendo estado/provincia).                      |
| `timezone`                   | String     | ""       | Zona horaria específica de la ciudad.                               |
| `is_use_city_boundary`       | Boolean    | false    | Indica si se debe validar que el viaje esté dentro de los límites.  |
| `city_locations`             | Array      | []       | Coordenadas que definen el polígono de la ciudad (Index 3D).        |
| `cityLatLong`                | [Number]   | -        | Coordenadas centrales (Lat/Long) para geolocalización (Index 2D).   |
| `cityRadius`                 | Number     | 50       | Radio operativo en kilómetros desde el centro.                      |
| `unit`                       | Number     | 1        | Unidad de medida (1: Millas, 2: Kilómetros).                        |
| `isBusiness`                 | Number     | 1        | Indica si la ciudad está activa para el negocio globalmente.        |
| `city_business`              | Number     | 1        | Flag para habilitar operaciones estándar en la ciudad.              |
| `airport_business`           | Number     | 1        | Flag para habilitar servicios desde/hacia aeropuertos.              |
| `zone_business`              | Number     | 1        | Flag para habilitar servicios por zonas específicas.                |
| `is_payment_mode_cash`       | Number     | 1        | Permite pagos en efectivo en esta ciudad (1: Sí, 0: No).            |
| `is_payment_mode_card`       | Number     | 1        | Permite pagos con tarjeta en esta ciudad.                           |
| `is_payment_mode_apple_pay`  | Number     | 0        | Permite Apple Pay.                                                  |
| `isPromoApplyForCash`        | Number     | 1        | Permite usar códigos promocionales en viajes en efectivo.           |
| `isPromoApplyForCard`        | Number     | 1        | Permite usar códigos promocionales en viajes con tarjeta.           |
| `destination_city`           | [ObjectId] | []       | Lista de IDs de otras ciudades permitidas como destino.             |
| `is_ask_user_for_fixed_fare` | Boolean    | false    | Pregunta al usuario si desea una tarifa fija antes de pedir.        |
| `is_caracas`                 | Boolean    | false    | Flag específico para lógica personalizada en la ciudad de Caracas.  |
| `main_city`                  | Number     | -        | Identificador de jerarquía si la ciudad es una capital o principal. |
| `created_at`                 | Date       | Date.now | Fecha de creación del registro.                                     |
| `updated_at`                 | Date       | Date.now | Fecha de la última actualización.                                   |
### Modelo - City_To_City.js

**Descripción:**
Este modelo funciona como una matriz de tarifas para viajes **interurbanos**. Mediante el presente modelo se puede definir un precio fijo para trayectos que conectan una ciudad de origen con una ciudad de destino específica

| Campo                 | Tipo     | Default  | Descripción                                      |
| :-------------------- | :------- | :------- | :----------------------------------------------- |
| `city_id`             | ObjectId | -        |                                                  |
| `destination_city_id` | ObjectId | -        |                                                  |
| `price`               | Number   | 0        | Tarifa plana asignada al trayecto entre ciudades |
| `service_type_id`     | ObjectId | -        | Referencia al modelo Service_Type                |
| `created_at`          | Date     | Date.now | Fecha de creación                                |
| `updated_at`          | Date     | Date.now | Fecha de la última actualización                 |
### Modelo - City_Type.js

**Descripción:**
Este modelo permite definir la configuración de precios para un tipo de servicio  dentro de una ciudad determinada.

| Campo                                     | Tipo              | Default  | Descripción                                                        |
| :---------------------------------------- | :---------------- | :------- | :----------------------------------------------------------------- |
| `countryid` / `countryname`               | ObjectId / String | ""       | Referencia al País de operación                                    |
| `cityid` / `city_id` / `cityname`         | ObjectId / String | ""       | Referencia a la Ciudad donde aplica esta configuración de precios. |
| `typeid` / `typename`                     | ObjectId / String | ""       | Referencia al Tipo de Servicio                                     |
| `type_image`                              | String            | ""       | URL del icono o imagen del vehículo                                |
| `is_hide`                                 | Number            | 1        | Determina si el tipo de servicio es visible para los usuarios      |
| `is_business`                             | Number            | 1        | Flag de activación .                                               |
| `base_price`                              | Number            | 0        | Costo inicial fijo                                                 |
| `base_price_distance`                     | Number            | 0        | Distancia incluida dentro del precio base.                         |
| `base_price_time`                         | Number            | 0        | Tiempo incluido en precio base.                                    |
| `min_fare`                                | Number            | 0        | Tarifa mínima                                                      |
| `price_per_unit_distance`                 | Number            | 0        | Precio por unidad de distancia adicional.                          |
| `price_for_total_time`                    | Number            | 0        | Precio por minuto de duración del viaje.                           |
| `tax` / `user_tax` / `provider_tax`       | Number            | 0        | Porcentajes de impuestos aplicables                                |
| `provider_profit`                         | Number            | 0        | Margen de ganancia para el conductor.                              |
| `max_space`                               | Number            | 0        | Capacidad máxima de carga                                          |
| `cancellation_fee`                        | Number            | 0        | Cargo por cancelación de viaje.                                    |
| `is_surge_hours`                          | Number            | 0        | Activa el multiplicador por alta demanda                           |
| `surge_multiplier`                        | Number            | 0        |                                                                    |
| `surge_hours`                             | Array             | [...]    |                                                                    |
| `is_zone` / `zone_ids`                    | Number / Array    | 0 / []   | Define si el precio es por zonas                                   |
| `is_ride_share`                           | Number            | 0        | Habilita la modalidad de viaje compartido                          |
| `is_car_rental_business`                  | Number            | 0        |                                                                    |
| `car_rental_ids`                          | Array[ObjectId]   | []       |                                                                    |
| `waiting_time_start_after_minute`         | Number            | 0        |                                                                    |
| `price_for_waiting_time`                  | Number            | 0        | Costo por minuto de espera                                         |
| `waiting_time_multiple_stops`             | Number            | 0        |                                                                    |
| `price_for_waiting_time_multiple_stops`   | Number            | 0        |                                                                    |
| `model_type`                              | Number            | 0        |                                                                    |
| `cost_per_helper`                         | Number            | 0        |                                                                    |
| `cost_per_stop_inside_city`               | Number            | 0        | Cargo por parada adicional                                         |
| `cost_per_stop_outside_city`              | Number            | 0        | Cargo por parada adicional                                         |
| `free_stops`                              | Number            | 2        | Cantidad de paradas incluidas sin costo extra.                     |
| `cost_travel_insurance`                   | Number            | 0        | Costo del seguro de viaje/carga.                                   |
| `fixed_fees`                              | Number            | 0        | Cargos administrativos fijos                                       |
| `night_shift`                             | Number            | 0        | Recargo por horario nocturno.                                      |
| `ferry_ticket_price` / `ferry_flety_cost` | Number            | -        | Costos asociados a traslados en Ferry.                             |
| `boat_ticket`                             | Number            | 0        |                                                                    |
| `ti_internal_transit`                     | Number            | -        | Tarifa de tránsito interno                                         |
| `user_type` / `user_type_id`              | Number / ObjectId | 0        |                                                                    |
| `corporate_partner_profit_fees`           | Number            | -        | Comisión                                                           |
| `created_at` / `updated_at`               | Date              | Date.now | fecha de registro y fecha de actualización                         |
### Modelo - City_Zone.js

**Descripción:**
Este modelo representa la entidad permite definir áreas de alta demanda, zonas de recargo o áreas con reglas de despacho específicas. 

| Campo                          | Tipo            | Descripción                                                 |
| :----------------------------- | :-------------- | :---------------------------------------------------------- |
| `cityid`                       | ObjectId        | Referencia al modelo **City**                               |
| `cityname`                     | String          | Nombre de la ciudad                                         |
| `title`                        | String          | Nombre identificador de la zona                             |
| `kmlzone`                      | Array           |                                                             |
| `total_provider_in_zone_queue` | Array[ObjectId] | Lista  de proveedoresque están en espera dentro de una zona |
| `description`                  | String          | Notas adicionales sobre la zona                             |
| `styleUrl`                     | String          |                                                             |
| `styleHash`                    | String          |                                                             |
| `stroke`                       | String          |                                                             |
| `stroke_opacity`               | Number          |                                                             |
| `stroke_width`                 | Number          |                                                             |
| `fill`                         | String          |                                                             |
| `fill_opacity`                 | Number          |                                                             |
| `created_at`                   | Date            | Fecha de creación del registro.                             |
| `updated_at`                   | Date            | Fecha de la última modificación.                            |
### Modelo - Corporate.js

**Descripción:**
Este modelo representa permite la personalización de servicios

| Campo                          | Tipo              | Descripción                                                              |
| :----------------------------- | :---------------- | :----------------------------------------------------------------------- |
| `unique_id`                    | Number            | identificador de registro                                                |
| `company_name`                 | String            | Nombre  o razón social de la empresa.                                    |
| `rif`                          | String            | Registro de Información Fiscal                                           |
| `name`                         | String            | Nombre del contacto principal o administrador de la cuenta corporativa.  |
| `email`                        | String            | Correo electrónico corporativo                                           |
| `password`                     | String            | Contraseña                                                               |
| `country_phone_code` / `phone` | String            | Código de país y número telefónico principal.                            |
| `alt_phone`                    | String            | Número telefónico alternativo.                                           |
| `address`                      | String            | Dirección.                                                               |
| `country_id` / `country_name`  | ObjectId / String |                                                                          |
| `wallet`                       | Number            | Saldo disponible en la billetera corporativa                             |
| `wallet_currency_code`         | String            | Moneda en la que se gestiona la billetera                                |
| `is_approved`                  | Number            | Estado de verificación por el Admin                                      |
| `token`                        | String            | Token de sesión para autenticación en paneles web.                       |
| `refferal_code`                | String            | Código único para el sistema de referidos.                               |
| `is_own_service_type`          | Number            |                                                                          |
| `picture` / `rif_url`          | String            | URLs de imagen de perfil y documento RIF digitalizado.                   |
| `document_2`                   | String            | URL del Acta o Documento Constitutivo (PDF).                             |
| `is_trip_approve`              | Number            |                                                                          |
| `is_subcorporate_admin`        | Number            | Define si la entidad tiene permisos de administración sobre sub-cuentas. |
| `corporate_type_id`            | ObjectId          |                                                                          |
| `corporate_type_userid`        | ObjectId          |                                                                          |
| `url_array`                    | Array             | Lista de rutas y permisos de acceso                                      |
| `active_api` / `api_key`       | Boolean / String  | Habilita el acceso vía API y almacena la llave de integración.           |
| `is_hide_amount`               | Number            | Flag para ocultar montos de facturación                                  |
| `preliquidation`               | Number            | Configuración para procesos de cierre de facturación anticipada.         |
| `is_use_fixed_partner_profit`  | Number            | Determina si usa un margen de ganancia fijo                              |
| `is_damasco`                   | Number            |                                                                          |
| `allow_edit_trip`              | Number            | Permite o restringe la edición de datos de un viaje tras ser solicitado. |
| `customer_id` / `account_id`   | String            | Referencias de pasarelas de pago                                         |
| `created_at` / `updated_at`    | Date              | Marcas de tiempo de creación y última actualización.                     |
### Modelo - Country.js

**Descripción:**
El modelo define la identidad del país (nombre, bandera, códigos), y las reglas de validación de teléfonos, la moneda de intercambio, las pasarelas de pago disponibles y las políticas de bonos o configuración de tarifas.

| Campo                        | Tipo    | Default  | Descripción                                                        |
| :--------------------------- | :------ | :------- | :----------------------------------------------------------------- |
| `countryname`                | String  | ""       | Nombre oficial del país                                            |
| `countrycode`                | String  | ""       | Código telefónico internacional                                    |
| `alpha2`                     | String  | ""       | Código ISO del país                                                |
| `currency`                   | String  | ""       | Nombre de la moneda local.                                         |
| `currencycode`               | String  | ""       | Código internacional de la moneda.                                 |
| `currencysign`               | String  | ""       | Símbolo gráfico de la moneda                                       |
| `flag_url`                   | String  | ""       | URL de la imagen de la bandera nacional.                           |
| `countrytimezone`            | String  | ""       | Zona horaria principal.                                            |
| `country_all_timezone`       | Array   | []       | Lista de todas las zonas horarias que cubren el territorio.        |
| `payment_gateways`           | Array   | []       | Lista de pasarelas de pago habilitadas                             |
| `countryphonecode`           | String  | ""       | Código de área telefónico (                                        |
| `isBusiness`                 | Number  | 1        | Define si el país está habilitado para operaciones                 |
| `phone_number_min_length`    | Number  | 8        | Longitud mínima permitida para números telefónicos                 |
| `phone_number_length`        | Number  | 10       | Longitud estándar/máxima para números telefónicos                  |
| `is_referral`                | Boolean | true     | Habilita/Deshabilita el sistema de referidos                       |
| `referral_bonus_to_user`     | Number  | 0        | Bono que recibe el usuario invitado.                               |
| `bonus_to_userreferral`      | Number  | 0        | Bono que recibe el usuario que invita                              |
| `is_provider_referral`       | Boolean | true     | Habilita/Deshabilita el sistema de referidos para **Proveedores**. |
| `referral_bonus_to_provider` | Number  | 0        | Bono que recibe el proveedor invitado.                             |
| `bonus_to_providerreferral`  | Number  | 0        | Bono que recibe el proveedor que invita.                           |
| `default_selected`           | Boolean | false    | Determina si es el país seleccionado por defecto en el registro.   |
| `is_auto_transfer`           | Boolean | true     | Habilita la transferencia automática de fondos a conductores.      |
| `auto_transfer_day`          | Number  | 7        | Ciclo de días para transferencias automáticas                      |
| `coordinates`                | Object  | -        | Coordenadas geográficas del país.                                  |
| `daily_cron_date`            | Date    | -        | Fecha de la última ejecución de tareas programadas                 |
| `created_at` / `updated_at`  | Date    | Date.now | Marcas de tiempo de creación y actualización de registro           |
### Modelo - Country_Data.js

**Descripción:**
El modelo sustenta la información asociada a la lógica de negocio que sirve para poblar selectores, validar códigos de moneda y  proporcionar detalles sobre los desplazamientos de las zonas horarias.

| Campo                    | Tipo    | Default | Descripción                                                           |
| :----------------------- | :------ | :------ | :-------------------------------------------------------------------- |
| `alpha2`                 | String  | ""      | Código ISO 3166-1 de 2 letras (ej: "US", "VE", "ES").                 |
| `alpha3`                 | String  | ""      | Código ISO 3166-1 de 3 letras (ej: "USA", "VEN", "ESP").              |
| `code`                   | String  | ""      | Código de identificación del país.                                    |
| `currency_code`          | String  | ""      | Código internacional de la moneda                                     |
| `decimals`               | Number  | 2       | Cantidad de decimales permitidos para la moneda del país              |
| `name`                   | String  | ""      | Nombre del país.                                                      |
| `sign`                   | String  | ""      | Símbolo de la moneda                                                  |
| `timezones`              | Array   | -       | Zonas horaria                                                         |
| `timezones_detail`       | Object  | -       | Objeto con metadatos zona horaria.                                    |
| `key.rawOffsetInMinutes` | Number  | -       | Desplazamiento respecto al UTC expresado en minutos.                  |
| `key.abbreviation`       | String  | -       | Abreviatura de la zona horaria (ej: "VET", "EST").                    |
| `key.rawFormat`          | String  | -       | Formato legible del desplazamiento                                    |
| `active`                 | Boolean | -       | Indica si este registro está disponible para ser usado en el sistema. |
### Modelo - Dispatcher.js

**Descripción:**
El modelo con manejo de información para la lógica de  solicitudes de servicios, monitoreo de conductores y asignación de viajes 

| Campo                   | Tipo              | Default  | Descripción                      |
| :---------------------- | :---------------- | :------- | :------------------------------- |
| `unique_id`             | Number            | -        | ID                               |
| `first_name`            | String            | ""       | Nombre del operador              |
| `last_name`             | String            | ""       | Apellido del operador            |
| `email`                 | String            | ""       | Correo electrónico               |
| `password`              | String            | ""       | Contraseña                       |
| `token`                 | String            | ""       | Token de sesión                  |
| `country_phone_code`    | String            | ""       | Código telefónico                |
| `phone`                 | String            | ""       | Número de teléfono .             |
| `country` / `countryid` | String / ObjectId | "" / -   | Nombre e ID del país             |
| `city` / `cityid`       | String / ObjectId | "" / -   | Nombre e ID de la ciudad         |
| `created_at`            | Date              | Date.now | Fecha de creación de registro    |
| `updated_at`            | Date              | Date.now | Fecha de la última actualización |
### Modelo - Documents.js

**Descripción:**
Este modelo no contiene los archivos subidos por los usuarios, define la **plantilla o regla** del documento requerido (ej: "Licencia de Conducir", "Seguro Vehicular"). Configura si el documento requiere fecha de vencimiento, código único o fecha de emisión para ser validado

| Campo             | Tipo     | Default  | Descripción                                                                  |
| :---------------- | :------- | :------- | :--------------------------------------------------------------------------- |
| `unique_id`       | Number   | -        | id                                                                           |
| `countryid`       | ObjectId | -        | Referencia al país donde este documento es obligatorio.                      |
| `title`           | String   | ""       | Nombre del documento                                                         |
| `type`            | Number   | 8        | Categoría interna del documento                                              |
| `option`          | Number   | 0        | Obligatoriedad                                                               |
| `expired_date`    | Date     | -        | Fecha de vencimiento                                                         |
| `issue_date`      | Date     | Date.now | Fecha de emisión                                                             |
| `is_issue_date`   | Boolean  | false    | Si es true, el sistema exigirá al usuario ingresar la fecha de emisión.      |
| `is_degree`       | Boolean  | false    | Flag para indicar si el documento requiere un grado académico o profesional. |
| `degree`          | String   | ""       |                                                                              |
| `is_unique_code`  | Boolean  | false    | Si es true, el sistema exigirá un código alfanumérico                        |
| `is_expired_date` | Boolean  | false    | Si es true, el sistema exigirá y validará una fecha de vencimiento futura.   |
| `document_for`    | Number   | -        | **Destinatario**: 0 para Persona, 1 para el Vehículo.                        |
| `created_at`      | Date     | Date.now | Fecha de creación de registro.                                               |
| `updated_at`      | Date     | Date.now | Fecha de la última modificación                                              |
### Modelo - Email_Deatil.js

**Descripción:**
Este modelo almacena la estructura y el contenido de los correos electrónicos que envía la plataforma.

| Campo              | Tipo     | Default | Descripción                                                    |
| :----------------- | :------- | :------ | :------------------------------------------------------------- |
| `emailUniqueId`    | Number   | -       | Id                                                             |
| `emailUniqueTitle` | String   | ""      | Nombre técnico de la plantilla de correo.                      |
| `emailTitle`       | String   | ""      | El asunto (Subject) del correo que verá el destinatario final. |
| `emailContent`     | String   | ""      | Cuerpo del mensaje.                                            |
| `emailAdminInfo`   | String   | ""      | Notas o descripción .                                          |
| `countryName`      | String   | ""      | Nombre del país asociado a la plantilla                        |
| `countryId`        | ObjectId | -       | Referencia al modelo **Country**                               |

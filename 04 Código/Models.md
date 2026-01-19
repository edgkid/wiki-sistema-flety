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
### Modelo - Emergency_Contact_Detail.js

**Descripción:**
Este modelo para soportar información de contactos de emergencia.

| Campo                         | Tipo     | Default  | Descripción                                                                |
| :---------------------------- | :------- | :------- | :------------------------------------------------------------------------- |
| `user_id`                     | ObjectId | -        | Id                                                                         |
| `name`                        | String   | ""       | Nombre                                                                     |
| `phone`                       | String   | ""       | Número telefónico                                                          |
| `is_always_share_ride_detail` | Number   | 0        | Flag para el envió del enlace de seguimiento de cada viaje a los contactos |
| `created_at`                  | Date     | Date.now | Fecha de registro                                                          |
| `updated_at`                  | Date     | Date.now | Fecha de la última actualización                                           |
### Modelo - Ferry_Ticket.js

**Descripción:**
El modelo  registra la compra y validación de boletos de ferry necesarios para que un servicio complete una ruta. 

| Campo             | Tipo     | Descripción                                                |
| :---------------- | :------- | :--------------------------------------------------------- |
| `unique_id`       | Number   | ID                                                         |
| `user_id`         | ObjectId | Referencia al usuario                                      |
| `user_type`       | Number   | Define el rol del usuario                                  |
| `amount`          | Number   | Monto total cargado al sistema por el concepto del ticket. |
| `ticket_cost`     | Number   | Valor nominal o costo real del ticket                      |
| `corporate_id`    | ObjectId | Referencia a la empresa                                    |
| `service_type_id` | ObjectId | Vinculación con el tipo de servicio                        |
| `country_id`      | ObjectId | Referencia al país                                         |
| `type_id`         | ObjectId | Referencia a `city_type`                                   |
| `status`          | Number   | status                                                     |
| `file_url`        | String   |                                                            |
| `created_at`      | Date     | Fecha de creación                                          |
| `updated_at`      | Date     | Fecha de la última                                         |
### Modelo - Guest_Token.js

**Descripción:**
El modelo  permite la creación y validación de credenciales temporales. 

| Campo         | Tipo    | Default  | Descripción                                               |
| :------------ | :------ | :------- | :-------------------------------------------------------- |
| `unique_id`   | Number  | -        | Id                                                        |
| `token_name`  | String  | ""       | Etiqueta descriptiva del token                            |
| `token_value` | String  | ""       | El valor alfanumérico del token                           |
| `state`       | Boolean | true     | status                                                    |
| `start_date`  | Date    | Date.now | Fecha a partir de la cual el token comienza a ser válido. |
| `code_expiry` | Date    | Date.now | Fecha y hora exacta en la que el token expira             |
| `created_at`  | Date    | Date.now | Fecha de creación del registro                            |
| `updated_at`  | Date    | Date.now | Fecha de la última modificación.                          |
### Modelo - Inbox_Notification.js

**Descripción:**
Este modelo almacena mensajes persistentes que el usuario puede leer en cualquier momento desde su centro de mensajes. 

| Campo        | Tipo     | Descripción                            |
| :----------- | :------- | :------------------------------------- |
| `unique_id`  | Number   | ID                                     |
| `title`      | String   | Encabezado o asunto de la notificación |
| `message`    | String   | Contenido detallado del mensaje        |
| `type`       | Number   |                                        |
| `country_id` | ObjectId | Referencia al modelo **Country**       |
| `created_at` | Date     | Fecha de creación                      |
| `updated_at` | Date     | Fecha de la última actualización.      |
### Modelo - Information.js

**Descripción:**
El modelo almacena datos que suelen ser consultados de forma recurrente en secciones como por ejemplo "Ayuda"

| Campo         | Tipo   | Default  | Descripción                                |
| :------------ | :----- | :------- | :----------------------------------------- |
| `title`       | String | ""       | Título del artículo o sección informativa  |
| `file`        | String | ""       | URL o ruta del archivo multimedia asociado |
| `description` | String | ""       | Cuerpo del texto informativo               |
| `created_at`  | Date   | Date.now | Fecha de creación del registro             |
| `updated_at`  | Date   | Date.now | Fecha de la última actualización.          |
### Modelo - Partner_Vehicle_Document.js

**Descripción:**
Este modelo almacena el _resultado_ la Documentación requerida para los vehículos subidos a la plataforma en cada servicio.

| Campo                 | Tipo     | Default  | Descripción                                                                 |
| :-------------------- | :------- | :------- | :-------------------------------------------------------------------------- |
| `document_id`         | ObjectId | -        | Referencia al modelo **Document**                                           |
| `vehicle_id`          | ObjectId | -        | Referencia al vehículo                                                      |
| `partner_id`          | ObjectId | -        | Referencia al conductor                                                     |
| `name`                | String   | ""       | Nombre del documento                                                        |
| `option`              | Number   | 0        | Flag de mandotoriedad del documento                                         |
| `document_picture`    | String   | ""       | URL o ruta de la imagen o archivo subido                                    |
| `is_uploaded`         | Number   | 0        | Estado de la carga                                                          |
| `unique_code`         | String   | ""       | Número del documento físico.                                                |
| `expired_date`        | Date     | Date.now | Fecha de vencimiento del documento.                                         |
| `is_unique_code`      | Boolean  | false    | Flag que indica si este documento requiere un código único para ser válido. |
| `is_expired_date`     | Boolean  | false    | Flag que indica si este documento debe tener una fecha de expiración.       |
| `is_document_expired` | Boolean  | false    | Estado de vigencia                                                          |
| `created_at`          | Date     | Date.now | Fecha de creación                                                           |
| `updated_at`          | Date     | Date.now | Fecha de la última modificación                                             |
### Modelo - Partner_Weekly_Earning.js

**Descripción:**
Este modelo consolida todas las transacciones de los conductores 

| Campo                                 | Tipo     | Default | Descripción                                                   |
| :------------------------------------ | :------- | :------ | :------------------------------------------------------------ |
| `provider_id`                         | ObjectId | -       | Referencia al proveedor                                       |
| `statement_number`                    | String   | ""      | Número de factura                                             |
| `total_distance`                      | Number   | 0       | Sumatoria de la distancia recorrida en todos los viajes       |
| `total_time`                          | Number   | 0       | Sumatoria del tiempo total de viaje.                          |
| `total_waiting_time`                  | Number   | 0       | Sumatoria del tiempo de espera cobrado durante la semana.     |
| `total_service_fees`                  | Number   | 0       | Total de la tarifa                                            |
| `total_service_surge_fees`            | Number   | 0       | Total recaudado                                               |
| `total_service_tax_fees`              | Number   | 0       | Total de impuestos                                            |
| `service_total`                       | Number   | 0       | Subtotal de los servicios                                     |
| `promo_referral_amount`               | Number   | 0       | Monto ganado por promociones                                  |
| `total`                               | Number   | 0       | Ingreso bruto total                                           |
| `total_card_payment`                  | Number   | 0       | Total recaudado mediante pagos con tarjeta                    |
| `total_cash_payment`                  | Number   | 0       | Total recaudado mediante pagos en efectivo.                   |
| `total_wallet_payment`                | Number   | 0       | Total recaudado mediante saldos de billetera electrónica.     |
| `total_partner_service_fees`          | Number   | 0       | Comisión neta                                                 |
| `total_in_admin_currency`             | Number   | 0       |                                                               |
| `total_partner_have_cash`             | Number   | 0       |                                                               |
| `total_pay_to_partner`                | Number   | 0       |                                                               |
| `admin_paid`                          | Number   | 0       |                                                               |
| `remaining_amount_to_paid`            | Number   | 0       |                                                               |
| `date_tag`                            | String   | ""      |                                                               |
| `start_date_server_timezone`          | Date     | -       |                                                               |
| `end_date_server_timezone`            | Date     | -       |                                                               |
| `partner_provider_weekly_earning_ids` | Array    | []      | Lista de IDs de los registros individuales de cada conductor  |
### Modelo - Partner.js

**Descripción:**
El modelo que define el perfil del socio comercial. A diferencia de un conductor individual, el Socio tiene la capacidad de registrar múltiples vehículos y conductores bajo su tutela

| Campo                          | Tipo     | Default  | Descripción                                             |
| :----------------------------- | :------- | :------- | :------------------------------------------------------ |
| `unique_id`                    | Number   | -        | ID .                                                    |
| `first_name`                   | String   | ""       | Nombre                                                  |
| `last_name`                    | String   | ""       | Apellido                                                |
| `partner_company_name`         | String   | ""       | Razón social                                            |
| `rif`                          | String   | ""       | Registro de Información Fiscal                          |
| `email`                        | String   | ""       | Correo electrónico                                      |
| `password`                     | String   | ""       | Contraseña                                              |
| `country_phone_code`           | String   | ""       | Código telefónico internacional del país.               |
| `phone`                        | String   | ""       | Número de teléfono de contacto.                         |
| `country_id`                   | ObjectId | -        | Referencia al país de operación.                        |
| `city_id`                      | ObjectId | -        | Referencia a la ciudad base del socio.                  |
| `address`                      | String   | ""       | Dirección física                                        |
| `wallet`                       | Number   | 0        | Saldo acumulado en la billetera                         |
| `wallet_currency_code`         | String   | ""       | Código de la moneda de la billetera                     |
| `is_approved`                  | Number   | 0        | Estado de activación                                    |
| `is_vehicle_document_uploaded` | Boolean  | false    | Indica si los documentos de la flota han sido cargados. |
| `vehicle_detail`               | Array    | []       | Lista o detalles de los vehículos                       |
| `picture`                      | String   | ""       |                                                         |
| `rif_url`                      | String   | ""       | URL del documento RIF                                   |
| `document_2`                   | String   | ""       | URL del documento legal (PDF).                          |
| `government_id_proof`          | String   | ""       | URL de la identificación                                |
| `stripe_doc` / `account_id`    | String   | ""       | IDs de referencia para integraciones .                  |
| `bank_id` / `account_number`   | String   | ""       | Identificación del banco y número de                    |
| `bank_code`                    | String   | ""       |                                                         |
| `token`                        | String   | ""       | Token de sesión                                         |
| `refferal_code`                | String   | ""       | Código de referido                                      |
| `webpush_config`               | Object   | {}       |                                                         |
| `mass_notifications`           | Array    | []       |                                                         |
| `last_transferred_date`        | Date     | Date.now | Fecha de la última liquidación                          |
| `created_at`                   | Date     | Date.now | Fecha de registro                                       |
| `updated_at`                   | Date     | Date.now | Fecha de la última actualización                        |
### Modelo - Payment_Transaction.js

**Descripción:**
Este modelo funge como motor de control para los pagos , almacena las llaves de la pasarela para esa transacción y mantiene el movimiento de dinero

| Campo                      | Tipo    | Default  | Descripción                                                   |
| :------------------------- | :------ | :------- | :------------------------------------------------------------ |
| `stripe_public_key`        | String  | ""       | Llave pública de Stripe                                       |
| `stripe_secret_key`        | String  | ""       | Llave secreta de Stripe .                                     |
| `amount`                   | Number  | 0        | Monto total de la transacción.                                |
| `currency_code`            | String  | ""       | Código de moneda                                              |
| `is_schedule_payment`      | Boolean | true     |                                                               |
| `is_payment_paid`          | Boolean | false    | Estatus del cobro                                             |
| `no_of_failed_transaction` | Number  | 0        | Contador de cuántas veces ha fallado el intento de cobro.     |
| `max_no_of_transaction`    | Number  | 0        | Límite máximo de reintentos permitidos                        |
| `transaction_detail`       | Array   | []       |                                                               |
| `card_detail`              | Array   | []       | Información  de la tarjeta utilizada para el pago.            |
| `last_payment_date`        | Date    | -        | Fecha y hora en la que se realizó el último intento de cobro. |
| `is_stop_system`           | Boolean | false    |                                                               |
| `type_detail`              | Array   | []       | Información  sobre el origen del pago                         |
| `created_at`               | Date    | Date.now | Fecha de creación                                             |
| `updated_at`               | Date    | Date.now | Fecha de la última actualización                              |
### Modelo - Promo_Code.js

**Descripción:**
El modelo permite manejar la información de los códigos promocionales,  lógica para limitar el número de usos totales, usos por usuario único, fechas de vigencia y restricciones por ciudad o tipo de servicio.

| Campo                   | Tipo            | Default  | Descripción                                                      |
| :---------------------- | :-------------- | :------- | :--------------------------------------------------------------- |
| `promocode`             | String          | ""       | El código de promoción                                           |
| `code_value`            | Number          | 0        | El valor del descuento a aplicar.                                |
| `code_type`             | Number          | 0        | Tipo de descuento                                                |
| `code_uses`             | Number          | 0        | Cantidad máxima de veces que el código puede ser usado           |
| `user_used_promo`       | Number          | 0        | Contador total de cuántas veces se ha canjeado el código         |
| `code_uses_per_user`    | Number          | 0        | Límite de veces que un mismo usuario puede utilizar este código. |
| `state`                 | Number          | 0        | Estado del código                                                |
| `completed_trips_type`  | Number          | 0        | Condición basada en viajes                                       |
| `completed_trips_value` | Number          | 0        | Umbral de viajes completados para activar la promoción.          |
| `countryid`             | ObjectId        | -        | Referencia de pais                                               |
| `cityid`                | Array[ObjectId] | []       | Lista de ciudades                                                |
| `serviceid`             | Array[ObjectId] | []       | Tipos de servicios.                                              |
| `start_date`            | Date            | Date.now | Fecha a partir de la cual el código empieza a ser válido.        |
| `code_expiry`           | Date            | Date.now | Fecha y hora de vencimiento                                      |
| `created_at`            | Date            | Date.now | Fecha de creación                                                |
| `updated_at`            | Date            | Date.now | Fecha de la última modificación                                  |
### Modelo - Provider_Daily_Analytic.js

**Descripción:**
Este modelo almacena la actividad transaccional y de tiempo de un conductor en un periodo de tiempo, el modelo permite generar reportes.

| Campo                  | Tipo     | Default  | Descripción                                                        |
| :--------------------- | :------- | :------- | :----------------------------------------------------------------- |
| `unique_id`            | Number   | -        | Id                                                                 |
| `provider_id`          | ObjectId | -        | Referencia al conductor                                            |
| `date_tag`             | String   | ""       | Etiqueta de fecha formateada                                       |
| `date_server_timezone` | Date     | Date.now | Fecha del servidor en la que se registran los datos                |
| `received`             | Number   | 0        | Total de solicitudes de viaje                                      |
| `accepted`             | Number   | 0        | Cantidad de viajes que el conductor aceptó.                        |
| `rejected`             | Number   | 0        | Cantidad de viajes que el conductor rechazó explícitamente.        |
| `not_answered`         | Number   | 0        | Cantidad de solicitudes que expiraron sin respuesta del conductor. |
| `cancelled`            | Number   | 0        | Viajes aceptados pero cancelados por el conductor.                 |
| `completed`            | Number   | 0        | Cantidad de viajes finalizados exitosamente.                       |
| `acception_ratio`      | Number   | 0        | Tasa de aceptación (Aceptados / Recibidos).                        |
| `rejection_ratio`      | Number   | 0        | Tasa de rechazo (Rechazados / Recibidos).                          |
| `cancellation_ratio`   | Number   | 0        | Tasa de cancelación (Cancelados / Aceptados).                      |
| `completed_ratio`      | Number   | 0        | Tasa de finalización de viajes                                     |
| `total_online_time`    | Number   | 0        | Tiempo total acumulado                                             |
| `online_times`         | Array    | []       |                                                                    |
| `created_at`           | Date     | Date.now | Fecha de creación                                                  |
| `updated_at`           | Date     | Date.now | Fecha de la última actualización                                   |
### Modelo - Provider_Daily_Earning.js

**Descripción:**
Este modelo almacena financieras de un conductor . 

| Campo                         | Tipo     | Default  | Descripción                                           |
| :---------------------------- | :------- | :------- | :---------------------------------------------------- |
| `provider_id`                 | ObjectId | -        | Referencia al conductor                               |
| `provider_type`               | Number   | -        | Identificador del tipo                                |
| `provider_type_id`            | ObjectId | -        | Referencia a la categoría                             |
| `statement_number`            | String   | ""       |                                                       |
| `total_distance`              | Number   | 0        | Distancia total recorrida en el viaje                 |
| `total_time`                  | Number   | 0        | Tiempo total transcurrido en el viaje                 |
| `total_waiting_time`          | Number   | 0        | Tiempo total que el conductor cobró                   |
| `total_service_fees`          | Number   | 0        | Suma de las tarifas base de los servicios realizados. |
| `total_service_surge_fees`    | Number   | 0        | Ganancias extra por tarifa dinámica                   |
| `total_service_tax_fees`      | Number   | 0        | Total de impuestos aplicados                          |
| `service_total`               | Number   | 0        | Monto bruto generado por los servicios.               |
| `promo_referral_amount`       | Number   | 0        | Incentivos ganados por uso de códigos promocionales   |
| `total`                       | Number   | 0        | Ingreso total del día                                 |
| `total_card_payment`          | Number   | 0        | Monto total recibido a través de tarjetas.            |
| `total_cash_payment`          | Number   | 0        | Monto total recibido en efectivo.                     |
| `total_wallet_payment`        | Number   | 0        | Monto total recibido desde la billetera               |
| `total_provider_service_fees` | Number   | 0        | Ganancia final para el conductor.                     |
| `total_in_admin_currency`     | Number   | 0        | Total diario en la moneda del                         |
| `total_provider_have_cash`    | Number   | 0        | Dinero físico que el conductor devengo                |
| `total_pay_to_provider`       | Number   | 0        | Saldo neto a transferir al conductor                  |
| `date_tag`                    | String   | ""       | Etiqueta de fecha                                     |
| `date_server_timezone`        | Date     | Date.now | Marca de tiempo                                       |
| `provider_trip_earning_ids`   | Array    | []       | Lista de IDs de los viajes individuales               |
### Modelo - Provider_Document.js

**Descripción:**
Este modelo almacena los documentos de cada conductor.

| Campo               | Tipo     | Descripción                                                      |
| ------------------- | -------- | ---------------------------------------------------------------- |
| document_id         | ObjectId | Referencia al modelo Document                                    |
| name                | String   | Nombre descriptivo del documento                                 |
| provider_id         | ObjectId | Referencia al conductor .                                        |
| option              | Number   | Define la obligatoriedad                                         |
| document_picture    | String   | URL de archivo PDF almacenado en el servidor.                    |
| is_uploaded         | Number   | Estado de la carga                                               |
| unique_code         | String   | El número del documento                                          |
| is_unique_code      | Boolean  | Flag qsi se requiere un código único.                            |
| expired_date        | Date     | Fecha de vencimiento del documento                               |
| issue_date          | Date     | Fecha en la que fue emitido el documento.                        |
| is_issue_date       | Boolean  | Define la obligatoriedad                                         |
| is_degree           | Boolean  | Indica si el documento valida un grado especial.                 |
| degree              | String   | El grado asociado al documento.                                  |
| is_expired_date     | Boolean  | Flag que indica si se requiere capturar la fecha de vencimiento. |
| is_document_expired | Boolean  | Estado dinámico que marca si el documento ya venció.             |
| created_at          | Date     | Fecha de creación                                                |
| updated_at          | Date     | Fecha de la última actualización                                 |
### Modelo - Provider_Weekly_Earning.js

**Descripción:**
Este modelo actúa como el resumen consolidado de la semana de un conductor, aquí se permite calcular el balance  entre la ganancia del conductor y recaudado en efectivo.

| Campo                         | Tipo     | Default | Descripción                                                        |
| :---------------------------- | :------- | :------ | :----------------------------------------------------------------- |
| `provider_id`                 | ObjectId | -       | Referencia al conductor                                            |
| `provider_type`               | Number   | -       | Tipo de proveedor.                                                 |
| `provider_type_id`            | ObjectId | -       | Referencia a la categoría de servicio del proveedor.               |
| `statement_number`            | String   | ""      | Identificador único de la factura o estado de cuenta semanal.      |
| `total_distance`              | Number   | 0       | Distancia total acumulada                                          |
| `total_time`                  | Number   | 0       | Tiempo total acumulado en servicios activos.                       |
| `total_waiting_time`          | Number   | 0       | Tiempo total de espera facturado en la semana.                     |
| `total_service_fees`          | Number   | 0       | Suma de tarifas base semanales.                                    |
| `total_service_surge_fees`    | Number   | 0       | Total generado por alta demanda                                    |
| `total_service_tax_fees`      | Number   | 0       | Total de impuestos recaudados                                      |
| `service_total`               | Number   | 0       | Subtotal bruto                                                     |
| `promo_referral_amount`       | Number   | 0       |                                                                    |
| `total`                       | Number   | 0       | Ingreso bruto total semanal                                        |
| `total_card_payment`          | Number   | 0       | Pagos recibidos vía tarjeta                                        |
| `total_cash_payment`          | Number   | 0       | Pagos recibidos en efectivo                                        |
| `total_wallet_payment`        | Number   | 0       | Pagos realizados mediante billetera virtual.                       |
| `total_provider_service_fees` | Number   | 0       | Ganancia neta final                                                |
| `total_in_admin_currency`     | Number   | 0       |                                                                    |
| `total_provider_have_cash`    | Number   | 0       | Monto total de efectivo                                            |
| `total_pay_to_provider`       | Number   | 0       | **Monto Neto a Pagar**                                             |
| `admin_paid`                  | Number   | 0       | Cantidad que el administrador ya ha transferido al conductor.      |
| `remaining_amount_to_paid`    | Number   | 0       | Saldo restante por pagar para cerrar la semana.                    |
| `date_tag`                    | String   | ""      |                                                                    |
| `start_date_tag`              | String   | ""      | Fecha de inicio del ciclo semanal                                  |
| `end_date_tag`                | String   | ""      | Fecha de fin del ciclo semanal                                     |
| `start_date_server_timezone`  | Date     | -       |                                                                    |
| `end_date_server_timezone`    | Date     | -       |                                                                    |
| `provider_daily_earning_ids`  | Array    | []      | Referencia a los 7 registros de ProviderDailyEarning de la semana. |
### Modelo - Provider.js

**Descripción:**
El modelo para manejar los datos de perfil del conductor.

| Campo                          | Tipo            | Default  | Descripción                                                       |
| :----------------------------- | :-------------- | :------- | :---------------------------------------------------------------- |
| `provider_type`                | Number          | -        | Tipo proveedor                                                    |
| `provider_type_id`             | ObjectId        | -        | ID de referencia  tipo  proveedor.                                |
| `unique_id`                    | Number          | -        | ID                                                                |
| `first_name`                   | String          | ""       | Nombre.                                                           |
| `last_name`                    | String          | ""       | Apellido                                                          |
| `email`                        | String          | ""       | Correo electrónico                                                |
| `gender`                       | String          | ""       | Género                                                            |
| `languages`                    | Array[ObjectId] | []       | Idiomas                                                           |
| `wallet`                       | Number          | 0        | Saldo actual                                                      |
| `wallet_currency_code`         | String          | ""       | Código de moneda                                                  |
| `phone`                        | String          | ""       | Número de teléfono                                                |
| `country_phone_code`           | String          | ""       | Prefijo telefónico internacional.                                 |
| `password`                     | String          | ""       | Contraseña                                                        |
| `picture`                      | String          | ""       | URL de la foto de perfil del conductor.                           |
| `token`                        | String          | ""       | Token de sesión                                                   |
| `is_available`                 | Number          | 0        | Estado de disponibilidad                                          |
| `is_active`                    | Number          | 0        | Estado de conexión                                                |
| `is_approved`                  | Number          | 0        |                                                                   |
| `is_documents_expired`         | Boolean         | false    | vigencia de documento                                             |
| `is_vehicle_document_uploaded` | Boolean         | false    | Indica si los documentos del vehículo asociado han sido cargados. |
| `service_type`                 | ObjectId        | -        |                                                                   |
| `car_model`                    | String          | ""       | Modelo del vehículo.                                              |
| `car_number`                   | String          | ""       | Placa o matrícula del vehículo.                                   |
| `device_token`                 | String          | ""       |                                                                   |
| `device_type`                  | String          | ""       | Sistema operativo del dispositivo                                 |
| `providerLocation`             | [Number]        | -        | Coordenadas geoespaciales actuales                                |
| `address_location`             | [Number]        | -        | Coordenadas                                                       |
| `rate`                         | Number          | 0        |                                                                   |
| `rate_count`                   | Number          | 0        | Cantidad total de calificaciones recibidas.                       |
| `referral_code`                | String          | ""       | Código único para invitar a otros conductores o usuarios.         |
| `total_request`                | Number          | 0        | Total de solicitudes recibidas                                    |
| `accepted_request`             | Number          | 0        | Cantidad total de viajes aceptados.                               |
| `completed_request`            | Number          | 0        | Cantidad total de viajes finalizados con éxito.                   |
| `cancelled_request`            | Number          | 0        | Cantidad total de viajes cancelados.                              |
| `account_id` / `bank_id`       | String          | ""       | Información para la dispersión de pagos (Stripe/Banco).           |
| `zone_queue_id`                | ObjectId        | -        | ID de la zona .                                                   |
| `created_at`                   | Date            | Date.now | Fecha de registro                                                 |
| `updated_at`                   | Date            | Date.now | Fecha de la última actualización                                  |
### Modelo - Red_Zone_Area.js

**Descripción:**
El modelo permite manejar información de áreas de riesgo

| Campo            | Tipo     | Default  | Descripción                                          |
| :--------------- | :------- | :------- | :--------------------------------------------------- |
| `cityid`         | ObjectId | -        | Referencia de City                                   |
| `title`          | String   | ""       | Nombre identificador de la zona.                     |
| `styleUrl`       | String   | ""       |                                                      |
| `styleHash`      | String   | ""       |                                                      |
| `description`    | String   | ""       | Detalle o motivo de la restricción de la zona.       |
| `stroke`         | String   | ""       | Color del borde del polígono en formato hexadecimal. |
| `stroke_opacity` | Number   | 0        | Nivel de transparencia del borde (0 a 1).            |
| `stroke_width`   | Number   | 0        | Grosor del borde del polígono en el mapa.            |
| `fill`           | String   | ""       | Color de relleno del área en formato hexadecimal.    |
| `fill_opacity`   | Number   | 0        | Nivel de transparencia del relleno (0 a 1).          |
| `kmlzone`        | Array    | []       | Arreglo de coordenadas                               |
| `created_at`     | Date     | Date.now | Fecha de creación del registro.                      |
| `updated_at`     | Date     | Date.now | Fecha de la última modificación                      |
### Modelo - Request_User_Corporate.js

**Descripción:**
Este modelo almacena los datos básicos, credenciales y documentos legales cargados durante el proceso de registro inicial. Una vez que el administrador valida la información, el estado cambia de `pending` a aprobado (permitiendo la migración o activación del perfil corporativo oficial).

| Campo         | Tipo   | Default   | Descripción                                   |
| :------------ | :----- | :-------- | :-------------------------------------------- |
| `unique_id`   | Number | -         | Id                                            |
| `country`     | String | -         | País de operaciones                           |
| `city`        | String | -         | Ciudad principal de operaciones de la empresa |
| `name`        | String | -         | razón social de la corporación                |
| `email`       | String | -         | Correo electrónico                            |
| `address`     | String | -         | Dirección física                              |
| `phone`       | String | -         | Número de teléfono                            |
| `countryCode` | String | -         | Código telefónico                             |
| `password`    | String | -         | Contraseña e                                  |
| `logo`        | Buffer | -         |                                               |
| `document`    | Buffer | -         |                                               |
| `status`      | String | 'pending' | Estatus de la solicitud.                      |
| `created_at`  | Date   | Date.now  | Fecha de creación                             |
| `updated_at`  | Date   | Date.now  | Fecha de la última modificación               |
### Modelo - Reviews.js

**Descripción:**
El modelo  consolida las calificaciones y comentarios generados al finalizar un servicio. 

| Campo                       | Tipo     | Default  | Descripción                                                              |
| :-------------------------- | :------- | :------- | :----------------------------------------------------------------------- |
| `userRating`                | Number   | 0        | Calificación numérica                                                    |
| `userReview`                | String   | ""       | Comentario o reseña                                                      |
| `userName`                  | String   | ""       | Nombre del usuario que realiza la reseña                                 |
| `providerRating`            | Number   | 0        | Calificación numérica otorgada por el proveedor al usuario.              |
| `providerReview`            | String   | ""       | Comentario escrito por el proveedor sobre el comportamiento del usuario. |
| `providerRatingDestination` | Number   | 0        | Calificación del proveedor específicamente sobre la zona                 |
| `providerReviewDestination` | String   | ""       | Comentarios del proveedor sobre dificultades o detalles del destino.     |
| `trip_id`                   | ObjectId | -        | Referencia al ID único del viaje (Trip)                                  |
| `trip_unique_id`            | Number   | -        | ID numérico incremental                                                  |
| `user_id`                   | ObjectId | -        | Referencia al usuario  involucrado en la reseña.                         |
| `provider_id`               | ObjectId | -        | Referencia al proveedor involucrado en la reseña.                        |
| `created_at`                | Date     | Date.now | Fecha de creación del registro                                           |
| `updated_at`                | Date     | Date.now | Fecha de la última actualización                                         |
### Modelo - Service_Specifications.js

**Descripción:**
Este modelo gestiona el catálogo de especificaciones técnicas que pueden ofrecer los proveedores. Estas especificaciones funcionan como filtros para que el usuario personalice su solicitud y el sistema pueda emparejarlo con un conductor cuyo vehículo cumpla con dichos requisitos. 

| Campo                | Tipo   | Default  | Descripción                                                |
| :------------------- | :----- | :------- | :--------------------------------------------------------- |
| `unique_id`          | Number | -        | Identificador numérico                                     |
| `specification_name` | String | ""       | Nombre de la característica                                |
| `specification_note` | String | ""       | descripción detallada de lo que implica la especificación. |
| `state`              | Number | 0        | Estado de la especificación.                               |
| `created_at`         | Date   | Date.now | Fecha de creación                                          |
| `updated_at`         | Date   | Date.now | Fecha de la última modificación                            |
### Modelo - Sms_Detail.js

**Descripción:**
El modelo  actúa como un repositorio de mensajes predefinidos.

| Campo            | Tipo   | Default | Descripción                      |
| :--------------- | :----- | :------ | :------------------------------- |
| `smsUniqueId`    | Number | -       | Identificador numérico           |
| `smsUniqueTitle` | String | ""      | Título descriptivo               |
| `smsContent`     | String | ""      | El cuerpo del mensaje de texto.  |
### Modelo - State_By_Country.js

**Descripción:**
El modelo maneja el esquema de divisiones administrativas de primer nivel (Estados, Provincias o Departamentos) dentro de un país determinado. Es esencial para los procesos de registro de usuarios y conductores, permitiendo  manera jerárquica, como por ejemplo; País > Estado > Ciudad.

| Campo          | Tipo     | Default | Descripción                                |
| :------------- | :------- | :------ | :----------------------------------------- |
| `unique_id`    | Number   | -       | Identificador numérico                     |
| `type`         | String   | ""      |                                            |
| `country_name` | String   | ""      | Nombre del país al que pertenece el estado |
| `country_id`   | ObjectId | -       | Referencia al modelo **Country**           |
| `state_name`   | String   | ""      | Nombre                                     |
| `state_number` | Number   | -       | Código numérico o ID                       |
| `features`     | Array    | []      |                                            |
### Modelo - Transfer_History.js

**Descripción:**
El esquema registra el historial de transferencias  realizadas por la administración. Se utiliza principalmente para realizar el seguimiento de los pagos de ganancias acumuladas a conductores (`Providers`) y socios de flota (`Partners`). 

| Campo             | Tipo     | Default  | Descripción                                |
| :---------------- | :------- | :------- | :----------------------------------------- |
| `unique_id`       | Number   | -        | Identificador numérico                     |
| `user_type`       | Number   | -        | tipo de usuairo receptor                   |
| `user_id`         | ObjectId | -        | ID de referencia de usuario                |
| `country_id`      | ObjectId | -        | Referencia al país                         |
| `amount`          | Number   | 0        | Monto total transferido                    |
| `currency_code`   | String   | ""       | Código ISO de la moneda                    |
| `transfer_status` | Number   | 0        | Estatus de transacción                     |
| `transfered_by`   | Number   | 0        |                                            |
| `error`           | Object   | -        | Objeto que captura el log en caso de error |
| `transfer_id`     | String   | ""       | ID de referencia                           |
| `created_at`      | Date     | Date.now | Fecha de creación                          |
| `updated_at`      | Date     | Date.now | Fecha de la última actualización           |
### Modelo - Trip.js

**Descripción:**
El modelo permite gestionar el ciclo de vida completo de un servicio, desde la solicitud inicial y la asignación del proveedor, hasta el seguimiento en tiempo real, el desglose detallado de la facturación y manejo de tarifas.

Este modelo declara dos esquemas.
Esquema #1 declarado

| Campo                 | Tipo     | Default  | Descripción                                     |
| :-------------------- | :------- | :------- | :---------------------------------------------- |
| `unique_id`           | Number   | -        | ID numérico                                     |
| `invoice_number`      | String   | ""       | Número de factura único del viaje.              |
| `user_id`             | ObjectId | -        | Referencia al usuario que solicita el servicio. |
| `provider_id`         | ObjectId | -        | Referencia al conductor                         |
| `service_type_name`   | String   | ""       | Nombre de la categoría de servicio              |
| `split_payment_users` | Array    | `[]`     | Lista de participantes para pago compartido     |
| `source_address`      | String   | ""       | Dirección pickup                                |
| `destination_address` | String   | ""       | Dirección de destino                            |
| `sourceLocation`      | [Number] | -        | Coordenadas  de origen.                         |
| `destinationLocation` | [Number] | -        | Coordenadas de destino.                         |
| `payment_mode`        | Number   | -        | Método de pago                                  |
| `total`               | Number   | 0        | Monto total                                     |
| `promo_payment`       | Number   | 0        | Descuento aplicado por promociones.             |
| `tax_fee`             | Number   | 0        | Impuestos aplicados al viaje.                   |
| `total_distance`      | Number   | 0        | Distancia total recorrida.                      |
| `total_time`          | Number   | 0        | Tiempo total del viaje en minutos.              |
| `is_schedule_trip`    | Boolean  | false    | Indica si el viaje fue programado.              |
| `is_trip_completed`   | Number   | 0        | Flag de viaje finalizado con éxito.             |
| `is_trip_cancelled`   | Number   | 0        | Flag de viaje cancelado.                        |
| `created_at`          | Date     | Date.now | Fecha de creación del registro.                 |
Esquema #2 declarado

| Campo               | Tipo     | Default | Descripción                                  |
| :------------------ | :------- | :------ | :------------------------------------------- |
| `user_id`           | ObjectId | -       | Referencia al usuario                        |
| `first_name`        | String   | ""      | Nombre del usuario.                          |
| `last_name`         | String   | ""      | Apellido del usuario.                        |
| `email`             | String   | ""      | Correo electrónico                           |
| `phone`             | String   | ""      | Número de teléfono.                          |
| `payment_intent_id` | String   | ""      | ID de registro de pago en Stripe             |
| `status`            | Number   | 0       | Estado invitación                            |
| `payment_status`    | Number   | 0       | Estado pago                                  |
| `total`             | Number   | 0       | Cuota total a pagar                          |
| `remaining_payment` | Number   | 0       | Monto restante por liquidar.                 |
| `card_payment`      | Number   | 0       | Monto pagado con tarjeta por este usuario.   |
| `wallet_payment`    | Number   | 0       | Monto pagado con billetera por este usuario. |

### Modelo - Trip_History.js

**Descripción:**
 Cuando un viaje en la colección activa `Trip` termina su ciclo de vida (completado o cancelado), se registra aquí, permitir auditorías, reportes.
 
Este modelo declara dos esquemas.
Esquema #1 declarado

| Campo                   | Tipo   | Descripción                                      |
| :---------------------- | :----- | :----------------------------------------------- |
| `unique_id`             | Number | Identificador numérico                           |
| `invoice_number`        | String | Número de factura del viaje                      |
| `service_type_name`     | String | Nombre de la categoría de servicio.              |
| `user_first_name`       | String | Nombre del cliente que solicitó el viaje.        |
| `provider_first_name`   | String | Nombre del conductor que realizó el viaje.       |
| `source_address`        | String | Dirección de origen                              |
| `destination_address`   | String | Dirección de destino                             |
| `total`                 | Number | Monto total final facturado al cierre del viaje. |
| `payment_mode`          | Number | Método de pago utilizado                         |
| `payment_status`        | Number | Estado final del pago                            |
| `is_trip_completed`     | Number | Flag de finalización                             |
| `is_trip_cancelled`     | Number | Flag de cancelación                              |
| `total_distance`        | Number | Distancia total recorrida en el viaje.           |
| `total_time`            | Number | Tiempo total transcurrido                        |
| `promo_payment`         | Number | Descuento total aplicado por promociones.        |
| `wallet_payment`        | Number | Monto pagadol.                                   |
| `card_payment`          | Number | Monto procesado                                  |
| `cash_payment`          | Number | Monto pagado                                     |
| `provider_service_fees` | Number | Ganancia neta para el proveedor.                 |
| `pay_to_provider`       | Number | Monto a transferir al conductor.                 |
| `created_at`            | Date   | Fecha de creación del registro                   |
Esquema #2 declarado

| Campo               | Tipo     | Descripción                 |
| :------------------ | :------- | :-------------------------- |
| `user_id`           | ObjectId | Referencia de usuario       |
| `first_name`        | String   | Nombre del usuario          |
| `email`             | String   | Correo electrónico          |
| `phone`             | String   | Número de teléfono          |
| `payment_intent_id` | String   | ID de transacción en Stripe |
| `status`            | Number   | Estado invitación           |
| `payment_status`    | Number   | Estado pago                 |
| `total`             | Number   |                             |
| `remaining_payment` | Number   | Monto pendiente por cobrar. |
| `cash_payment`      | Number   | Monto pagado en efectivo.   |
| `card_payment`      | Number   | Monto pagado con tarjeta.   |
| `wallet_payment`    | Number   | Monto pagado con billetera. |
### Modelo - Trip_Location.js

**Descripción:**
 El modelo  almacena los datos de coordenadas punto a punto de un viaje. 

| Campo                                       | Tipo     | Default  | Descripción                                                      |
| :------------------------------------------ | :------- | :------- | :--------------------------------------------------------------- |
| `tripID`                                    | ObjectId | -        | Referencia al ID único del viaje                                 |
| `trip_unique_id`                            | Number   | -        | ID numérico incremental ia.                                      |
| `providerStartTime`                         | Date     | Date.now | Hora en la que el conductor inició el trayecto hacia el usuario. |
| `providerStartLocation`                     | [Number] | -        | Ubicación GPS inicial                                            |
| `startTripTime`                             | Date     | Date.now | Hora exacta en la que se inicio el servici                       |
| `startTripLocation`                         | [Number] | -        | Ubicación GPS del punto del recorrido                            |
| `endTripTime`                               | Date     | Date.now | Hora en la que se marcó el fin del viaje.                        |
| `endTripLocation`                           | [Number] | -        | Ubicación GPS del punto de llegada real                          |
| `providerStartToStartTripLocations`         | Array    | []       | Historial de coordenadas del servicio realizado                  |
| `startTripToEndTripLocations`               | Array    | []       |                                                                  |
| `actual_startTripToEndTripLocations`        | Array    | []       |                                                                  |
| `googlePathStartLocationToPickUpLocation`   | String   | ""       |                                                                  |
| `googlePickUpLocationToDestinationLocation` | String   | ""       |                                                                  |
| `google_total_distance`                     | Number   | 0        | Distancia total calculada                                        |
| `speed`                                     | Number   | 0        | Velocidad promedio                                               |
| `created_at`                                | Date     | Date.now | Fecha de creación                                                |
| `updated_at`                                | Date     | Date.now | Fecha de la última actualización                                 |
### Modelo - Trip_Servcie.js

**Descripción:**
 Este modelo permite definir tarifas base para servicios 

| Campo                             | Tipo     | Descripción                                           |
| :-------------------------------- | :------- | :---------------------------------------------------- |
| `trip_id`                         | ObjectId | Referencia del viaje                                  |
| `service_type_id`                 | ObjectId | Referencia al tipo de servicio                        |
| `city_id`                         | ObjectId | Referencia de ciudad                                  |
| `service_type_name`               | String   | Nombre del tipo de servicio.                          |
| `typename`                        | String   |                                                       |
| `min_fare`                        | Number   | Tarifa mínima                                         |
| `base_price`                      | Number   | Precio inicial                                        |
| `price_per_unit_distance`         | Number   | Costo por unidad de distancia                         |
| `price_for_total_time`            | Number   | Costo por minuto transcurrido de trayecto.            |
| `price_for_waiting_time`          | Number   | Costo por minuto de espera una vez iniciado el cobro. |
| `waiting_time_start_after_minute` | Number   | Minutos de gracia antes de cobrar tiempo de espera.   |
| `surge_multiplier`                | Number   | Multiplicador por alta demanda (                      |
| `is_surge_hours`                  | Number   | Flag para activar o desactivar horas pico.            |
| `user_tax`                        | Number   | Porcentaje de impuesto aplicado                       |
| `provider_tax`                    | Number   | Porcentaje de impuesto retenido                       |
| `provider_profit`                 | Number   | Ganancia configurada para el conductor.               |
| `cancellation_fee`                | Number   | Penalidad por cancelación tardía.                     |
| `is_car_rental_business`          | Number   |                                                       |
| `cost_per_helper`                 | Number   |                                                       |
| `cost_travel_insurance`           | Number   |                                                       |
| `ferry_ticket_price`              | Number   |                                                       |
| `model_type`                      | Number   |                                                       |
| `user_type`                       | Number   | Creador de la tarifa                                  |

| Campo (Tramo)    | Rango de Distancia | Descripción                                               |
| :--------------- | :----------------- | :-------------------------------------------------------- |
| `price_per_km_a` | 0 - 15 KM          | Tarifa para trayectos urbanos cortos.                     |
| `price_per_km_b` | 16 - 30 KM         | Tarifa para trayectos suburbanos.                         |
| `price_per_km_c` | 31 - 50 KM         | Tarifa para trayectos metropolitanos.                     |
| `price_per_km_d` | 51 - 80 KM         | Tarifa para viajes regionales cortos.                     |
| `price_per_km_e` | 81 - 110 KM        | Tarifa para viajes regionales medios.                     |
| `price_per_km_f` | 111 - 150 KM       | Tarifa para viajes interciudades.                         |
| `price_per_km_g` | 151 - 200 KM       | Tarifa para transporte troncal.                           |
| `price_per_km_h` | 201 - 300 KM       | Tarifa para viajes intermunicipales.                      |
| `price_per_km_p` | 301 - 450 KM       | Tarifa para viajes intermunicipales largos.               |
| `price_per_km_q` | 451 - 600 KM       | Tarifa para logística de media distancia.                 |
| `price_per_km_r` | 601 - 800 KM       | Tarifa para logística nacional.                           |
| `price_per_km_s` | 801 - 1000 KM      | Tarifa para transporte de carga pesada nacional.          |
| `price_per_km_t` | 1001 - 1150 KM     | Tarifa para trayectos de gran recorrido.                  |
| `price_per_km_u` | 1151 - 1300 KM     | Tarifa para rutas críticas de larga distancia.            |
| `price_per_km_w` | > 1300 KM          | Tarifa para transporte internacional o de larga distancia |
|                  |                    |                                                           |

### Modelo - Type.js

**Descripción:**
 Este modelo es la base de jerarquía de servicios. Define las características maestras de una categoría,  límites de carga, es el molde sobre el cual se aplican luego los precios por ciudad.

| Campo                     | Tipo    | Descripción                                |
| :------------------------ | :------ | :----------------------------------------- |
| `typename`                | String  | Nombre principal de la categoría           |
| `typename2`               | String  | Nombre secundario                          |
| `description`             | String  | Descripción de lo que incluye el servicio. |
| `type_image_url`          | String  |                                            |
| `map_pin_image_url`       | String  |                                            |
| `panel_map_pin_image_url` | String  |                                            |
| `service_type`            | Number  |                                            |
| `priority`                | Number  |                                            |
| `is_business`             | Number  |                                            |
| `is_default_selected`     | Boolean |                                            |
| `ride_share_limit`        | Number  | Capacidad máxima                           |
| `type_model_list`         | Array   | IDs de modelos de vehículos permitidos     |
| `type_service_list`       | Array   | IDs de servicios adicionales vinculados.   |
| `type_capacity_list`      | Array   | Capacidades permitidas                     |
| `label_capacity_id`       | Array   | Capacidad de carga.                        |
| `label_measurement_id`    | Array   |                                            |
| `label_pallet_id`         | Array   |                                            |
| `is_use_model`            | Number  |                                            |
| `is_use_capacity`         | Number  |                                            |
| `is_use_services`         | Number  |                                            |
| `model_type`              | Number  |                                            |
| `created_at`              | Date    | Fecha de creación                          |
| `updated_at`              | Date    | Fecha de la última actualización           |

### Modelo - Type_Capacity.js

**Descripción:**
 El modelo permite la gestión   de carga pesada y la naturaleza de la carga.
 
| Campo           | Tipo   | Descripción                       |
| :-------------- | :----- | :-------------------------------- |
| `unique_id`     | Number | IId                               |
| `capacity_name` | String | Nombre                            |
| `value`         | Number | Capacidad                         |
| `state`         | Number | Estatus                           |
| `unit`          | Number | Tipo de medida.                   |
| `created_at`    | Date   | Fecha de creación del registro.   |
| `updated_at`    | Date   | Fecha de la última actualización. |
### Modelo - Type_Model.js

**Descripción:**
 El modelo  gestiona el catálogo de tipos y modelos para un servicio en específicos.

| **Campo**           | **Tipo** | **Descripción**                 |
| ------------------- | -------- | ------------------------------- |
| `unique_id`         | `Number` | Identificador numérico          |
| `model_name`        | `String` | Nombre descriptivo del modelo   |
| `model_image_url`   | `String` |                                 |
| `state`             | `Number` | Estado del registro             |
| `type_service_list` | `Array`  | Lista de IDs de servicios       |
| `sequence`          | `String` |                                 |
| `model_type`        | `Number` |                                 |
| `created_at`        | `Date`   | Fecha de creación.              |
| `updated_at`        | `Date`   | Fecha de la última modificación |

### Modelo - Type_Service.js

**Descripción:**
El modelo `Type_Services` define las reglas operativas de un servicio específico. 

| Campo                 | Tipo   | Descripción                       |
| :-------------------- | :----- | :-------------------------------- |
| `unique_id`           | Number | Identificador numérico            |
| `service_name`        | String | Nombre del servicio               |
| `specification_array` | Array  |                                   |
| `courier_type`        | Number | Lógica de Flujo                   |
| `state`               | Number | Estado del servicio               |
| `created_at`          | Date   | Fecha de creación del registro.   |
| `updated_at`          | Date   | Fecha de la última actualización. |
### Modelo - User.js

**Descripción:**
El modelo  representa al cliente en la plataforma.

| Campo          | Tipo   | Descripción              |
| :------------- | :----- | :----------------------- |
| `unique_id`    | Number | ID numérico              |
| `first_name`   | String | Nombre(s) del usuario.   |
| `last_name`    | String | Apellido(s) del usuario. |
| `email`        | String | Correo electrónico       |
| `phone`        | String | Número telefónico        |
| `password`     | String | Contraseña               |
| `token`        | String | Token de sesió           |
| `device_token` | String | Token de Firebase        |
| `login_by`     | String | Método de acceso.        |
### Modelo - User_Document.js

**Descripción:**
El modelo permite vincular un documento requerido (definido globalmente) con los datos del  usuario.

| Campo                 | Tipo     | Descripción                                                       |
| :-------------------- | :------- | :---------------------------------------------------------------- |
| `document_id`         | ObjectId | Referencia al tipo de documento                                   |
| `name`                | String   | Nombre descriptivo del documento                                  |
| `user_id`             | ObjectId | Referencia al usuario                                             |
| `option`              | Number   | Define si es obligatorio                                          |
| `document_picture`    | String   |                                                                   |
| `is_uploaded`         | Number   | Estado de carga                                                   |
| `unique_code`         | String   |                                                                   |
| `expired_date`        | Date     | Fecha de vencimiento del documento.                               |
| `is_unique_code`      | Boolean  | Indica si el documento requiere obligatoriamente un código único. |
| `is_expired_date`     | Boolean  | Indica si el documento requiere una fecha de vencimiento.         |
| `is_document_expired` | Boolean  |                                                                   |
| `created_at`          | Date     | Fecha de creación del registro.                                   |
| `updated_at`          | Date     | Fecha de la última actualización.                                 |
### Modelo - User_Promo.js

**Descripción:**
El modelo vincula un usuario con un código promocional específico tras la finalización de un viaje. 

| Campo                                | Tipo     | Descripción                       |
| :----------------------------------- | :------- | :-------------------------------- |
| `promo_id`                           | ObjectId | Referencia al documento           |
| `promocode`                          | String   | El código de promoción            |
| `user_id`                            | ObjectId | Referencia al usuario             |
| `promo_type`                         | Number   | Tipo de descuento                 |
| `promo_value`                        | Number   | El valor nominal de la promoción  |
| `trip_id`                            | ObjectId | Referencia al viaje               |
| `user_used_amount`                   | Number   | Monto                             |
| `user_used_amount_in_admin_currency` | Number   | Monto descontado                  |
| `created_at`                         | Date     | Fecha de creación                 |
| `updated_at`                         | Date     | Fecha de la última actualización  |

### Modelo - Wallet_History.js

**Descripción:**
El modelo diseñado para  mantener la trazabilidad financiera de los pago y cobros por servicios.

| Campo                | Tipo   | Descripción                 |
| :------------------- | :----- | :-------------------------- |
| `from_amount`        | Number | Monto                       |
| `from_currency_code` | String | Código de moneda            |
| `to_currency_code`   | String | Código de moneda de destino |
| `current_rate`       | Number | Tasa de cambio              |
| `wallet_status`      | Number | Estatus                     |
### Modelo - Zone_Value.js

**Descripción:**
El modelo se utiliza para aplicar una **tarifa plana** entre dos puntos geográficos.

| Campo                        | Tipo     | Default  | Descripción                                                |
| :--------------------------- | :------- | :------- | :--------------------------------------------------------- |
| `cityid`                     | ObjectId | -        | Referencia de la ciudad                                    |
| `service_type_id`            | ObjectId | -        | ID de la categoría de servicio                             |
| `from`                       | ObjectId | -        | ID de la zona de origen                                    |
| `to`                         | ObjectId | -        | ID de la zona de destino                                   |
| `amount`                     | Number   | 0        | Tarifa plana/fija para el trayecto entre estas zonas.      |
| `partner_profit_fees`        | Number   | 0        | Valor de la ganancia para el socio/proveedor.              |
| `partner_profit_type`        | Number   | -        | Tipo de ganancia                                           |
| `model_id`                   | Array    | `[]`     | Lista de modelos de vehículos permitidos para esta tarifa. |
| `cost_per_helper`            | Number   | -        | Costo adicional por ayudante en esta ruta.                 |
| `night_shift`                | Number   | 0        | Recargo por turno nocturno.                                |
| `boat_ticket`                | Number   | 0        |                                                            |
| `cost_per_stop_inside_city`  | Number   | 0        |                                                            |
| `cost_per_stop_outside_city` | Number   | 0        |                                                            |
| `ti_zone`                    | Number   | -        |                                                            |
| `created_at`                 | Date     | Date.now | Fecha de creación de la tarifa.                            |
| `updated_at`                 | Date     | Date.now | Fecha de la última actualización.                          |






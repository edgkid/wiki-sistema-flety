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

| Campo | Tipo | Default | Descripción |
| :--- | :--- | :--- | :--- |
| `countryid` | ObjectId | - | Referencia al modelo Country. |
| `countryname` | String | "" | Nombre del país al que pertenece la ciudad. |
| `cityname` | String | "" | Nombre corto de la ciudad. |
| `full_cityname` | String | "" | Nombre completo (incluyendo estado/provincia). |
| `timezone` | String | "" | Zona horaria específica de la ciudad. |
| `is_use_city_boundary` | Boolean | false | Indica si se debe validar que el viaje esté dentro de los límites. |
| `city_locations` | Array | [] | Coordenadas que definen el polígono de la ciudad (Index 3D). |
| `cityLatLong` | [Number] | - | Coordenadas centrales (Lat/Long) para geolocalización (Index 2D). |
| `cityRadius` | Number | 50 | Radio operativo en kilómetros desde el centro. |
| `unit` | Number | 1 | Unidad de medida (1: Millas, 2: Kilómetros). |
| `isBusiness` | Number | 1 | Indica si la ciudad está activa para el negocio globalmente. |
| `city_business` | Number | 1 | Flag para habilitar operaciones estándar en la ciudad. |
| `airport_business` | Number | 1 | Flag para habilitar servicios desde/hacia aeropuertos. |
| `zone_business` | Number | 1 | Flag para habilitar servicios por zonas específicas. |
| `is_payment_mode_cash` | Number | 1 | Permite pagos en efectivo en esta ciudad (1: Sí, 0: No). |
| `is_payment_mode_card` | Number | 1 | Permite pagos con tarjeta en esta ciudad. |
| `is_payment_mode_apple_pay` | Number | 0 | Permite Apple Pay. |
| `isPromoApplyForCash` | Number | 1 | Permite usar códigos promocionales en viajes en efectivo. |
| `isPromoApplyForCard` | Number | 1 | Permite usar códigos promocionales en viajes con tarjeta. |
| `destination_city` | [ObjectId] | [] | Lista de IDs de otras ciudades permitidas como destino. |
| `is_ask_user_for_fixed_fare` | Boolean | false | Pregunta al usuario si desea una tarifa fija antes de pedir. |
| `is_caracas` | Boolean | false | Flag específico para lógica personalizada en la ciudad de Caracas. |
| `main_city` | Number | - | Identificador de jerarquía si la ciudad es una capital o principal. |
| `created_at` | Date | Date.now | Fecha de creación del registro. |
| `updated_at` | Date | Date.now | Fecha de la última actualización. |
# Archivo: `Setting.js` 

## Descripción General
Este controlador gestiona el panel de configuración global del sistema, es decir todos los parámetros que rigen el comportamiento de la plataforma; laves de API (Google, Firebase, Stripe), certificados de notificaciones,  términos legales, políticas de privacidad y configuraciones de marca,  se establecen las reglas de negocio para los viajes, las versiones de las apps móviles y las integraciones con servicios de terceros como Twilio para SMS.

---

## Funciones del Controlador

### 1. Configuraciones de Legales
| Función                      | Tipo  | Entrada            | Salida      | Descripción                                                                                  |
| :--------------------------- | :---- | :----------------- | :---------- | :------------------------------------------------------------------------------------------- |
| `installation_settings`      | Async | `req.session`      | Vista HTML  | Carga la interfaz principal de configuración                                                 |
| `terms_and_privacy_setting`  | Sync  | `req.session`      | Vista HTML  | Renderiza la vista para editar los textos legales (términos y condiciones) de la plataforma. |
| `update_provider_terms...`   | Sync  | `req.body.terms`   | Redirección | Actualiza el texto legal de términos y condiciones                                           |
| `update_provider_privacy...` | Sync  | `req.body.privacy` | Redirección | Actualiza la política de privacidad                                                          |
| `update_user_terms...`       | Sync  | `req.body.terms`   | Redirección | Guarda las modificaciones en los términos y condiciones                                      |
| `update_user_privacy...`     | Sync  | `req.body.privacy` | Redirección | Guarda las modificaciones en la política de privacidad para los usuarios finales.            |

### 2. Llaves de API y Comunicaciones
| Función                      | Tipo | Entrada    | Salida      | Descripción                                                                              |
| :--------------------------- | :--- | :--------- | :---------- | :--------------------------------------------------------------------------------------- |
| `update_app_key`             | Sync | `req.body` | Redirección | Actualiza las llaves de seguridad y tokens de autenticación interna de las aplicaciones. |
| `twilio_settings_update`     | Sync | `req.body` | Redirección | Configura las credenciales de Twilio para el envío de SMS.                               |
| `google_api_key_settings...` | Sync | `req.body` | Redirección | Actualiza la API Key de Google Maps para geocodificación y cálculo de rutas.             |
| `gcm_api_key_settings...`    | Sync | `req.body` | Redirección | Configura la llave de Google Cloud Messaging para notificaciones Android.                |
| `update_firebase_key`        | Sync | `req.body` | Redirección | Configura el Firebase Server Key para el envío de notificaciones Push.                   |
| `email_settings_update`      | Sync | `req.body` | Redirección | Configura el servidor SMTP                                                               |

### 3. Identidad y Certificados
| Función                   | Tipo | Entrada     | Salida      | Descripción                                                                       |
| :------------------------ | :--- | :---------- | :---------- | :-------------------------------------------------------------------------------- |
| `upload_logo_images`      | Sync | `req.files` | Redirección | Procesa y guarda los archivos de imagen para el logo del panel, email y facturas. |
| `upload_ios_push_cert...` | Sync | `req.files` | Redirección | Sube los certificados necesarios para las notificaciones push en iOS.             |
| `update_app_name`         | Sync | `req.body`  | Redirección | Cambia el nombre comercial de la app que se muestra en paneles y correos.         |

### 4. Pasarelas de Pago
| Función                        | Tipo | Entrada    | Salida      | Descripción                                               |
| :----------------------------- | :--- | :--------- | :---------- | :-------------------------------------------------------- |
| `payment_gate_way_settings...` | Sync | `req.body` | Redirección | Configura llaves de Stripe  y activa los métodos de pago. |
| `connectium_settings_update`   | Sync | `req.body` | Redirección | Configura la pasarela de pago.                            |

### 5. Parámetros Operativos 

| Función                       | Tipo  | Entrada    | Salida      | Descripción                                                                          |
| :---------------------------- | :---- | :--------- | :---------- | :----------------------------------------------------------------------------------- |
| `admin_settings_update`       | Sync  | `req.body` | Redirección | Actualiza parámetros generales                                                       |
| `trip_settings_update`        | Sync  | `req.body` | Redirección | Configura reglas de viaje                                                            |
| `update_notification_setting` | Async | `req.body` | Redirección | Activa o desactiva  notificaciones                                                   |
| `update_app_version`          | Sync  | `req.body` | Redirección | Define la versión mínima requerida para forzar la actualización de las apps móviles. |
| `android_app_url_settings...` | Sync  | `req.body` | Redirección | Establece los enlaces de descarga de las apps en la Google Play Store.               |
| `ios_app_url_settings...`     | Sync  | `req.body` | Redirección | Establece los enlaces de descarga de las apps en la Apple App Store.                 |

### 6. Configuración Remota y APIs de Datos
| Función                         | Tipo  | Entrada       | Salida      | Descripción                                       |
| :------------------------------ | :---- | :------------ | :---------- | :------------------------------------------------ |
| `settings`                      | Async | `req.session` | JSON        | Retorna las configuraciones actuales del sistema. |
| `update_firebase_remote_config` | Async | `req.body`    | Redirección |                                                   |
| `remove_remote_config_...`      | Async | `req.body.id` | Redirección | Elimina configuraciones de anuncios               |
| `update_app_redict_url`         | Sync  | `req.body`    | Redirección |                                                   |
| `get_advertisement_urls`        | Async | `req.body.id` | JSON        |                                                   |

### Grafo Relacional
EL objetivo es mostrar como se encuentran distribuidas y asociadas las distintas colecciones de documentos en la base de datos Actual



A continuación se muestra la definición de las colecciones existentes en el esquema flety_dev 
 de la base de datos en Mongo del sistema.

### Settings - Collection
 
```json
//// Settings
{
  "_id": { "$oid": "64f1a2b3c4d5e6f7a8b90124" },
  "provider_timeout": 60,
  "countryname": "",
  "adminCurrencyCode": "",
  "adminCurrency": "",
  "adminTimeZone": "",
  "sms_notification": false,
  "email_notification": false,
  "push_notification": false,
  "get_referral_profit_on_card_payment": false,
  "get_referral_profit_on_cash_payment": false,
  "userEmailVerification": false,
  "providerEmailVerification": false,
  "userSms": false,
  "providerSms": false,
  "admin_phone": "",
  "contactUsEmail": "",
  "twilio_call_masking": false,
  "access_key_id": "",
  "secret_key_id": "",
  "aws_bucket_name": "",
  "is_use_aws_bucket": false,
  "image_base_url": "",
  "is_ride_share": false,
  "is_split_payment": false,
  "max_split_user": 5,
  "admin_email": "",
  "default_Search_radious": 100,
  "scheduled_request_pre_start_minute": 30,
  "scheduled_request_day_limit": 3,
  "number_of_try_for_scheduled_request": 1,
  "is_public_demo": false,
  "is_provider_initiate_trip": false,
  "stripe_secret_key": "",
  "stripe_publishable_key": "",
  "paystack_secret_key": "",
  "paystack_publishable_key": "",
  "payu_key": "",
  "payu_salt": "",
  "payment_gateway_type": 10,
  "email": "",
  "password": "",
  "domain": "",
  "provider_offline_min": 30,
  "smtp_host": "",
  "smtp_port": "",
  "is_show_estimation_in_provider_app": false,
  "is_show_estimation_in_user_app": false,
  "twilio_account_sid": "",
  "twilio_auth_token": "",
  "twilio_number": "",
  "twiml_url": "",
  "userPath": false,
  "providerPath": false,
  "android_client_app_url": "",
  "android_driver_app_url": "",
  "ios_client_app_url": "",
  "ios_driver_app_url": "",
  "find_nearest_driver_type": 1,
  "request_send_to_no_of_providers": 2,
  "android_user_app_gcm_key": "",
  "android_provider_app_gcm_key": "",
  "android_user_app_google_key": "",
  "android_provider_app_google_key": "",
  "ios_user_app_google_key": "",
  "ios_provider_app_google_key": "",
  "web_app_google_key": "",
  "road_api_google_key": "",
  "backend_google_key": "",
  "user_passphrase": "",
  "provider_passphrase": "",
  "ios_certificate_mode": "",
  "hotline_app_id": "",
  "hotline_app_key": "",
  "google_map_lic_key": "",
  "is_google_map_lic_key_expired": 0,
  "server_url": "",
  "app_name": "FLETY",
  "partner_panel_name": "",
  "dispatcher_panel_name": "",
  "hotel_panel_name": "",
  "corporate_panel_name": "",
  "is_tip": false,
  "is_toll": false,
  "timezone_for_display_date": "",
  "android_user_app_version_code": "",
  "android_user_app_force_update": false,
  "android_provider_app_version_code": "",
  "android_provider_app_force_update": false,
  "ios_user_app_version_code": "",
  "ios_user_app_force_update": false,
  "ios_provider_app_version_code": "",
  "ios_provider_app_force_update": false,
  "is_debug_log": true,
  "location": [0, 0],
  "firebase_apiKey": "",
  "firebase_authDomain": "",
  "firebase_databaseURL": "",
  "firebase_projectId": "",
  "firebase_storageBucket": "",
  "firebase_messagingSenderId": "",
  "user_terms_and_condition": "",
  "provider_terms_and_condition": "",
  "user_privacy_policy": "",
  "provider_privacy_policy": "",
  "android_places_autocomplete_key": "",
  "ios_places_autocomplete_key": "",
  "team_id": "",
  "key_id": "",
  "provider_bundle_id": "",
  "user_bundle_id": "",
  "type": "",
  "private_key_id": "",
  "private_key": "",
  "client_email": "",
  "client_id": "",
  "auth_uri": "",
  "token_uri": "",
  "auth_provider_x509_cert_url": "",
  "client_x509_cert_url": "",
  "is_user_social_login": true,
  "is_provider_social_login": true,
  "is_guest_token": false,
  "is_otp_verification_start_trip": false,
  "is_receive_new_request_near_destination": false,
  "near_destination_radius": 2000,
  "is_driver_go_home": false,
  "is_driver_go_home_change_address": false,
  "driver_go_home_radius": 2000,
  "is_allow_multiple_stop": false,
  "is_multiple_stop_waiting_free_on_each_stop": false,
  "multiple_stop_count": 3,
  "is_allow_ride_share": false,
  "ride_share_pickup_radius": 3,
  "ride_share_destination_radius": 3,
  "minimum_phone_number_length": 8,
  "maximum_phone_number_length": 14,
  "email_list_trip_notifiy": [],
  "base_url": "",
  "webpush_public_key": "",
  "webpush_private_key": "",
  "server_type": 2,
  "connectium_key": "",
  "connectium_base_url": "",
  "connectium_short_code": "",
  "connectium_dlr": "",
  "connectium_dlr_level": null,
  "connectium_dlr_webhook_url": "",
  "stop_threshold": 50,
  "emails_notify_registration_data": [],
  "tracking_link_sms": false,
  "landing_page_url": "",
  "user_app_insta_ad_url": "",
  "driver_app_insta_ad_url": "",
  "advertise_urls": []
}
```


### Admins - Collection

```json
/// Admins
{
  "_id": { "$oid": "65d7e8f2a1b2c3d4e5f6g7h8" },
  "username": "",
  "password": "",
  "email": "",
  "token": "",
  "type": 0,
  "url_array": [],
  "created_at": { "$date": "" },
  "updated_at": { "$date": "" },
  "uid": "",
  "country_phone_code": "",
  "country_id": { "$oid": "65d7e8f2a1b2c3d4e5f6g799" },
  "super_admin": 1
}

```

### Aiports - Collection

```json
/// airports
{
  "_id": { "$oid": "65d7f1a2b3c4d5e6f7a8b901" },
  "city_id": { "$oid": "65d7f1a2b3c4d5e6f7a8b902" },
  "title": "",
  "kmlzone": [],
  "styleUrl": "",
  "styleHash": "",
  "description": "",
  "stroke": "",
  "stroke_opacity": 0,
  "stroke_width": 0,
  "fill": "",
  "fill_opacity": 0,
  "created_at": { "$date": "" },
  "updated_at": { "$date": "" }
}
```

### Airport_to_cities - Collection

```json
//// Airports_to_cities
{
  "_id": { "$oid": "65d7f5b1e4b0a12345678901" },
  "city_id": { "$oid": "65d7f5b1e4b0a12345678902" },
  "airport_id": { "$oid": "65d7f5b1e4b0a12345678903" },
  "price": 0,
  "service_type_id": { "$oid": "65d7f5b1e4b0a12345678904" },
  "created_at": { "$date": "" },
  "updated_at": { "$date": "" }
}
```


### API Partners - Collections

```json
////api_partners
{
  "_id": { "$oid": "65d802a1b3c4d5e6f7a8b905" },
  "name": "",
  "token": "a1b2c3d4e5f6g7h8i9j0k1l2m3n4o5p6",
  "createdAt": { "$date": "" },
  "updatedAt": { "$date": "" },
  "__v": 0
}

```


### Bank Details - Collections

```json
//// bank_details

{
  "_id": { "$oid": "65d80ba5c4d5e6f7a8b90200" },
  "bank_holder_type": 0,
  "bank_holder_id": { "$oid": "65d80ba5c4d5e6f7a8b90201" },
  "unique_id": 1001,
  "bank_name": "",
  "bank_branch": "",
  "bank_account_number": "",
  "bank_account_holder_name": "",
  "bank_beneficiary_address": "",
  "bank_unique_code": "",
  "bank_swift_code": "",
  "is_updated": 0,
  "created_at": { "$date": "" },
  "updated_at": { "$date": "" }
}

```


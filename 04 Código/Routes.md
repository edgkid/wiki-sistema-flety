
El sistema de rutas funge como interfaz de entrada permitiendo el  _mapping_ entre las peticiones del usuario bajo un contexto  HTTP (GET, POST, PUT, DELETE) y una URL Hacia la logica de los controladores, modelos y services.

# Flujo de  una solicitud
![Flujo de solicitud](../Pasted%20image%2020260202093133.png)

# Recursos que ejecutan una solicitud
![Recursos de solicitud](../Pasted%20image%2020260202092310.png)

# Listado de Rutas Generales 

| Ruta                                      | Controlador (Método)                                   | Tipo |
| :---------------------------------------- | :----------------------------------------------------- | :--- |
| `/getlanguages`                           | `admin.getlanguages`                                   | POST |
| `/getsettingdetail`                       | `admin.getsettingdetail`                               | POST |
| `/generate_firebase_access_token`         | `admin.generate_firebase_access_token`                 | POST |
| `/update_unapprove_status`                | `admin.update_unapprove_status`                        | POST |
| `/upload-proof`                           | `admin.uploadProof`                                    | GET  |
| `/upload-proof`                           | `admin.uploadProofImages`                              | POST |
| `/add_bank_detail`                        | `bankdetail.add_bank_detail`                           | POST |
| `/delete_bank_detail`                     | `bankdetail.delete_bank_detail`                        | POST |
| `/get_bank_detail`                        | `bankdetail.get_bank_detail`                           | POST |
| `/add_bank_detail_web`                    | `bankdetail.add_bank_detail_web`                       | POST |
| `/addcard`                                | `card.add_card`                                        | POST |
| `/delete_card`                            | `card.delete_card`                                     | POST |
| `/cardscard`                              | `card.card_list`                                       | POST |
| `/card_selection`                         | `card.card_selection`                                  | POST |
| `/userchangepaymenttype`                  | `card.change_paymenttype`                              | POST |
| `/get_stripe_add_card_intent`             | `card.get_stripe_add_card_intent`                      | POST |
| `/paystack_add_card_callback`             | `card.paystack_add_card_callback`                      | GET  |
| `/get_stripe_payment_intent`              | `card.get_stripe_payment_intent`                       | POST |
| `/send_paystack_required_detail`          | `card.send_paystack_required_detail`                   | POST |
| `/fail_payment`                           | `card.fail_payment`                                    | POST |
| `/citilist_selectedcountry`               | `city.citylist`                                        | POST |
| `/typelist_selectedcountrycity`           | `citytype.list`                                        | POST |
| `/typelist_for_dispatcher`                | `citytype.disptcher_city_type_list`                    | POST |
| `/user_city_type_list`                    | `citytype.list`                                        | POST |
| `/w_typelist`                             | `citytype.new_web_typelist`                            | GET  |
| `/w_typelist`                             | `citytype.new_web_typelist`                            | POST |
| `/country_list`                           | `country.countries_list`                               | GET  |
| `/country_list`                           | `country.countries_list`                               | POST |
| `/get_country_city_list`                  | `country.get_country_city_list`                        | POST |
| `/cities_list/:countryId`                 | `country.countries_list`                               | GET  |
| `/add_emergency_contact`                  | `emergencyContactDetail.add_emergency_contact`         | POST |
| `/update_emergency_contact`               | `emergencyContactDetail.update_emergency_contact`      | POST |
| `/delete_emergency_contact`               | `emergencyContactDetail.delete_emergency_contact`      | POST |
| `/get_emergency_contact_list`             | `emergencyContactDetail.get_emergency_contact_list`    | POST |
| `/send_sms_to_emergency_contact`          | `emergencyContactDetail.send_sms_to_emergency_contact` | POST |
| `/get_provider_daily_earning_detail`      | `provider_earning.get_provider_daily_earning_detail`   | POST |
| `/get_provider_weekly_earning_detail`     | `provider_earning.get_provider_weekly_earning_detail`  | POST |
| `/uploaddocument`                         | `providerdocument.uploaddocument`                      | POST |
| `/getproviderdocument`                    | `providerdocument.getproviderdocument`                 | POST |
| `/providerregister`                       | `providers.provider_register`                          | POST |
| `/providerupdatedetail`                   | `providers.provider_update`                            | POST |
| `/provider_location`                      | `providers.update_location`                            | POST |
| `/providerslogin`                         | `providers.provider_login`                             | POST |
| `/providerlogout`                         | `providers.logout`                                     | POST |
| `/togglestate`                            | `providers.change_provider_status`                     | POST |
| `/toggle_go_home`                         | `providers.change_go_home_status`                      | POST |
| `/get_provider_detail`                    | `providers.get_provider_detail`                        | POST |
| `/get_provider_info`                      | `providers.get_provider_info`                          | POST |
| `/getproviderlatlong`                     | `providers.getproviderlatlong`                         | POST |
| `/providerupdatetype`                     | `providers.provider_updatetype`                        | POST |
| `/updateproviderdevicetoken`              | `providers.update_device_token`                        | POST |
| `/provider_heat_map`                      | `providers.provider_heat_map`                          | POST |
| `/apply_provider_referral_code`           | `providers.apply_provider_referral_code`               | POST |
| `/get_provider_referal_credit`            | `providers.get_provider_referal_credit`                | POST |
| `/get_provider_terms_and_condition`       | `providers.get_provider_terms_and_condition`           | GET  |
| `/get_provider_privacy_policy`            | `providers.get_provider_privacy_policy`                | GET  |
| `/provider_add_vehicle`                   | `providers.provider_add_vehicle`                       | POST |
| `/upload_vehicle_document`                | `providers.upload_vehicle_document`                    | POST |
| `/get_provider_vehicle_list`              | `providers.get_provider_vehicle_list`                  | POST |
| `/change_current_vehicle`                 | `providers.change_current_vehicle`                     | POST |
| `/delete_provider`                        | `providers.delete_provider`                            | POST |
| `/get_provider_rating`                    | `providers.get_provider_rating`                        | POST |
| `/get_provider_trip_details`              | `providers.get_provider_trip_details`                  | POST |
| `/getfuturetrip`                          | `scheduledtrip.getfuturetrip`                          | POST |
| `/cancelscheduledtrip`                    | `scheduledtrip.cancelScheduledtrip`                    | POST |
| `/createtrip`                             | `trip.create`                                          | POST |
| `/provider_createtrip`                    | `trip.provider_create`                                 | POST |
| `/send_request`                           | `trip.send_request_from_dispatcher`                    | POST |
| `/gettripstrip`                           | `trip.provider_get_trips`                              | POST |
| `/gettripsdetailstrip`                    | `trip.provider_get_trip_details`                       | POST |
| `/usergettripstatus`                      | `trip.user_get_trip_status`                            | POST |
| `/respondstrip`                           | `trip.responds_trip`                                   | POST |
| `/canceltrip`                             | `trip.trip_cancel_by_user`                             | POST |
| `/tripcancelbyprovider`                   | `trip.trip_cancel_by_provider`                         | POST |
| `/tripcancelbyadmin`                      | `trip.trip_cancel_by_admin`                            | POST |
| `/scheduledtripcancelbyadmin`             | `trip.scheduled_trip_cancel_by_admin`                  | POST |
| `/settripstatus`                          | `trip.provider_set_trip_status`                        | POST |
| `/settripstopstatus`                      | `trip.provider_set_trip_stop_status`                   | POST |
| `/completetrip`                           | `trip.provider_complete_trip`                          | POST |
| `/tripeditbyadmin`                        | `trip.edit_trip`                                       | GET  |
| `/updatetrip`                             | `trip.update_trip`                                     | POST |
| `/pay_payment`                            | `trip.pay_payment`                                     | POST |
| `/pay_tip_payment`                        | `trip.pay_tip_payment`                                 | POST |
| `/pay_stripe_intent_payment`              | `trip.pay_stripe_intent_payment`                       | POST |
| `/fail_stripe_intent_payment`             | `trip.fail_stripe_intent_payment`                      | POST |
| `/userhistory`                            | `trip.user_history`                                    | POST |
| `/usertripdetail`                         | `trip.user_tripdetail`                                 | POST |
| `/providertripdetail`                     | `trip.provider_tripdetail`                             | POST |
| `/providergettripstatus`                  | `trip.providergettripstatus`                           | POST |
| `/providerhistory`                        | `trip.provider_history`                                | POST |
| `/usergiverating`                         | `trip.user_rating`                                     | POST |
| `/providergiverating`                     | `trip.provider_rating`                                 | POST |
| `/providergivedestinationrating`          | `trip.provider_destination_rating`                     | POST |
| `/getuserinvoice`                         | `trip.user_invoice`                                    | POST |
| `/getproviderinvoice`                     | `trip.provider_invoice`                                | POST |
| `/usersetdestination`                     | `trip.user_setdestination`                             | POST |
| `/getgooglemappath`                       | `trip.getgooglemappath`                                | POST |
| `/setgooglemappath`                       | `trip.setgooglemappath`                                | POST |
| `/optimize_route`                         | `trip.optimize_route`                                  | POST |
| `/get_optimized_route`                    | `trip.get_optimized_route`                             | POST |
| `/check_destination`                      | `trip.check_destination`                               | POST |
| `/user_submit_invoice`                    | `trip.user_submit_invoice`                             | POST |
| `/provider_submit_invoice`                | `trip.provider_submit_invoice`                         | POST |
| `/getnearbyprovider`                      | `trip.get_near_by_provider`                            | POST |
| `/twilio_voice_call`                      | `trip.twilio_voice_call`                               | POST |
| `/refund_amount_in_wallet`                | `trip.refund_amount_in_wallet`                         | POST |
| `/refund_amount_in_card`                  | `trip.refund_amount_in_card`                           | POST |
| `/upload_trip_images`                     | `trip.upload_trip_images`                              | POST |
| `/upload_pod_image`                       | `trip.upload_pod_images`                               | POST |
| `/upload_pod_per_stop`                    | `trip.upload_pod_per_stop`                             | POST |
| `/pay_by_other_payment_mode`              | `trip.pay_by_other_payment_mode`                       | POST |
| `/get_provider_assigned_trips`            | `trip.get_provider_assigned_trips`                     | POST |
| `/provider_confirm_trip`                  | `trip.provider_confirm_trip`                           | POST |
| `/web_fareestimate`                       | `trip.w_fareestimate`                                  | POST |
| `/upload_chat_images`                     | `trip.upload_chat_images`                              | POST |
| `/complete_card_payment_trip`             | `trip.complete_card_payment_trip`                      | POST |
| `/userPendingTrips`                       | `trip.userPendingTrips`                                | POST |
| `/providerDropTrip`                       | `trip.providerDropTrip`                                | POST |
| `/userNotifyUnload`                       | `trip.userNotifyUnload`                                | POST |
| `/provider_change_drop_trip_status`       | `trip.provider_change_drop_trip_status`                | POST |
| `/userGetTripVehicleDocs`                 | `trip.user_get_trip_vehicle_docs`                      | POST |
| `/uploaduserdocument`                     | `userdocument.uploaduserdocument`                      | POST |
| `/getuserdocument`                        | `userdocument.userdocument_list`                       | POST |
| `/check_user_registered`                  | `users.check_user_registered`                          | POST |
| `/get_otp`                                | `users.get_otp`                                        | POST |
| `/update_password`                        | `users.update_password`                                | POST |
| `/verification`                           | `users.verification`                                   | POST |
| `/verify_email_phone`                     | `users.verify_email_phone`                             | POST |
| `/userregister`                           | `users.user_register`                                  | POST |
| `/userupdate`                             | `users.user_update`                                    | POST |
| `/userslogin`                             | `users.user_login`                                     | POST |
| `/add_wallet_amount`                      | `users.add_wallet_amount`                              | POST |
| `/change_user_wallet_status`              | `users.change_user_wallet_status`                      | POST |
| `/logout`                                 | `users.logout`                                         | POST |
| `/apply_referral_code`                    | `users.apply_referral_code`                            | POST |
| `/getuserdetail`                          | `users.get_user_detail`                                | POST |
| `/getfareestimate`                        | `users.getfareestimate`                                | POST |
| `/aproxdistance`                          | `users.aproxdistance`                                  | POST |
| `/apply_promo_code`                       | `users.apply_promo_code`                               | POST |
| `/remove_promo_code`                      | `users.remove_promo_code`                              | POST |
| `/updateuserdevicetoken`                  | `users.update_device_token`                            | POST |
| `/get_user_referal_credit`                | `users.get_user_referal_credit`                        | POST |
| `/forgotpassword`                         | `users.forgotpassword`                                 | POST |
| `/optimizedorder`                         | `users.newOptimizedOrder`                              | POST |
| `/new-optimizedorder`                     | `users.newOptimizedOrder`                              | POST |
| `/get_user_setting_detail`                | `users.get_user_setting_detail`                        | POST |
| `/get_user_privacy_policy`                | `users.get_user_privacy_policy`                        | GET  |
| `/get_user_terms_and_condition`           | `users.get_user_terms_and_condition`                   | GET  |
| `/set_home_address`                       | `users.set_home_address`                               | POST |
| `/get_home_address`                       | `users.get_home_address"                               | POST |
| `/user_accept_reject_corporate_request`   | `users.user_accept_reject_corporate_request`           | POST |
| `/add_favourite_driver`                   | `users.add_favourite_driver`                           | POST |
| `/get_favourite_driver`                   | `users.get_favourite_driver`                           | POST |
| `/remove_favourite_driver`                | `users.remove_favourite_driver`                        | POST |
| `/get_all_driver_list`                    | `users.get_all_driver_list`                            | POST |
| `/search_user_for_split_payment`          | `users.search_user_for_split_payment`                  | POST |
| `/send_split_payment_request`             | `users.send_split_payment_request`                     | POST |
| `/accept_or_reject_split_payment_request` | `users.accept_or_reject_split_payment_request`         | POST |
| `/remove_split_payment_request`           | `users.remove_split_payment_request`                   | POST |
| `/update_split_payment_payment_mode`      | `users.update_split_payment_payment_mode`              | POST |
| `/delete_user`                            | `users.delete_user`                                    | POST |
| `/get_user_trip_details`                  | `users.get_user_trip_details`                          | POST |
| `/chat_push_notification`                 | `users.chat_push_notification`                         | POST |
| `/get_user_running_trips`                 | `users.running_trips`                                  | POST |
| `/need-ferry`                             | `users.need_ferry`                                     | POST |
| `/get_user_account_deletion_info`         | `users.user_account_deletion_info`                     | GET  |
| `/get_wallet_history`                     | `wallet_history.get_wallet_history`                    | POST |


### Listado de Rutas API Partner

| Ruta                       | Controlador (Método)         | Tipo |
| :------------------------- | :--------------------------- | :--- |
| `/need-ferry`              | `trips.needFerry`            | POST |
| `/getfareestimate`         | `trips.getFareEstimate`      | POST |
| `/createtrip`              | `trips.create`               | POST |
| `/citytype/capacity-types` | `selects.getCapacitiesTypes` | POST |
| `/citytype/services`       | `selects.getServicesTypes`   | POST |
| `/citytype/types`          | `selects.getTypeByTypeId`    | POST |
| `/citytype/models-types`   | `selects.getModelsCars`      | POST |
| `/citytype/service-types`  | `selects.getCityTypes`       | POST |
| `/user-info/:phone`        | `getInfo`                    | GET  |

### Listado de Rutas User

| Ruta                                      | Controlador (Método)                           | Tipo |
| :---------------------------------------- | :--------------------------------------------- | :--- |
| `/terms&condition`                        | `users.terms`                                  | GET  |
| `/privacy`                                | `users.privacy`                                | GET  |
| `/payments`                               | `payments.user_payments`                       | GET  |
| `/card_type`                              | `payments.card_type`                           | POST |
| `/add_card`                               | `payments.add_card`                            | POST |
| `/delete_user_card`                       | `payments.delete_card`                         | POST |
| `/user_card_selection`                    | `payments.card_selection`                      | POST |
| `/check_card`                             | `payments.check_card`                          | POST |
| `/user_add_wallet_amount`                 | `payments.user_add_wallet_amount`              | POST |
| `/create_trip`                            | `users.user_create_trip`                       | GET  |
| `/get_nearby_provider`                    | `users.get_nearby_provider`                    | POST |
| `/history`                                | `users.user_request`                           | GET  |
| `/history`                                | `users.user_request`                           | POST |
| `/user_chat_history`                      | `users.user_chat_history`                      | POST |
| `/user_future_request`                    | `users.user_future_request`                    | GET  |
| `/user_future_request`                    | `users.user_future_request`                    | POST |
| `/generate_user_future_trip_export_excel` | `users.generate_user_future_trip_export_excel` | POST |
| `/check_old_trip`                         | `users.check_old_trip`                         | POST |
| `/user_trip_map`                          | `users.user_trip_map`                          | POST |
| `/user_trip_invoice`                      | `users.user_trip_invoice`                      | POST |
| `/register`                               | `users.user_register`                          | GET  |
| `/user_register`                          | `users.user_register_post`                     | POST |
| `/login`                                  | `users.user_login`                             | GET  |
| `/`                                       | `users.landing`                                | GET  |
| `/user_login`                             | `users.user_login_post`                        | POST |
| `/logout`                                 | `users.user_sign_out`                          | GET  |
| `/trip_map`                               | `users.user_trip_map`                          | POST |
| `/profiles`                               | `users.user_profile`                           | GET  |
| `/user_profile_update`                    | `users.user_profile_update`                    | POST |
| `/check_promocode`                        | `users.check_promocode`                        | POST |
| `/user_forgot_password`                   | `users.forgot_password`                        | GET  |
| `/user_forgot_password`                   | `users.forgot_psw_email`                       | POST |
| `/user_update_psw`                        | `users.update_psw`                             | POST |
| `/user_newpassword`                       | `users.edit_psw`                               | GET  |
| `/user_document_panel`                    | `users.user_document_panel`                    | GET  |
| `/user_document_panel`                    | `users.user_document_panel`                    | POST |
| `/change_password`                        | `users.change_password`                        | POST |
| `/referral_user`                          | `users.apply_referral_code`                    | POST |
| `/user_social_login_web`                  | `users.user_social_login_web`                  | POST |
| `/user_document_edit`                     | `users.user_documents_edit`                    | POST |
| `/user_document_update`                   | `users.user_documents_update`                  | POST |
| `/generate_user_history_export_excel`     | `users.generate_user_history_export_excel`     | POST |


### Listado de Rutas Provider

| Ruta                               | Controlador (Método)                              | Tipo       |
| :--------------------------------- | :------------------------------------------------ | :--------- |
| `/provider_payments`               | `provider_payments.provider_payments`             | GET        |
| `/provider_add_card`               | `provider_payments.add_card`                      | POST       |
| `/delete_provider_card`            | `provider_payments.delete_card`                   | POST       |
| `/provider_card_selection`         | `provider_payments.card_selection`                | POST       |
| `/provider_add_wallet_amount`      | `provider_payments.provider_add_wallet_amount`    | POST       |
| `/provider_register`               | `providers.provider_register`                     | GET        |
| `/provider_register`               | `providers.provider_register_post`                | POST       |
| `/provider_login`                  | `providers.provider_login`                        | GET        |
| `/provider_login`                  | `providers.provider_login_post`                   | POST       |
| `/provider_logout`                 | `providers.provider_sign_out`                     | GET        |
| `/provider_trip_map`               | `providers.provider_trip_map`                     | POST       |
| `/provider_profiles`               | `providers.provider_profile`                      | GET        |
| `/provider_profile_update`         | `providers.provider_profile_update`               | POST       |
| `/provider_document_panel`         | `providers.provider_document_panel`               | GET / POST |
| `/provider_forgot_password`        | `providers.forgot_password`                       | GET        |
| `/provider_forgot_password`        | `providers.forgot_psw_email`                      | POST       |
| `/provider_update_psw`             | `providers.update_psw`                            | POST       |
| `/provider_newpassword`            | `providers.edit_psw`                              | GET        |
| `/provider_earnings`               | `provider_earning.provider_earning`               | POST       |
| `/provider_daily_earnings`         | `provider_daily_earning.provider_daily_earning`   | POST       |
| `/provider_weekly_earnings`        | `provider_weekly_earning.provider_weekly_earning` | POST       |
| `/provider_social_login_web`       | `providers.provider_social_login_web`             | POST       |
| `/provider_vehicle`                | `providers.provider_vehicle`                      | GET        |
| `/provider_add_vehicle_details`    | `providers.provider_add_vehicle_details`          | POST       |
| `/provider_edit_vehicle_detail`    | `providers.edit_vehicle_detail`                   | POST       |
| `/provider_add_vehicle`            | `providers.provider_add_vehicle`                  | GET        |
| `/provider_update_vehicle_details` | `providers.update_vehicle_detail`                 | POST       |
| `/provider_vehicle_document_list`  | `providers.vehicle_document_list`                 | POST       |
| `/vehicle_documents_edit`          | `providers.provider_vehicle_documents_edit`       | POST       |
| `/vehicle_documents_update`        | `providers.provider_vehicle_documents_update`     | POST       |
| `/provider_document_edit`          | `providers.provider_documents_edit`               | POST       |
| `/provider_document_update`        | `providers.provider_documents_update`             | POST       |
| `/provider-terms&condition`        | `providers.terms`                                 | GET        |
| `/provider-privacy`                | `providers.privacy`                               | GET        |
| `/provider_history`                | `providers.provider_request`                      | GET        |
| `/provider_history`                | `providers.provider_request`                      | POST       |
| `/provider_wallet_history`         | `providers.provider_wallet_history`               | GET        |
| `/provider_wallet_history`         | `providers.provider_wallet_history`               | POST       |
| `/provider_history_export_excel`   | `providers.provider_history_export_excel`         | POST       |



# Archivo: `Partner.js`

## Descripción General
Este controlador gestiona el ciclo de vida completo de los asociados. Cubre desde la autenticación, gestión de conductores y vehículos, hasta la analítica financiera, exportación de reportes y configuración de perfiles.

---

## 1. Autenticación 

| Función                         | Tipo   | Entrada             | Salida           | Descripción                                       |
| :------------------------------ | :----- | :------------------ | :--------------- | :------------------------------------------------ |
| `partner_login`                 | Async  | `email`, `password` | Redirección      | Valida credenciales y crea la sesión              |
| `partner_login_web`             | Async  | `email`, `password` | Redirección      | Variante de login optimizada para acceso vía web. |
| `partner_logout`                | Sync   | `req.session`       | Redirección      | Finaliza la sesión                                |
| `partner_forgot_password`       | Async  | `email`             | JSON/Redirección | Inicia el proceso de recuperación de contraseña.  |
| `partner_forgot_password_email` | Async  | `email`             | Redirección      | Envía el enlace de recuperación de contraseña     |
| `partner_edit_psw`              | Render | `id`, `token`       | Vista HTML       | Muestra formulario para nueva contraseña.         |
| `partner_update_psw`            | Async  | `password`          | Redirección      | Actualiza la contraseña en la base de datos.      |

## 2. Gestión de Perfil 

| Función                  | Tipo  | Entrada             | Salida      | Descripción                    |
| :----------------------- | :---- | :------------------ | :---------- | :----------------------------- |
| `partner_profile`        | Async | `session`           | Vista HTML  | Muestra los datos de asociados |
| `update_partner_profile` | Async | `req.body`, `files` | Redirección | Actualiza información .        |
| `partner_detail_edit`    | Async | `id`                | Vista HTML  | Permite editar                 |
| `partner_detail_update`  | Async | `req.body`          | Redirección | Guarda cambios de asociados    |

## 3. Administración de Proveedores/Conductores

| Función                               | Tipo   | Entrada        | Salida      | Descripción                                      |
| :------------------------------------ | :----- | :------------- | :---------- | :----------------------------------------------- |
| `partner_providers`                   | Async  | `filters`      | Vista HTML  | Lista los conductores pertenecientes al asocaido |
| `partner_add_provider_form`           | Render | N/A            | Vista HTML  | Formulario para registrar un nuevo conductor.    |
| `partner_add_provider_detail`         | Async  | `req.body`     | Redirección | Crea el perfil del conductor vinculado al Socio. |
| `partner_edit_provider`               | Async  | `id`           | Vista HTML  | Carga datos del conductor para edición.          |
| `partner_update_provider`             | Async  | `req.body`     | Redirección | Actualiza del conductor.                         |
| `partner_provider_active_decline`     | Async  | `id`, `status` | JSON        | Activa o suspende a un conductor.                |
| `partner_provider_location`           | Async  | `id`           | JSON        | Obtiene coordenadas actuales del conductor.      |
| `partner_provider_history`            | Async  | `id`           | Vista HTML  | Historial de viajes de un conductor              |
| `partner_provider_reviews`            | Async  | `id`           | Vista HTML  | Calificaciones recibidas por el conductor.       |
| `partner_provider_bank_detail`        | Async  | `id`           | Vista HTML  | Gestión de datos bancarios para pagos.           |
| `partner_provider_bank_detail_update` | Async  | `req.body`     | Redirección | Actualiza cuenta bancaria del conductor.         |
| `partner_approve_decline_provider`    | Async  | `id`, `state`  | JSON        | Aprobación administrativa de conductores.        |
| `partner_delete_provider`             | Async  | `id`           | JSON        | Elimina al conductor de la flota del asociado.   |



## 4. Gestión de Vehículos

| Función                          | Tipo   | Entrada       | Salida      | Descripción                                        |
| :------------------------------- | :----- | :------------ | :---------- | :------------------------------------------------- |
| `partner_vehicles`               | Async  | `session`     | Vista HTML  | Lista de vehículos registrados por asociado.       |
| `partner_add_vehicle_form`       | Render | N/A           | Vista HTML  | Formulario para añadir vehículo a la flota.        |
| `partner_add_vehicle_detail`     | Async  | `req.body`    | Redirección | Registra vehículo y sus características técnicas.  |
| `partner_edit_vehicle`           | Async  | `id`          | Vista HTML  | Formulario de edición de vehículo.                 |
| `partner_update_vehicle`         | Async  | `req.body`    | Redirección | Actualiza datos                                    |
| `partner_vehicle_active_decline` | Async  | `id`, `state` | JSON        | Cambia estado de disponibilidad del vehículo.      |
| `partner_delete_vehicle`         | Async  | `id`          | JSON        | Elimina el vehículo del sistema.                   |
| `get_type_model_data`            | Async  | `type_id`     | JSON        | Retorna modelos según el tipo de servicio.         |
| `get_service_type_model_data`    | Async  | `id`          | JSON        | Filtra servicios aplicables al modelo de vehículo. |

## 5. Historial y Seguimiento de Viajes 

| Función                  | Tipo  | Entrada   | Salida     | Descripción                                        |
| :----------------------- | :---- | :-------- | :--------- | :------------------------------------------------- |
| `partner_history`        | Async | `filters` | Vista HTML | Listado general de viajes realizados por la flota. |
| `partner_trip_details`   | Async | `id`      | Vista HTML | Detalle completo de un viaje (mapa, costos).       |
| `partner_future_trip`    | Async | `filters` | Vista HTML | Listado de viajes programados/futuros.             |
| `partner_trip_map`       | Async | `id`      | Vista HTML | Visualización del recorrido en el mapa.            |
| `partner_running_trip`   | Async | `filters` | Vista HTML | Muestra viajes que están ocurriendo ahora.         |
| `partner_track_provider` | Async | `id`      | Vista HTML | Seguimiento GPS                                    |
| `partner_view_invoice`   | Async | `id`      | Vista HTML | Genera la factura digital del viaje.               |
| `partner_render_map`     | Async | `id`      | Vista HTML | Carga el mapa dinámico para tracking.              |
| `partner_cancel_trip`    | Async | `trip_id` | JSON       | Permite cancelar un viaje de su flota.             |

## 6. Gestión Documental 

| Función                            | Tipo  | Entrada    | Salida      | Descripción                                   |
| :--------------------------------- | :---- | :--------- | :---------- | :-------------------------------------------- |
| `partner_provider_documents`       | Async | `id`       | Vista HTML  | Lista documentos del conductor                |
| `partner_provider_document_edit`   | Async | `id`       | Vista HTML  | Formulario para resubir documento.            |
| `partner_provider_document_update` | Async | `req.body` | Redirección | Procesa el archivo y actualiza fechas.        |
| `partner_vehicle_documents`        | Async | `id`       | Vista HTML  | Lista documentos del vehículo                 |
| `partner_vehicle_document_edit`    | Async | `id`       | Vista HTML  | Formulario para editar documento de vehículo. |
| `partner_vehicle_document_update`  | Async | `req.body` | Redirección | Actualiza archivos y vigencia del documento.  |

## 7. Finanzas y Billetera 

| Función                      | Tipo  | Entrada   | Salida      | Descripción                                     |
| :--------------------------- | :---- | :-------- | :---------- | :---------------------------------------------- |
| `partner_wallet_history`     | Async | `filters` | Vista HTML  | Movimientos de dinero en la cuenta del asociado |
| `partner_add_wallet_amount`  | Async | `amount`  | Redirección | Recarga de saldo vía pasarela de pago.          |
| `partner_earnings`           | Async | `filters` | Vista HTML  | Resumen de ingresos por periodos.               |
| `partner_daily_earning`      | Async | `date`    | Vista HTML  | Desglose de ganancias de un día específico.     |
| `partner_weekly_earning`     | Async | `range`   | Vista HTML  | Reporte consolidado de la semana.               |
| `partner_weekly_statement`   | Async | `id`      | Vista HTML  | Estado de cuenta para descarga.                 |
| `get_partner_wallet_history` | Async | `filters` | JSON        | Consulta movimientos de billetera.              |
| `partner_request_payout`     | Async | `amount`  | JSON        | Solicita retiro de fondos a cuenta bancaria.    |

## 8. Reportes 

| Función                               | Tipo  | Entrada   | Salida | Descripción                               |
| :------------------------------------ | :---- | :-------- | :----- | :---------------------------------------- |
| `partner_export_excel`                | Async | `filters` | Excel  | Exporta historial de viajes a .xlsx.      |
| `partner_export_csv`                  | Async | `filters` | CSV    | Exporta historial de viajes a .csv.       |
| `partner_provider_export_excel`       | Async | `filters` | Excel  | Exporta lista de conductores a .xlsx.     |
| `partner_provider_export_csv`         | Async | `filters` | CSV    | Exporta lista de conductores a .csv.      |
| `partner_vehicle_export_excel`        | Async | `filters` | Excel  | Exporta lista de vehículos a .xlsx.       |
| `partner_vehicle_export_csv`          | Async | `filters` | CSV    | Exporta lista de vehículos a .csv.        |
| `partner_wallet_history_export_excel` | Async | `filters` | Excel  | Exporta movimientos de billetera a .xlsx. |
| `partner_wallet_history_export_csv`   | Async | `filters` | CSV    | Exporta movimientos de billetera a .csv.  |
| `partner_earning_export_excel`        | Async | `filters` | Excel  | Exporta reporte de ganancias a .xlsx.     |
| `partner_earning_export_csv`          | Async | `filters` | CSV    | Exporta reporte de ganancias a .csv.      |
| `partner_future_trip_export_excel`    | Async | `filters` | Excel  | Exporta viajes programados a .xlsx.       |
| `partner_future_trip_export_csv`      | Async | `filters` | CSV    | Exporta viajes programados a .csv.        |

## 9. Funciones Administrativas  

| Función                  | Tipo   | Entrada        | Salida      | Descripción                             |
| :----------------------- | :----- | :------------- | :---------- | :-------------------------------------- |
| `partners`               | Async  | `filters`      | Vista HTML  | Listado de todos los asociados          |
| `add_partner_form`       | Render | N/A            | Vista HTML  | Registro manual de un nuevo asociado.   |
| `add_partner_detail`     | Async  | `req.body`     | Redirección | Guarda nuevo asociado                   |
| `edit_partner`           | Async  | `id`           | Vista HTML  | Edición de cuenta de Asocaido           |
| `update_partner`         | Async  | `req.body`     | Redirección | Actualiza datos de asocaido.            |
| `partner_active_decline` | Async  | `id`, `status` | JSON        | Suspende o habilita cuenta de asociado. |
| `delete_partner`         | Async  | `id`           | JSON        | Elimina asociado                        |
| `export_partner_excel`   | Async  | `filters`      | Excel       | Exporta censo de asociados              |
| `export_partner_csv`     | Async  | `filters`      | CSV         | Exporta censo de asociados.             |
| `get_partner_data`       | Async  | `id`           | JSON        |                                         |

## 10. Lógica Interna y Helpers 

| Función                    | Tipo    | Entrada      | Salida   | Descripción                                    |
| :------------------------- | :------ | :----------- | :------- | :--------------------------------------------- |
| `check_partner_available`  | Async   | `email`      | JSON     | Valida si el correo ya está en uso.            |
| `get_partner_list`         | Async   | `country_id` | JSON     | Lista nombres de asociados por país.           |
| `get_city_list`            | Async   | `country_id` | JSON     | Lista ciudades operativas.                     |
| `get_service_type_list`    | Async   | `city_id`    | JSON     | Lista tipos de servicios en la ciudad.         |
| `get_type_model_list`      | Async   | `type_id`    | JSON     | Lista modelos de vehículos permitidos.         |
| `get_document_list`        | Async   | `country_id` | JSON     | Lista requisitos de docuementos por región.    |
| `get_vehicle_list`         | Async   | `partner_id` | JSON     | Lista vehículos activos del asociado.          |
| `get_provider_list`        | Async   | `partner_id` | JSON     | Lista conductores libres para asignar.         |
| `get_partner_vehicle_list` | Async   | `partner_id` | JSON     | Helper para obtener vehículos filtrados.       |
| `toObjectId`               | Interna | `string`     | ObjectId | Convierte strings a formato BSON de MongoDB.   |
| `getUniqueIds`             | Interna | `array`      | Array    | Filtra IDs únicos en colecciones de servicios. |
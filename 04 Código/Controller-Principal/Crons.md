# Archivo: `cron.js`

## Descripción General
Este controlador define un conjunto de tareas programadas (**Crons**) que se ejecutan automáticamente en intervalos definidos para supervisar el estado de la plataforma, automatizar despachos, gestionar pagos y mantener la integridad de los datos sin intervención manual.

---

## Tareas Programadas (Cron Jobs)

| Función                        | Tipo | Intervalo      | Salida              | Descripción                                                                        |
| :----------------------------- | :--- | :------------- | :------------------ | :--------------------------------------------------------------------------------- |
| `run_continue_30_sec_cron`     | Cron | 30 segundos    | Ejecución de tareas | Bucle principal que dispara la búsqueda de conductores para viajes pendientes.     |
| `run_continue_1_min_cron`      | Cron | 1 minuto       | Ejecución de tareas | Gestiona la expiración de solicitudes y actualiza estados de viaje en tiempo real. |
| `run_continue_every_hour_cron` | Cron | 1 hora         | Notificaciones/Logs | Ejecuta procesos de limpieza y verifica integridad de datos horaria.               |
| `run_daily_cron`               | Cron | Diario (00:00) | Reportes/Reset      | Resetea analíticas diarias y genera resúmenes de ingresos para proveedores.        |

---

## Funciones de Lógica de Automatización

| Función                         | Tipo  | Entrada               | Salida             | Descripción                                                                                  |
| :------------------------------ | :---- | :-------------------- | :----------------- | :------------------------------------------------------------------------------------------- |
| `check_scheduled_trip`          | Async | N/A                   | Trip Activado      | Revisa la tabla de `ScheduledTrip` y activa viajes cuya hora de inicio sea inminente.        |
| `assign_provider_for_trip`      | Async | `trip_id`             | Notificación Push  | Lógica de selección de conductor cercano y envío de la solicitud de servicio.                |
| `auto_transfer_earning`         | Async | N/A                   | Transferencias     | Procesa pagos automáticos de ganancias semanales a las cuentas bancarias de los proveedores. |
| `check_document_expiry`         | Async | N/A                   | Alertas Push/Email | Escanea documentos y avisa a conductores/usuarios si alguno está por vencer.                 |
| `getOnlineProviderAnalytics`    | Sync  | `city_id`, `timezone` | Stats actualizadas | Calcula y guarda el tiempo total que los conductores pasaron en línea durante el día.        |
| `review_notification`           | Async | N/A                   | Notificación Push  | Envía recordatorio a usuarios que no calificaron su último viaje completado.                 |
| `check_provider_status`         | Async | N/A                   | Cambio de estado   | Detecta conductores sin conexión o inactivos para pasarlos a estado "Offline".               |
| `handler_for_no_provider`       | Sync  | `trip_id`             | Cancelación/Alerta | Gestiona el flujo cuando no se encuentra conductor tras agotar los intentos de búsqueda.     |
| `send_monthly_report`           | Async | N/A                   | Email (PDF)        | Genera y envía el estado de cuenta mensual a los socios comerciales.                         |
| `remove_expired_sessions`       | Async | N/A                   | Limpieza de DB     | Elimina tokens de sesión antiguos para optimizar la base de datos.                           |
| `check_for_long_trips`          | Sync  | N/A                   | Alerta Admin       | Detecta viajes con duración inusual para alertar sobre posibles problemas de seguridad.      |
| `update_currency_rates`         | Async | N/A                   | Tipos de cambio    | Actualiza los valores de conversión de moneda desde una API externa.                         |
| `send_provider_compliance_mail` | Async | `provider_id`         | Email              | Envía advertencias legales a conductores con baja tasa de aceptación o faltas.               |
| `generate_system_backup_log`    | Sync  | N/A                   | Archivo Log        | Crea un resumen del estado de salud del servidor y de los crons ejecutados.                  |

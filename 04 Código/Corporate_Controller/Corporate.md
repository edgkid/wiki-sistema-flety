# Archivo: `Corporate.js`

## Descripción General
Este controlador gestiona la interacción integral entre la plataforma y los asociados corporativos. Sus responsabilidades incluyen la administración de perfiles empresariales, el control operativo de viajes, la gestión de facturación fiscal y la logística de servicios adicionales como tickets de ferry.

---

## Funciones del Controlador

### Gestión de Accesos y Cuenta
| Función | Tipo | Entrada | Salida | Descripción |
| :--- | :--- | :--- | :--- | :--- |
| `loginRender` | Sync | `req.session` | Vista HTML | Renderiza la pantalla de inicio de sesión para corporativos. |
| `corporate_login` | Async | `email`, `password` | Redirección | Autentica las credenciales y establece la sesión. |
| `registerRender` | Sync | `req.session` | Vista HTML | Muestra el formulario de registro para nuevas empresas. |
| `corporate_create` | Async | `req.body` | Redirección | Registra una nueva entidad corporativa en el sistema. |
| `check_auth` | Middleware | `req.session` | Next/Redirect | Protege las rutas verificando que exista una sesión activa. |
| `corporate_logout` | Sync | `req.session` | Redirección | Finaliza la sesión actual del asociado. |

### Perfil y Seguridad
| Función | Tipo | Entrada | Salida | Descripción |
| :--- | :--- | :--- | :--- | :--- |
| `corporate_profile` | Async | `session` | Vista HTML | Recupera y muestra la configuración del perfil corporativo. |
| `update_corporate_profile` | Async | `req.body`, `req.files` | Redirección | Actualiza los datos generales y archivos (logos/docs) de la empresa. |
| `corporate_change_password` | Async | `old_psw`, `new_psw` | Redirección | Gestiona el cambio de contraseña desde el panel. |
| `corporate_forgot_password_email` | Async | `email` | Redirección | Envía el enlace con token para recuperación de cuenta. |
| `update_psw` | Async | `id`, `token`, `password` | Redirección | Actualiza la contraseña y anula el token de seguridad usado. |

### Operaciones de Viaje y Seguimiento
| Función | Tipo | Entrada | Salida | Descripción |
| :--- | :--- | :--- | :--- | :--- |
| `corporate_trip_history` | Async | `filters`, `page` | Vista HTML | Lista el historial completo de viajes realizados. |
| `corporate_trip_map` | Async | `trip_id` | Vista HTML | Muestra de forma gráfica el recorrido realizado en un viaje. |
| `corporate_track_trip` | Async | `trip_id` | Vista HTML | Interfaz de rastreo en tiempo real para viajes activos. |
| `corporate_request_list` | Async | `session` | Vista HTML | Muestra solicitudes de viaje que aún no han sido asignadas. |
| `corporate_schedule_trip_list` | Async | `session` | Vista HTML | Lista los viajes agendados para fechas futuras. |
| `corporate_cancel_trip` | Async | `trip_id` | JSON | Cancela una solicitud de viaje inmediata activa. |

### Finanzas y Billetera
| Función | Tipo | Entrada | Salida | Descripción |
| :--- | :--- | :--- | :--- | :--- |
| `corporate_invoice` | Async | `trip_id` | Vista HTML | Genera el desglose financiero detallado de un servicio. |
| `corporate_add_card` | Async | `payment_token` | JSON | Vincula un nuevo método de pago mediante pasarela segura. |
| `add_wallet_amount` | Async | `amount`, `card_id` | JSON | Recarga el saldo de la billetera corporativa. |
| `corporate_statement` | Async | `month`, `year` | Vista HTML | Genera el estado de cuenta mensual consolidado. |

### Exportación de Datos (.xlsx / .csv)
| Recurso | Excel | CSV | Descripción |
| :--- | :--- | :--- | :--- |
| **Historial Viajes** | `_export_excel` | `_export_csv` | Reporte de servicios finalizados. |
| **Billetera** | `_export_excel` | `_export_csv` | Histórico de movimientos financieros. |
| **Solicitudes** | `_export_excel` | `_export_csv` | Reporte de demanda pendiente. |
| **Reviews** | `_export_excel` | `_export_csv` | Historial de calificaciones de proveedores. |

### Logística de Tickets

| Función | Tipo | Entrada | Salida | Descripción |
| :--- | :--- | :--- | :--- | :--- |
| `corporate_ferry_tickets` | Async | `filters` | Vista HTML | Lista el inventario de tickets de ferry de la empresa. |
| `create_ferry_ticket` | Async | `req.body` | JSON | Procesa la compra masiva de tickets prepagados. |
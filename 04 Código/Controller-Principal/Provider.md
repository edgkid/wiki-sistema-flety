# Archivo: `Provider.js`

## Descripción General
Este controlador permite la gestión integral de los proveedores (conductores), facilitando el listado de viajes realizados y la generación de reportes de ingresos, métricas de desempeño y facturación en tiempo real.

---

## Funciones del Controlador

| Función | Tipo | Entrada | Salida | Descripción |
| :--- | :--- | :--- | :--- | :--- |
| `get_provider_daily_earning` | Async | `provider_id`, `date` | JSON con totales diarios | Calcula el resumen financiero (ganancias netas) de un día específico. |
| `get_provider_weekly_earning` | Async | `provider_id`, `start_date` | JSON reporte semanal | Genera un desglose de ingresos de los 7 días de la semana. |
| `get_provider_earning_detail` | Async | `provider_id`, `trip_id` | Detalle de factura | Retorna el desglose financiero exacto que recibió el proveedor por un viaje único. |
| `get_daily_analytic` | Async | `provider_id`, `date` | Stats de actividad | Obtiene métricas: tiempo en línea, viajes rechazados, cancelados y aceptados. |
| `get_weekly_analytic` | Async | `provider_id`, `week_range` | Resumen analítico | Agrega las estadísticas diarias para mostrar el desempeño global de la semana. |
| `provider_earning_to_wallet` | Async | `provider_id`, `amount` | Nuevo saldo Wallet | Transfiere las ganancias acumuladas al saldo de la billetera virtual del proveedor. |
| `get_earning_history` | Async | `provider_id`, `page` | Lista paginada | Historial de ganancias pasadas para consulta del conductor. |
| `update_earning_status` | Sync | `trip_id`, `status` | Éxito/Error | Marca una transacción de ganancia como "Pagada" o "Pendiente". |
| `calculate_provider_profit` | Sync | `base_fare`, `distance` | Monto neto | Implementación para determinar cuánto gana el proveedor según el tarifario de la ciudad. |
| `get_referral_earning` | Async | `provider_id` | Total referidos | Calcula las ganancias obtenidas por invitar a otros conductores a la plataforma. |
| `check_provider_debt` | Async | `provider_id` | Balance de deuda | Determina si el proveedor le debe dinero a la plataforma (por cobros en efectivo). |
| `get_provider_invoice` | Async | `trip_id` | PDF/Data Recibo | Genera el comprobante de pago digital para el proveedor. |
| `set_provider_tax_info` | Async | `provider_id`, `tax_id` | Éxito | Registra información fiscal necesaria para la retención de impuestos. |
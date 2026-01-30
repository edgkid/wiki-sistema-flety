# Archivo: `admin_partner_weekly_earning.js`

## Descripción General
Este controlador está diseñado para el panel administrativo y permite supervisar y gestionar la liquidación de las ganancias acumuladas por los **Socios (Partners)**. Facilita la auditoría de ingresos y la preparación de los archivos necesarios para las transferencias bancarias masivas.

---

## Funciones del Controlador

| Función | Tipo | Entrada | Salida | Descripción |
| :--- | :--- | :--- | :--- | :--- |
| `admin_partner_weekly_earning` | Async | `req.body` (filtros) | Vista HTML | Recupera el listado de todos los socios y calcula sus ganancias totales, comisiones y montos netos a pagar en un rango de fechas específico. |
| `admin_partner_weekly_earning_export_excel` | Async | `req.body` (filtros) | Archivo Excel | Genera y descarga un reporte profesional en formato `.xlsx` con el desglose detallado de ingresos de los socios. |
| `admin_partner_weekly_earning_export_csv` | Async | `req.body` (filtros) | Archivo CSV | Genera y descarga un reporte en formato `.csv` compatible con sistemas de gestión de pagos de terceros. |
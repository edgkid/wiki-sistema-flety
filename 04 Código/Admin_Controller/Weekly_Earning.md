
# Archivo: `weekly_earning.js`

## Descripción General
Este controlador es el encargado de gestionar el ciclo de vida de los pagos semanales. 

---

## Funciones del Controlador

| Función                             | Tipo  | Entrada                 | Salida     | Descripción                                                                                                                     |
| :---------------------------------- | :---- | :---------------------- | :--------- | :------------------------------------------------------------------------------------------------------------------------------ |
| `get_weekly_earning`                | Async | `req.body` (ID, fechas) | JSON       | Calcula las ganancias de un proveedor o socio en un rango de fechas específico, desglosando impuestos, comisiones y total neto. |
| `provider_weekly_earning`           | Async | `req.session`           | Vista HTML | Renderiza el panel de visualización de ganancias semanales para el perfil del proveedor.                                        |
| `partner_weekly_earning`            | Async | `req.session`           | Vista HTML | Renderiza el panel de control de ganancias para los socios (partners).                                                          |
| `admin_weekly_earning`              | Async | `req.body` (filtros)    | Vista HTML | Interfaz administrativa para supervisar y auditar las ganancias semanales de todos los proveedores.                             |
| `admin_weekly_earning_export_excel` | Async | `filters`               | Excel      | Exporta el reporte masivo de ganancias semanales en formato .xlsx para contabilidad.                                            |
| `admin_weekly_earning_export_csv`   | Async | `filters`               | CSV        | Genera un reporte ligero descargable con los detalles de los pagos semanales.                                                   |
| `admin_paid_weekly_earning`         | Async | `req.body` (ID de pago) | JSON       | Cambia el estado de una liquidación semanal a "Pagado" tras la verificación administrativa.                                     |
| `statement_weekly_earning`          | Async | `trip_id`               | Vista HTML | Genera el estado de cuenta (factura digital) detallado de un viaje específico.                                                  |
| `weekly_statement_export_excel`     | Async | `req.body`              | Excel      | Exporta el desglose detallado de ganancias de un periodo completo a Excel.                                                      |
| `weekly_statement_export_csv`       | Async | `req.body`              | CSV        | Exporta el desglose detallado de ganancias de un periodo completo a CSV.                                                        |
| `pay_weekly_earning`                | Async | `req.body`              | JSON       | Ejecuta la instrucción de transferencia real de fondos hacia la cuenta bancaria registrada del proveedor.                       |

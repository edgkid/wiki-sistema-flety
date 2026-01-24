# Archivo: `provider_earning.js`

## Descripción General
Este controlador se especializa en el procesamiento y la entrega de información detallada sobre los ingresos devengados por los proveedores. Su objetivo es proporcionar transparencia financiera mediante desgloses temporales de las ganancias.

---

## Funciones del Controlador

| Función | Tipo | Entrada (req.body) | Salida | Descripción |
| :--- | :--- | :--- | :--- | :--- |
| `get_provider_daily_earning_detail` | Async | `provider_id`, `token`, `date` | JSON con el desglose de ingresos del día | Obtiene el resumen financiero detallado de un día específico, incluyendo tarifas base, extras y descuentos. |
| `get_provider_weekly_earning` | Async | `provider_id`, `token`, `start_date` | JSON con el resumen de la semana | Agrega y totaliza los datos de ingresos de una semana completa (7 días) para la visualización del proveedor. |
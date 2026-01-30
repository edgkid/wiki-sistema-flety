# Archivo: `Provider_Earning.js` (Panel Administrativo)

## Descripción General
Este controlador gestiona la visualización de ganancias de los proveedores, proporciona un desglose de la información de facturación de los conductores. 

---

## Funciones del Controlador

| Función                         | Tipo  | Entrada                 | Salida        | Descripción                                                   |
| :------------------------------ | :---- | :---------------------- | :------------ | :------------------------------------------------------------ |
| `provider_earning`              | Async | `req.body` (filtros)    | Vista HTML    | Recupera el listado general de ganancias,                     |
| `provider_earning_export_excel` | Async | `req.body` (filtros)    | Archivo Excel | Exporta el reporte completo de ganancias acumuladas a `.xlsx` |
| `statement_provider_earning`    | Async | `req.body.id` (Trip ID) | Vista HTML    |  Genera el recibo detallado de un viaje.                      |
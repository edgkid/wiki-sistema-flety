# Archivo: `Provider_Weekly_Earning.js`

## Descripción General
Este controlador permite a los conductores consultar sus ingresos agrupados por semanas. 

---

## Funciones del Controlador

| Función                                | Tipo  | Entrada                         | Salida        | Descripción                                                                                                   |
| :------------------------------------- | :---- | :------------------------------ | :------------ | :------------------------------------------------------------------------------------------------------------ |
| `provider_weekly_earning`              | Async | `req.session.provider`, filtros | Vista HTML    | Calcula y lista las ganancias semanales del proveedor.                                                        |
| `provider_weekly_earning_export_excel` | Async | `req.body` (filtros)            | Archivo Excel | Procesa los datos de la consulta semanal y genera un documento `.xlsx` detallado con el historial de ingresos |
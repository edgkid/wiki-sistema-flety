
# Archivo: `Daily_Earning.js`

## Descripción General
Este controlador gestiona las ganancias diarias de los proveedores, permitiendo a los administradores supervisar el rendimiento en tiempo real, desglosar los ingresos por ciudad y país, y generar estados de cuenta específicos por día. 

---

## Funciones del Controlador

### Gestión de Ganancias y Reportes
| Función                      | Tipo  | Entrada                      | Salida        | Descripción                                                            |
| :--------------------------- | :---- | :--------------------------- | :------------ | :--------------------------------------------------------------------- |
| `daily_earning`              | Async | `req.body` (filtros, fechas) | Vista HTML    | Recupera y lista las ganancias diarias de los proveedores              |
| `daily_earning_export_excel` | Async | `req.body` (filtros)         | Archivo Excel | Genera un reporte detallado en formato `.xlsx` de los ingresos diarios |

### Liquidación 

| Función                           | Tipo  | Entrada                 | Salida     | Descripción                                                       |
| :-------------------------------- | :---- | :---------------------- | :--------- | :---------------------------------------------------------------- |
| `statement_provider_dailyearning` | Async | `ID proveedor`, `fecha` | Vista HTML | Genera un estado de cuenta detallado para un proveedor específico |

### Utilidades 

| Función | Tipo | Entrada | Salida | Descripción |
| :--- | :--- | :--- | :--- | :--- |
| `get_city_list` | Async | `req.body.country` | JSON | Función auxiliar que retorna las ciudades vinculadas a un país para filtrar las métricas de ganancias por región. |
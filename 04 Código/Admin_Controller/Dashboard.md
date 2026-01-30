# Archivo: `Dashboard.js`

## Descripción General
Este controlador lleva la gestión del dashboard de la plataforma, recopila, procesa y presenta métricas  de todas las entidades del sistema (Usuarios, Proveedores, Socios, Empresas y Viajes). 

---

## Funciones del Controlador

### Analítica y Estadísticas Globales
| Función | Tipo | Entrada | Salida | Descripción |
| :--- | :--- | :--- | :--- | :--- |
| `statistics` | Async | `session`, `selected_country` | Vista HTML | Genera el Dashboard principal. Calcula contadores totales de usuarios, proveedores activos, viajes completados y montos facturados, segmentando por países. |

### Control de Calidad y Desasignaciones
| Función                           | Tipo  | Entrada              | Salida        | Descripción                                                                                                          |
| :-------------------------------- | :---- | :------------------- | :------------ | :------------------------------------------------------------------------------------------------------------------- |
| `get_unassigned_reasons`          | Async | `req.body` (filtros) | Vista HTML    | Consulta y agrupa los viajes que fueron rechazados o desasignados manualmente, detallando el motivo y el responsable |
| `export_unassigned_reasons_excel` | Async | `req.body` (filtros) | Archivo Excel | Genera el reporte de viajes desasignados (`.xlsx`), incluyendo el historial técnico y los responsables implicados.   |

### Funciones de Soporte Interno 

| Función                  | Tipo    | Entrada              | Salida              | Descripción                                                                      |
| :----------------------- | :------ | :------------------- | :------------------ | :------------------------------------------------------------------------------- |
| `getAdminUnassignData`   | Interna | Model (Trip/History) | Array (Aggregation) | Ejecuta la lógica de agregación en MongoDB para extraer datos de desasignación   |
| `getPartnerUnassignData` | Interna | Model (Trip/History) | Array (Aggregation) | Ejecuta la lógica de agregación para la analítica de desasignaciones realizadas  |
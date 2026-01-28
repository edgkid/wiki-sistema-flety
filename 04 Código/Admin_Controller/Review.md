# Archivo: `Review.js`

## Descripción General
Este controlador gestiona las reseñas y calificaciones intercambiadas entre usuarios y conductores.

---

## Funciones del Controlador

###  Reseñas y Calificaciones
| Función                 | Tipo  | Entrada                 | Salida        | Descripción                                                                                                 |
| :---------------------- | :---- | :---------------------- | :------------ | :---------------------------------------------------------------------------------------------------------- |
| `review`                | Async | `req.body` (filtros)    | Vista HTML    | Recupera y lista todas las reseñas del sistema.                                                             |
| `review_detail`         | Sync  | `req.body.id` (Trip ID) | Vista HTML    | Muestra la información de un viaje específico; la calificación que el usuario dio al conductor y viceversa. |
| `generate_review_excel` | Sync  | `req.body` (filtros)    | Archivo Excel | Procesa las reseñas filtradas y genera un documento `.xlsx`                                                 |

### Análisis de Cancelaciones
| Función                             | Tipo  | Entrada              | Salida        | Descripción                                                                    |
| :---------------------------------- | :---- | :------------------- | :------------ | :----------------------------------------------------------------------------- |
| `cancellation_reason`               | Async | `req.body` (filtros) | Vista HTML    | Lista los viajes cancelados, detallando quién canceló, y el motivo registrado. |
| `generate_cancelation_reason_excel` | Sync  | `req.body` (filtros) | Archivo Excel | Exporta un reporte detallado en Excel sobre las cancelaciones                  |
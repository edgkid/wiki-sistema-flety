# Archivo: `Promo_code.js`

## Descripción General
Este controlador gestiona el ciclo de vida de los Códigos Promocionales. Permite a crear incentivos para los usuarios, definiendo reglas como: fechas de validez, límites de uso por usuario, regiones específicas (países/ciudades) y el tipo de beneficio (monto fijo o porcentaje). 

---

## Funciones del Controlador

### Gestión de Campañas y Vistas
| Función                | Tipo  | Entrada                       | Salida      | Descripción                                                                           |
| :--------------------- | :---- | :---------------------------- | :---------- | :------------------------------------------------------------------------------------ |
| `promotions`           | Async | `req.session.userid`, filtros | Vista HTML  | Lista todos los códigos promocionales, permitiendo filtrar por nombre, país y estado. |
| `add_promocode_form`   | Async | N/A                           | Vista HTML  | Carga el formulario de creación con la lista de países y servicios activos.           |
| `add_promocode_detail` | Async | `req.body` (datos promo)      | JSON        | Registra el código  y guarda las reglas de descuento y límites.                       |
| `edit_promocode`       | Async | `req.body.id`                 | Vista HTML  | Recupera la configuración de una promoción para su modificación                       |
| `update_promocode`     | Async | `req.body`                    | Redirección | Actualiza parámetros como fechas de expiración, valor o visibilidad.                  |

### Control Operativo y Validación
| Función                 | Tipo  | Entrada                  | Salida      | Descripción                                                                         |
| :---------------------- | :---- | :----------------------- | :---------- | :---------------------------------------------------------------------------------- |
| `act`                   | Async | `id`, `state`            | Redirección | Activa o desactiva un código                                                        |
| `check_valid_promocode` | Async | `promocode`, `countryid` | JSON        | Valida si un código ya existe en un país determinado para evitar duplicidad.        |
| `promo_code_uses`       | Async | `promo_id`               | Vista HTML  | Muestra el historial de uso: qué usuarios lo aplicaron y en qué viajes específicos. |

### Reportes y Analítica
| Función | Tipo | Entrada | Salida | Descripción |
| :--- | :--- | :--- | :--- | :--- |
| `export_excel` | Async | `req.body` (filtros) | Archivo Excel | Genera un reporte detallado en `.xlsx` sobre el rendimiento de las promociones. |
| `export_csv` | Async | `req.body` (filtros) | Archivo CSV | Genera un reporte descargable en `.csv` con la lista de códigos y sus estados. |
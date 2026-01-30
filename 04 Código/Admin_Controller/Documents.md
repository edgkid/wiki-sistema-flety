# Archivo: `Documents.js`

## Descripción General
Este controlador para la gestión de documentos de usuarios en la plataforma. Permite a los administradores definir qué documentos son obligatorios según el país y el tipo de entidad (Usuario, Proveedor o Vehículo). Gestiona  fechas de vencimiento, códigos únicos de identificación y la visibilidad de los documentos.

---

## Funciones del Controlador

### Configuración y Gestión Administrativa
| Función | Tipo | Entrada | Salida | Descripción |
| :--- | :--- | :--- | :--- | :--- |
| `list` | Async | `req.session.admin` | Vista HTML | Recupera y muestra la lista maestra de documentos configurados, permitiendo filtrar por país y tipo de entidad. |
| `add_document_form` | Render | N/A | Vista HTML | Muestra el formulario administrativo para crear un nuevo requisito documental (ej. Licencia, RIF, Seguro). |
| `add_document_detail` | Async | `req.body` | Redirección | Registra el documento y lo asigna automáticamente a todos los perfiles existentes en el país seleccionado. |
| `edit_document` | Async | `req.body.id` | Vista HTML | Carga la configuración de un documento específico para modificar su obligatoriedad o parámetros. |
| `update_document` | Async | `req.body` | Redirección | Actualiza los datos y propaga los cambios a todos los registros vinculados en las colecciones de la base de datos. |

### Validación y Reportes
| Función                    | Tipo  | Entrada              | Salida        | Descripción                                                                                                 |
| :------------------------- | :---- | :------------------- | :------------ | :---------------------------------------------------------------------------------------------------------- |
| `find_document_by_country` | Async | `country`, `title`   | JSON          | API interna que comprueba si un documento ya existe en un país para evitar duplicados.                      |
| `export_excel`             | Async | `req.body` (filtros) | Archivo Excel | Genera un reporte en formato `.xlsx` con la lista de documentos registrados y sus configuraciones técnicas. |
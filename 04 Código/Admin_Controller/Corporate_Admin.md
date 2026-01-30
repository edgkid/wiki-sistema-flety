# Archivo: `Corporate.js` (Panel Administrativo)

## Descripción General
Este controlador gestiona  las cuentas corporativas, permite al administrador del sistema listar todas las empresas registradas, aprobar o suspender sus cuentas, gestionar sus documentos y eliminar cuentas. 

---

## Funciones del Controlador

### Gestión de Cuentas y Validación
| Función | Tipo | Entrada | Salida | Descripción |
| :--- | :--- | :--- | :--- | :--- |
| `list` | Async | `req.session.userid` | Vista HTML | Recupera y lista todas las empresas registradas en la plataforma para su supervisión. |
| `edit` | Async | `req.body.id` | Vista HTML | Carga los datos de una empresa específica y la lista de países para permitir su edición técnica. |
| `update` | Async | `req.body`, `req.files` | Redirección | Procesa la actualización de los datos maestros de la empresa y sus archivos adjuntos. |
| `approve_decline_corporate` | Async | `id`, `is_approved` | JSON | Permite al administrador activar o desactivar una cuenta corporativa para operar en la App. |
| `delete_corporate` | Async | `req.body.id` | Redirección | Elimina de forma definitiva la cuenta corporativa del sistema. |

### Finanzas y Documentación
| Función | Tipo | Entrada | Salida | Descripción |
| :--- | :--- | :--- | :--- | :--- |
| `add_corporate_wallet_amount` | Async | `req.body` (monto) | JSON | Permite al administrador realizar ajustes manuales o recargas directas al saldo de la billetera empresarial. |
| `admin_delete_corporate_document` | Async | `id`, `type` | Redirección | Elimina archivos específicos del servidor (como documentos legales vencidos) y limpia la referencia en el perfil. |

### Reportes y Exportación
| Función | Tipo | Entrada | Salida | Descripción |
| :--- | :--- | :--- | :--- | :--- |
| `export_excel` | Async | `req.body` (filtros) | Archivo Excel | Genera un reporte descargable en formato `.xlsx` con el censo de empresas. |
| `export_csv` | Async | `req.body` (filtros) | Archivo CSV | Genera un reporte descargable en formato `.csv` con la información administrativa. |
# Archivo: `Bank_Detail.js`

## Descripción General
Este controlador gestiona el ciclo de vida de la información bancaria dentro de la plataforma. Su función es almacenar, consultar y actualizar los datos de cuentas bancarias de los proveedores y socios, brindando el soporte necesario para procesar los medios de pago y liquidaciones.

---

## Funciones del Controlador

### Consultas de Perfil (Vistas)
| Función | Tipo | Entrada | Salida | Descripción |
| :--- | :--- | :--- | :--- | :--- |
| `partner_bank_detail` | Async | `req.session.partner` | Vista HTML | Busca y muestra los detalles bancarios vinculados a la cuenta del Socio. |
| `partner_provider_bank_detail` | Async | `req.body.id` | Vista HTML | Permite a un Socio visualizar o editar la información bancaria de un proveedor perteneciente a su flota. |
| `provider_bank_detail` | Async | `req.session.provider` | Vista HTML | Recupera y muestra la información bancaria del Proveedor independiente para su gestión personal. |

### Consultas Administrativas
| Función | Tipo | Entrada | Salida | Descripción |
| :--- | :--- | :--- | :--- | :--- |
| `admin_partner_bank_detail` | Async | `req.body.id` | Vista HTML | Permite al administrador del sistema auditar los datos bancarios de los socios registrados. |
| `admin_provider_bank_detail` | Async | `req.body.id` | Vista HTML | Facilita al administrador la consulta de los datos bancarios de cualquier proveedor en la plataforma. |

### Operaciones CRUD y API
| Función | Tipo | Entrada | Salida | Descripción |
| :--- | :--- | :--- | :--- | :--- |
| `add_bank_details` | Async | `req.body` (datos banco) | Redirección | Crea un nuevo registro de cuenta bancaria para el proveedor o socio según corresponda. |
| `update_bank_detail` | Async | `req.body` (datos banco) | Redirección | Actualiza la información de un registro bancario ya existente. |
| `delete_bank_detail` | Async | `req.body.id` | JSON | Elimina de forma permanente el registro bancario especificado de la base de datos. |
| `get_bank_detail` | Async | `req.body.id` | JSON | Interfaz de API que retorna los datos bancarios de un usuario en formato JSON para procesos externos. |
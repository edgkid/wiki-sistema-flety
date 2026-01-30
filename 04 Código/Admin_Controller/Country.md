# Archivo: `Country.js`

## Descripción General
Este controlador permite  gestionar los países donde la plataforma opera. Define parámetros  como el símbolo de la moneda, el código telefónico y la configuración de impuestos. 

---

## Funciones del Controlador

### Gestión Administrativa (Vistas)
| Función | Tipo | Entrada | Salida | Descripción |
| :--- | :--- | :--- | :--- | :--- |
| `country` | Async | `req.session.userid` | Vista HTML | Recupera y muestra la lista completa de países registrados en el sistema. |
| `add_country_form` | Async | N/A | Vista HTML | Renderiza el formulario para registrar un nuevo país en la plataforma. |
| `edit_country` | Async | `req.body.id` | Vista HTML | Carga la configuración específica de un país para permitir la modificación de sus parámetros operativos. |

### Operaciones de Datos (Escritura)
| Función | Tipo | Entrada | Salida | Descripción |
| :--- | :--- | :--- | :--- | :--- |
| `add_country_detail` | Async | `req.body` | Redirección | Crea un nuevo país validando que la configuración inicial sea correcta. |
| `update_country_detail` | Async | `req.body` | Redirección | Actualiza los datos maestros del país (moneda, formato de unidad, impuestos). |
| `delete_country` | Async | `req.body.id` | JSON | Elimina un país del sistema siempre y cuando no tenga ciudades o servicios vinculados. |

### Servicios 

| Función | Tipo | Entrada | Salida | Descripción |
| :--- | :--- | :--- | :--- | :--- |
| `fetch_country_list` | Async | N/A | JSON | Retorna un listado de todos los países marcados como activos. |
| `get_country_data` | Async | `country_id` | JSON | Retorna el detalle técnico de un país específico (moneda, código de teléfono, etc.). |
| `check_country_exists` | Async | `country_name` | JSON | Valida en tiempo real si un país ya está registrado para evitar duplicados. |
| `get_country_timezone` | Async | `country_id` | JSON | Obtiene la lista de zonas horarias soportadas por el país seleccionado. |
| `change_country_visibility` | Async | `id`, `is_visible` | JSON | Activa o desactiva la visibilidad de un país en las aplicaciones móviles. |
| `get_country_list` | Async | N/A | JSON | Función optimizada para retornar solo nombres e IDs para selectores rápidos. |

### Programa de Referidos
| Función | Tipo | Entrada | Salida | Descripción |
| :--- | :--- | :--- | :--- | :--- |
| `update_referral_details` | Async | `req.body` | JSON | Configura los montos de bonificación por referidos para usuarios y proveedores en ese país. |
| `get_referral_details` | Async | `country_id` | JSON | Consulta la configuración vigente de los programas de incentivos por referidos. |
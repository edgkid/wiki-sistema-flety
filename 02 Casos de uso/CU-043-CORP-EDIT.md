## Caso de Uso: CU-043-CORP-EDIT - Dashboard de usuarios

Este caso de uso describe el proceso para modificar la información básica, datos de contacto y las reglas de negocio específicas (precios, beneficios, API) de una entidad corporativa registrada en la plataforma.

### 📋 Información General

| Sección | Descripción |
| :--- | :--- |
| **ID** | CU-043-CORP-EDIT |
| **Caso de Uso** | Dashboard de usuarios |
| **Actor Principal** | Usuario |
| **Actor Secundario** | Software |
| **Objetivo** | Permite modificar la información básica, de contacto y las reglas de negocio específicas (precios, beneficios, API) de una entidad corporativa en la plataforma. |
| **Prioridad** | Alta |

---

### 🛠️ Precondiciones del Sistema
* El usuario inició sesión de forma exitosa (**CU-001-ADM / CU-001-CLI**).
* El usuario cuenta con el rol y los permisos pertinentes.
* El usuario hizo clic en la opción editar detalles desde **CU-042-CORP-DASH** del registro de usuario corporativo mostrado.

---

### 🔄 Flujo del Sistema

| Actor Principal (Usuario) | Actor Secundario (Sistema) |
| :--- | :--- |
| | 1) El sistema recupera y muestra la información actual: nombre, email, país, teléfono y el estado de los interruptores de configuración. |
| 2) El administrador realiza los cambios necesarios (ej. actualizar el teléfono o activar/desactivar beneficios). | 3) El sistema realiza las validaciones pertinentes. |
| 4) El administrador guarda los cambios. | 5) Se deja persistencia de los cambios realizados. |
| | 6) El sistema redirige al caso de uso **CU-042-CORP-DASH**. |
| **Fin** | |

---

### 🔀 Flujo Alternativo del Sistema

| Escenario | Reacción del Sistema |
| :--- | :--- |
| El administrador cambia el email a uno que ya existe en otro registro. | El sistema arroja una excepción y no guarda los cambios. |
| Ocurre un fallo técnico durante el guardado. | El sistema informa que los cambios no fueron guardados y mantiene los datos en el formulario para reintento. |

---

### ✅ Post-Condiciones

| Escenario de Éxito | Escenario de Fallo |
| :--- | :--- |
| Los cambios realizados en los campos (Nombre, Email, País, Teléfono) se han impactado en la base de datos de manera permanente. | El sistema garantiza la integridad de los datos; el administrador permanece en la vista de edición con los datos que intentó modificar. |
| El sistema muestra un mensaje de confirmación visual al administrador. | |

---

### 🔗 Casos de Uso Relacionados
* [CU-042-CORP-DASH](02%20Casos%20de%20uso/CU-042-CORP-DASH.md)
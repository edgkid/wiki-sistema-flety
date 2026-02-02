## Caso de Uso: CU-025-CON-HISR - Historial de referencias del Conductor

Este caso de uso describe la funcionalidad que permite al administrador consultar el listado de referencias y reseñas asociadas a un conductor específico, facilitando la verificación de su reputación y el seguimiento de las valoraciones recibidas por parte de los usuarios.

### 📋 Información General

| Sección | Descripción |
| :--- | :--- |
| **ID** | CU-025-CON-HISR |
| **Caso de Uso** | Historial de referencias del conductor |
| **Actor Principal** | Usuario |
| **Actor Secundario** | Software |
| **Objetivo** | Permite consultar un listado con información de referencias de un conductor; Item nombre, teléfono y fecha de creación. |
| **Prioridad** | Alta |

---

### 🛠️ Precondiciones del Sistema
* El usuario inicia sesión de forma exitosa (**CU-001-ADM / CU-001-CLI**).
* El usuario cuenta con el rol y los permisos pertinentes.
* El usuario hizo clic en editar desde **CU-023-CON-VEHI**.
* Debe existir información de reseñas.

---

### 🔄 Flujo del Sistema

| Actor Principal (Usuario) | Actor Secundario (Sistema) |
| :--- | :--- |
| | 1) El sistema carga y muestra una tabla con los registros de reseñas de usuarios: item, nombre, teléfono y fecha de creación. |
| 2) Puede consultar la información mostrada. | |
| 3) El usuario puede filtrar los datos mostrados. | |
| **Fin** | |

---

### 🔀 Flujo Alternativo

| Actor Principal (Usuario) | Actor Secundario (Sistema) |
| :--- | :--- |
| 1) El usuario puede interactuar con otros módulos del sistema, aquellos que su rol le permita. | |
| **Fin** | |

---

### ✅ Post-Condiciones

| Escenario | Resultado Esperado |
| :--- | :--- |
| **Consulta Exitosa** | El administrador visualiza correctamente el listado de referencias y datos de contacto asociados a las reseñas. |
| **Filtro Aplicado** | El sistema procesa la búsqueda y muestra los resultados que coinciden con los criterios de filtrado. |

---

### 🔗 Casos de Uso Relacionados
* [Conductor (CU-021)](02%20Casos%20de%20uso/CU-021-Conductor.md)
* [CU-027-CON-APRO](02%20Casos%20de%20uso/CU-027-CON-APRO.md)
* [CU-028-CON-NPRO](02%20Casos%20de%20uso/CU-028-CON-NPRO.md)
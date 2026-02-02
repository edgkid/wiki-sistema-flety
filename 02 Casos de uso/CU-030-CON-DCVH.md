## Caso de Uso: CU-030-CON-DCVH - Documentos de vehículo

Este caso de uso describe la funcionalidad que permite al administrador consultar y gestionar el expediente digital de cada vehículo asociado a un conductor. Centraliza la revisión de documentos legales, fechas de vencimiento y códigos de identificación únicos para garantizar el cumplimiento normativo de la flota.

### 📋 Información General

| Sección | Descripción |
| :--- | :--- |
| **ID** | CU-030-CON-DCVH |
| **Caso de Uso** | Listado de documentos del vehículo |
| **Actor Principal** | Usuario |
| **Actor Secundario** | Software |
| **Objetivo** | Permite consultar y gestionar la información de la documentación de los vehículos asociados a un conductor. |
| **Prioridad** | Alta |

---

### 🛠️ Precondiciones del Sistema
* El usuario inicia sesión de forma exitosa (**CU-001-ADM / CU-001-CLI**).
* El usuario cuenta con el rol y los permisos pertinentes.
* El usuario hizo clic en editar desde **CU-023-CON-VEHI**.
* Existen vehículos asociados al conductor.

---

### 🔄 Flujo del Sistema

| Actor Principal (Usuario) | Actor Secundario (Sistema) |
| :--- | :--- |
| | 1) El sistema carga información de los documentos pertenecientes a cada uno de los vehículos asociados a cada conductor; nombre, fecha de vencimiento, código único y documento. |
| 2) Puede consultar la información mostrada. | |
| **Fin** | |

---

### 🔀 Flujo Alternativo

| Actor Principal (Usuario) | Actor Secundario (Sistema) |
| :--- | :--- |
| 1) El usuario puede interactuar con otros módulos del sistema, aquellos que su rol le permita. | |

---

### ✅ Post-Condiciones

| Escenario | Resultado Esperado |
| :--- | :--- |
| **Éxito** | El administrador visualiza correctamente el listado de documentos y sus estados de vigencia. |
| **Interacción** | El usuario puede navegar hacia otros módulos permitidos por su perfil. |

---

### 🔗 Casos de Uso Relacionados
* [Conductor (CU-021)](02%20Casos%20de%20uso/CU-021-Conductor.md)
* [CU-027-CON-APRO](02%20Casos%20de%20uso/CU-027-CON-APRO.md)
* [CU-028-CON-NPRO](02%20Casos%20de%20uso/CU-028-CON-NPRO.md)
* [CU-029-CON-EDVH](02%20Casos%20de%20uso/CU-029-CON-EDVH.md)
* [CU-030-CON-DCVH](02%20Casos%20de%20uso/CU-030-CON-DCVH.md)
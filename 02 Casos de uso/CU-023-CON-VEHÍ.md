## Caso de Uso: CU-023-CON-VEHI - Lista de vehículos del conductor

Este caso de uso describe la funcionalidad que permite al administrador visualizar y gestionar los vehículos vinculados a un conductor específico, incluyendo detalles técnicos y el estado de accesibilidad de cada unidad.

### 📋 Información General

| Sección | Descripción |
| :--- | :--- |
| **ID** | CU-023-CON-VEHI |
| **Caso de Uso** | Lista de vehículos del conductor |
| **Actor Principal** | Usuario |
| **Actor Secundario** | Software |
| **Objetivo** | Permite consultar y gestionar la información de los vehículos asociados a un conductor. |
| **Prioridad** | Alta |

---

### 🛠️ Precondiciones del Sistema
* El usuario inicia sesión de forma exitosa (**CU-001-ADM / CU-001-CLI**).
* El usuario cuenta con el rol y los permisos pertinentes.
* El usuario hizo clic en editar desde **CU-021-CON-ENLI**.
* Existen vehículos asociados al conductor.

---

### 🔄 Flujo del Sistema

| Actor Principal (Usuario) | Actor Secundario (Sistema) |
| :--- | :--- |
| | 1) El sistema carga información de los vehículos asociados a cada conductor; nombre, placa, modelo, color, año, Accesibilidad. |
| 2) Puede consultar la información mostrada. | |
| 3) Puede editar la información. | 4) Es redirigido a **CU-029-CON-EDVH**. |
| 5) Puede consultar la información de vehículo. | 6) Es Redirigido a **CU-030-CON-DCVH**. |
| **Fin** | |

---

### 🔀 Flujo Alternativo

| Actor Principal (Usuario) | Actor Secundario (Sistema) |
| :--- | :--- |
| 1) El usuario puede interactuar con otros módulos del sistema, aquellos que su rol le permita. | |
| 2) Regresa a **CU-021-CON-ENLI**. | |

---

### ✅ Post-Condiciones

| Escenario | Resultado Esperado |
| :--- | :--- |
| **Éxito** | Los datos se cargaron correctamente. |
| **Interacción** | El usuario consulta los datos e interactúa con el resto del sistema. |

---

### 🔗 Casos de Uso Relacionados
* [Conductor (CU-021)](02%20Casos%20de%20uso/CU-021-Conductor.md)
* [CU-027-CON-APRO](02%20Casos%20de%20uso/CU-027-CON-APRO.md)
* [CU-028-CON-NPRO](02%20Casos%20de%20uso/CU-028-CON-NPRO.md)
* [CU-029-CON-EDVH](02%20Casos%20de%20uso/CU-029-CON-EDVH.md)
* [CU-030-CON-DCVH](02%20Casos%20de%20uso/CU-030-CON-DCVH.md)
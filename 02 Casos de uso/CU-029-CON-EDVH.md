## Caso de Uso: CU-029-CON-EDVH - Editar Detalles de Vehículo

Este caso de uso describe el proceso mediante el cual un administrador puede modificar las especificaciones técnicas y datos de identificación de los vehículos asociados a un conductor, garantizando que la información de la flota esté actualizada.

### 📋 Información General

| Sección | Descripción |
| :--- | :--- |
| **ID** | CU-029-CON-EDVH |
| **Caso de Uso** | Editar Detalles de Vehículo |
| **Actor Principal** | Usuario |
| **Actor Secundario** | Software |
| **Objetivo** | Permite editar la información de los vehículos asociados a un conductor. |
| **Prioridad** | Alta |

---

### 🛠️ Precondiciones del Sistema
* El usuario inicia sesión de forma exitosa (**CU-001-ADM / CU-001-CLI**).
* El usuario cuenta con el rol y los permisos pertinentes.
* El usuario hizo clic en editar desde **CU-023-CON-VEHI** y/o **CU-034-CAM-DASH**.
* Existen vehículos asociados al conductor.

---

### 🔄 Flujo del Sistema

| Actor Principal (Usuario) | Actor Secundario (Sistema) |
| :--- | :--- |
| | 1) Carga la información del vehículo seleccionado para su posterior edición. |
| | 2) Carga un listado de modelos de vehículos (camiones). |
| 3) Puede editar los siguientes datos: nombre, modelo, placa, etc. | |
| 4) Guarda los cambios. | 5) Actualiza la información en la base de datos. |
| **Fin** | |

---

### 🔀 Flujo Alternativo

| Actor Principal (Usuario) | Actor Secundario (Sistema) |
| :--- | :--- |
| 1) El usuario puede cancelar la operación en cualquier momento. | |
| 2) El usuario puede interactuar con otros módulos del sistema, aquellos que su rol le permita. | |

---

### ✅ Post-Condiciones

| Escenario | Resultado Esperado |
| :--- | :--- |
| **Éxito** | El usuario es redirigido a **CU-034-CAM-DASH**. |
| **Fallo** | Se muestra mensaje de error y el usuario se mantiene en la vista o caso de uso actual. |
| **Interacción** | El usuario puede interactuar con otros módulos del sistema. |

---

### 🔗 Casos de Uso Relacionados
* [CU-023-CON-VEHI](02%20Casos%20de%20uso/CU-023-CON-VEHI.md)
* [CU-034-Camiones](CU-034-Camiones.md)
* [Conductor (CU-021)](02%20Casos%20de%20uso/CU-021-Conductor.md)
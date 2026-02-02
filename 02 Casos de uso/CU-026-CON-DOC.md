## Caso de Uso: CU-026-CON-DOC - Documentos del Conductor

Este caso de uso describe la funcionalidad que permite al administrador consultar y gestionar el expediente digital del conductor, visualizando todos los documentos legales y operativos cargados en la plataforma, junto con sus respectivas vigencias.

### 📋 Información General

| Sección | Descripción |
| :--- | :--- |
| **ID** | CU-026-CON-DOC |
| **Caso de Uso** | Documentos del Conductor |
| **Actor Principal** | Usuario |
| **Actor Secundario** | Software |
| **Objetivo** | Permite consultar un listado con todos los documentos asociados a un conductor. |
| **Prioridad** | Alta |

---

### 🛠️ Precondiciones del Sistema
* El usuario inicia sesión de forma exitosa (**CU-001-ADM / CU-001-CLI**).
* El usuario cuenta con el rol y los permisos pertinentes.
* El usuario hizo clic en Documentos desde **CU-024-CON-HIST** y/o **CU-025-CON-HISR**.
* Debe existir información de reseñas.

---

### 🔄 Flujo del Sistema

| Actor Principal (Usuario) | Actor Secundario (Sistema) |
| :--- | :--- |
| | 1) El sistema carga y muestra una tabla con los registros de todos los documentos asociados al conductor; documento, fecha de vencimiento, código único. |
| 2) Visualiza los documentos registrados. | |
| **Fin** | |

---

### 🔀 Flujo Alternativo

| Actor Principal (Usuario) | Actor Secundario (Sistema) |
| :--- | :--- |
| 1) El usuario puede interactuar con otros módulos del sistema, aquellos que su rol le permita. | |
| 2) Puede editar el documento seleccionado. | 3) Redirige a **CU-033-CON-DOCE**. |
| 4) El usuario puede interactuar con otros módulos del sistema, aquellos que su rol le permita. | |

---

### ✅ Post-Condiciones

| Escenario | Resultado Esperado |
| :--- | :--- |
| **Éxito** | El usuario puede interactuar con otros módulos del sistema, aquellos que su rol le permita. |

---

### 🔗 Casos de Uso Relacionados
* [Conductor (CU-021)](02%20Casos%20de%20uso/CU-021-Conductor.md)
* [CU-027-CON-APRO](02%20Casos%20de%20uso/CU-027-CON-APRO.md)
* [CU-028-CON-NPRO](02%20Casos%20de%20uso/CU-028-CON-NPRO.md)
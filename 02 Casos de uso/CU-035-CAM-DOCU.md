## Caso de Uso: CU-035-CAM-DOCU - Dashboard de camiones

Este caso de uso describe la funcionalidad que permite al usuario visualizar y descargar la documentación técnica y legal del vehículo seleccionado dentro de la flota para su verificación o archivo.

### 📋 Información General

| Sección | Descripción |
| :--- | :--- |
| **ID** | CU-035-CAM-DOCU |
| **Caso de Uso** | Dashboard de camiones |
| **Actor Principal** | Usuario |
| **Actor Secundario** | Software |
| **Objetivo** | Permitir al usuario visualizar y descargar la documentación del vehículo seleccionado dentro de la flota. |
| **Prioridad** | Alta |

---

### 🛠️ Precondiciones del Sistema
* El usuario inicia sesión de forma exitosa (**CU-001-ADM / CU-001-CLI**).
* El usuario cuenta con el rol y los permisos pertinentes.
* Que se haya cargado previamente los documentos del vehículo.

---

### 🔄 Flujo del Sistema

| Actor Principal (Usuario) | Actor Secundario (Sistema) |
| :--- | :--- |
| | 1) El sistema consulta la base de datos y presenta la documentación del vehículo. |
| 2) Puede consultar la información mostrada. | |
| 3) Puede descargar cada documento. | |
| **Fin** | |

---

### 🔀 Flujo Alternativo del Sistema

| Actor Principal (Usuario) | Actor Secundario (Sistema) |
| :--- | :--- |
| 1) Puede interactuar otros módulos del sistema, aquellos que su rol le permitan. | |

---

### ✅ Post-Condiciones

| Escenario de Éxito | Escenario de Fallo |
| :--- | :--- |
| Es creada y presentada la documentación del vehículo. | No existe documentación a mostrar y por tanto el vehículo se encuentra en **CU-034-CAM-DASH**. |

---

### 🔗 Casos de Uso Relacionados
* [Camiones (CU-034)](02%20Casos%20de%20uso/CU-034-Camiones.md)
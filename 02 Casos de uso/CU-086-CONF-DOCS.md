## Caso de Uso: CU-086-CONF-DOCS - Documentos

### 📋 Información General

| Sección | Descripción |
| :--- | :--- |
| **id** | CU-086-CONF-DOCS |
| **Caso de Uso** | Documentos |
| **Actor Principal** | Usuario |
| **Actores Secundarios** | Software |
| **Objetivo** | Permite gestionar; Consultar, editar y crear información de documentación requerida para los diferentes actores (usuarios y camiones) del sistema. |
| **Prioridad** | |

---

### 🛠️ Precondiciones del Sistema
* El usuario inicia sesión de forma exitosa CU-001-ADM / CU-001-CLI.
* El usuario cuenta con el rol y los permisos pertinentes.

---

### 🔄 Flujo del Sistema

| Actor principal (usuario) | Actor Secundario (sistema) |
| :--- | :--- |
| | El sistema carga un listado con todos los item (documentos) que serán solicitados por usuarios, conductores y camiones. |
| | El sistema presenta en el listado la siguiente información: Nombre, país y tipo. |
| El usuario visualiza la información de los documentos creados para solicitar en el sistema. | |
| El usuario puede aplicar filtros sobre la información mostrada. | |
| **Fin** | |

---

### 🔀 Flujo alternativo del sistema

| Acción del Usuario | Reacción del Sistema |
| :--- | :--- |
| El usuario puede agregar un nuevo documento para solicitar en el sistema. | El sistema redirige a **CU-087-CONF-NWDC**. |
| El usuario puede editar la información de un documento que será solicitado en el sistema. | El sistema redirige a **CU-088-CONF-EDDC**. |

---

### ✅ Post Condición del sistema

| Escenario | Resultado |
| :--- | :--- |
| **Éxito** | Cualquier cambio realizado sobre la información mostrada se actualiza inmediatamente. |
| **Fallo** | |

---

### 🔗 CU - Relacionado
* [CU-087-CONF-NWDC](02%20Casos%20de%20uso/CU-087-CONF-NWDC.md)
* [CU-088-CONF-EDDC](02%20Casos%20de%20uso/CU-088-CONF-EDDC.md)
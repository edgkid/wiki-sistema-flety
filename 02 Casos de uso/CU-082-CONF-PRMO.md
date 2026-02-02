## Caso de Uso: CU-082-CONF-PRMO - Códigos Promocionales

### 📋 Información General

| Sección | Descripción |
| :--- | :--- |
| **id** | CU-082-CONF-PRMO |
| **Caso de Uso** | Códigos Promocionales |
| **Actor Principal** | Usuario |
| **Actores Secundarios** | Software |
| **Objetivo** | Permite gestionar los códigos promocionales (creación, edición, activación y eliminación). |
| **Prioridad** | |

---

### 🛠️ Precondiciones del Sistema
* El usuario inicia sesión de forma exitosa CU-001-ADM / CU-001-CLI
* El usuario cuenta con el rol y los permisos pertinentes

---

### 🔄 Flujo del Sistema

| Actor principal (usuario) | Actor Secundario (sistema) |
| :--- | :--- |
| | El sistema presenta un listado con la información de los códigos promocionales existentes, mostrando: código promocional, país, tipo, valor, uso, usuarios usados, estatus y si este expiró o no. |
| El usuario visualiza la información de los códigos promocionales. | |
| El usuario puede aplicar filtros sobre la información mostrada. | |
| El usuario puede activar o inactivar un código promocional. | |
| | El sistema deja persistencia de la acción. |
| | El sistema muestra mensaje con el resultado de la operación. |
| El usuario puede eliminar un código promocional. | |
| | El sistema deja persistencia de la acción. |
| | El sistema muestra mensaje con el resultado de la operación. |
| **Fin** | |

---

### 🔀 Flujo alternativo del sistema

| Acción del Usuario | Reacción del Sistema |
| :--- | :--- |
| El usuario puede crear un nuevo código promocional. | El sistema redirige a **CU-083-CONF-NWPM**. |
| El usuario puede editar un registro de código promocional. | El sistema redirige a **CU-084-CONF-EDPM**. |
| El usuario puede ver el detalle de la información promocional usada. | El sistema redirige a **CU-085-CONF-PMINF**. |
| **Fin** | |

---

### ✅ Post Condición del sistema

| Escenario | Resultado |
| :--- | :--- |
| **Éxito** | Los códigos gestionados quedan disponibles (o inhabilitados) en tiempo real para los usuarios. |
| **Fallo** | |

---

### 🔗 CU - Relacionado
* [CU-083-CONF-NWPM](02%20Casos%20de%20uso/CU-083-CONF-NWPM.md)
* [CU-084-CONF-EDPM](02%20Casos%20de%20uso/CU-084-CONF-EDPM.md)
* [CU-085-CONF-PMINF](02%20Casos%20de%20uso/CU-085-CONF-PMINF.md)
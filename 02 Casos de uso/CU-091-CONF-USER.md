## Caso de Uso: CU-091-CONF-USER - Configuración de usuarios

### 📋 Información General

| Sección | Descripción |
| :--- | :--- |
| **id** | CU-091-CONF-USER |
| **Caso de Uso** | Configuración de usuarios |
| **Actor Principal** | Usuario |
| **Actores Secundarios** | Software |
| **Objetivo** | Permite gestionar los usuarios del sistema; consultar, crear, editar y eliminar un usuario del sistema. |
| **Prioridad** | |

---

### 🛠️ Precondiciones del Sistema
* El usuario inicia sesión de forma exitosa CU-001-ADM / CU-001-CLI.
* El usuario cuenta con el rol y los permisos pertinentes.

---

### 🔄 Flujo del Sistema

| Actor principal (usuario) | Actor Secundario (sistema) |
| :--- | :--- |
| | El sistema muestra un listado con todos los usuarios existentes en el sistema, muestra la siguiente información: usuario, email, tipo y país. |
| El usuario visualiza la información presentada en la lista. | |
| El usuario puede eliminar un usuario del sistema. | |
| | El sistema muestra un mensaje indicado si la eliminación fue exitosa o no. |
| **Fin** | |

---

### 🔀 Flujo alternativo del sistema

| Acción del Usuario | Reacción del Sistema |
| :--- | :--- |
| El usuario puede crear un nuevo usuario. | El sistema redirige a **CU-092-CONF-NWUS**. |
| El usuario puede editar los datos de un usuario. | El sistema redirige a **CU-093-CONF-EDUS**. |

---

### ✅ Post Condición del sistema

| Escenario | Resultado |
| :--- | :--- |
| **Éxito** | Los datos de los usuario y la lista se actualizan inmediatamente. |
| **Fallo** | |

---

### 🔗 CU - Relacionado
* [CU-092-CONF-NWUS](02%20Casos%20de%20uso/CU-092-CONF-NWUS.md)
* [CU-093-CONF-EDUS](02%20Casos%20de%20uso/CU-093-CONF-EDUS.md)
## Caso de Uso: CU-088-CONF-EDDC - Editar documento

### 📋 Información General

| Sección | Descripción |
| :--- | :--- |
| **id** | CU-088-CONF-EDDC |
| **Caso de Uso** | Editar documento |
| **Actor Principal** | Usuario |
| **Actores Secundarios** | Software |
| **Objetivo** | |
| **Prioridad** | |

---

### 🛠️ Precondiciones del Sistema
* El usuario inicia sesión de forma exitosa CU-001-ADM / CU-001-CLI.
* El usuario cuenta con el rol y los permisos pertinentes.
* El usuario hizo clic en editar documento desde **CU-086-CONF-DOCS**.

---

### 🔄 Flujo del Sistema

| Actor principal (usuario) | Actor Secundario (sistema) |
| :--- | :--- |
| | El sistema muestra un formulario con los datos precargados y que son requeridos en el sistema. |
| El usuario actualiza los siguientes datos: país, nombre, tipo, si es opcional y el tipo de documento. | |
| El usuario puede indicar a través de un interruptor lo siguiente: si cuenta con un código único, si contará con fecha de caducidad y si contará con fecha de emisión. | |
| El usuario indica que desea guardar los datos. | |
| | El sistema deja persistencia de los datos. |
| | El sistema redirige a **CU-086-CONF-DOCS**. |
| **Fin** | |

---

### 🔀 Flujo alternativo del sistema
N/A

---

### ✅ Post Condición del sistema

| Escenario | Resultado |
| :--- | :--- |
| **Éxito** | |
| **Fallo** | |

---

### 🔗 CU - Relacionado
* [CU-086-CONF-DOCS](02%20Casos%20de%20uso/CU-086-CONF-DOCS.md)
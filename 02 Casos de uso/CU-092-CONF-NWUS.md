## Caso de Uso: CU-092-CONF-NWUS - Crear usuarios

### 📋 Información General

| Sección | Descripción |
| :--- | :--- |
| **id** | CU-092-CONF-NWUS |
| **Caso de Uso** | Crear usuarios |
| **Actor Principal** | Usuario |
| **Actores Secundarios** | Software |
| **Objetivo** | Permite crear el registro de un nuevo usuario. |
| **Prioridad** | |

---

### 🛠️ Precondiciones del Sistema
* El usuario inicia sesión de forma exitosa CU-001-ADM / CU-001-CLI.
* El usuario cuenta con el rol y los permisos pertinentes.
* El usuario hizo clic en agregar usuario desde **CU-091-CONF-USER**.

---

### 🔄 Flujo del Sistema

| Actor principal (usuario) | Actor Secundario (sistema) |
| :--- | :--- |
| | El sistema presenta un formulario con los datos requeridos de un usuario del sistema. |
| El usuario puede cargar la siguiente información: nombre, tipo, país, email y contraseña. Presiona guardar. | |
| | El sistema deja persistencia de los datos. |
| | El sistema redirige a **CU-091-CONF-USER**. |
| **Fin** | |

---

### 🔀 Flujo alternativo del sistema
N/A

---

### ✅ Post Condición del sistema

| Escenario | Resultado |
| :--- | :--- |
| **Éxito** | Los datos de los usuario y la lista se actualizan inmediatamente. |
| **Fallo** | |

---

### 🔗 CU - Relacionado
* [CU-091-CONF-USER](02%20Casos%20de%20uso/CU-091-CONF-USER.md)
## Caso de Uso: CU-089-CONF-EMAIL - Configurar correo

### 📋 Información General

| Sección | Descripción |
| :--- | :--- |
| **id** | CU-089-CONF-EMAIL |
| **Caso de Uso** | Configurar correo |
| **Actor Principal** | Usuario |
| **Actores Secundarios** | Software |
| **Objetivo** | Permite la configuración del formato de correo electrónico. |
| **Prioridad** | |

---

### 🛠️ Precondiciones del Sistema
* El usuario inicia sesión de forma exitosa CU-001-ADM / CU-001-CLI.
* El usuario cuenta con el rol y los permisos pertinentes.

---

### 🔄 Flujo del Sistema

| Actor principal (usuario) | Actor Secundario (sistema) |
| :--- | :--- |
| | El sistema muestra un formulario para la carga de los datos del formato del correo electrónico. |
| El usuario puede indicar los siguientes datos: Título único del correo electrónico (Asunto), título del cuerpo del correo, información del administrador del correo electrónico y cuerpo del correo. | |
| El usuario guarda los datos de configuración. | |
| | El sistema deja persistencia de la nueva configuración. |
| **Fin** | |

---

### 🔀 Flujo alternativo del sistema
N/A

---

### ✅ Post Condición del sistema

| Escenario | Resultado |
| :--- | :--- |
| **Éxito** | El sistema deja disponibilidad del nuevo formato del correo. |
| **Fallo** | |

---


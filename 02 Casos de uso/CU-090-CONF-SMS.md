## Caso de Uso: CU-090-CONF-SMS - Configurar plantilla de SMS

### 📋 Información General

| Sección | Descripción |
| :--- | :--- |
| **id** | CU-090-CONF-SMS |
| **Caso de Uso** | Configurar plantilla de SMS |
| **Actor Principal** | Usuario |
| **Actores Secundarios** | Software |
| **Objetivo** | Permite la configuración de una plantilla de SMS. |
| **Prioridad** | |

---

### 🛠️ Precondiciones del Sistema
* El usuario inicia sesión de forma exitosa CU-001-ADM / CU-001-CLI.
* El usuario cuenta con el rol y los permisos pertinentes.

---

### 🔄 Flujo del Sistema

| Actor principal (usuario) | Actor Secundario (sistema) |
| :--- | :--- |
| | El sistema presenta un breve formulario que permite definir la plantilla de un SMS. |
| El usuario puede indicar un título único del SMS. | |
| El usuario puede indicar un título de SMS. | |
| | El sistema deja persistencia del mensaje. |
| **Fin** | |

---

### 🔀 Flujo alternativo del sistema
N/A

---

### ✅ Post Condición del sistema

| Escenario | Resultado |
| :--- | :--- |
| **Éxito** | El sistema deja disponibilidad del nuevo formato del SMS. |
| **Fallo** | |

---

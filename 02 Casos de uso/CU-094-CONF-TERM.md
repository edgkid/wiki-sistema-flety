## Caso de Uso: CU-094-CONF-TERM - Configurar políticas y términos

### 📋 Información General

| Sección | Descripción |
| :--- | :--- |
| **id** | CU-094-CONF-TERM |
| **Caso de Uso** | Configurar políticas y términos |
| **Actor Principal** | Usuario |
| **Actores Secundarios** | Software |
| **Objetivo** | Permite crear y actualizar los términos y políticas de la aplicación mediante una plantilla. |
| **Prioridad** | |

---

### 🛠️ Precondiciones del Sistema
* El usuario inicia sesión de forma exitosa CU-001-ADM / CU-001-CLI.
* El usuario cuenta con el rol y los permisos pertinentes.

---

### 🔄 Flujo del Sistema

| Actor principal (usuario) | Actor Secundario (sistema) |
| :--- | :--- |
| | El sistema presenta una plantilla compuesta por cuatro pestañas para la creación y actualización de las políticas y términos de uso. |
| El usuario indica la información de las políticas y términos de uso. | |
| | El sistema mantiene la persistencia. |
| **Fin** | |

---

### 🔀 Flujo alternativo del sistema
N/A

---

### ✅ Post Condición del sistema

| Escenario | Resultado |
| :--- | :--- |
| **Éxito** | Las políticas y términos se actualizan en tiempo real. |
| **Fallo** | |

---


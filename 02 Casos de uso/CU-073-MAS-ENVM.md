## Caso de Uso: CU-073-MAS-ENVM - Enviar notificaciones masivas

### 📋 Información General

| Sección | Descripción |
| :--- | :--- |
| **id** | CU-073-MAS-ENVM |
| **Caso de Uso** | Enviar notificaciones masivas |
| **Actor Principal** | Usuario |
| **Actores Secundarios** | Software |
| **Objetivo** | Permite al usuario enviar mensajes de texto o notificaciones push de manera simultánea a un grupo específico de destinatarios (Usuarios y Conductores) |
| **Prioridad** | |

---

### 🛠️ Precondiciones del Sistema
* El usuario inicia sesión de forma exitosa CU-001-ADM / CU-001-CLI
* El usuario cuenta con el rol y los permisos pertinentes

---

### 🔄 Flujo del Sistema

| Actor principal (usuario) | Actor Secundario (sistema) |
| :--- | :--- |
| | El sistema presenta dos opciones de filtro; 1) grupo de destinatarios (Conductor y usuario), y 2) La región |
| El usuario selecciona grupo de usuario para envío masivo de notificación | |
| El usuario selecciona la región | |
| Indica el mensaje y presiona enviar | |
| | El sistema ejecuta el servicio de envío |
| | Indica el resultado exitoso o fallido del envío de notificación |
| **Fin** | |

---

### 🔀 Flujo alternativo del sistema
* **Si el usuario intenta enviar sin texto**: El sistema debe indicar que no existe notificación a enviar y no permitir el envío de una notificación vacía.

---

### ✅ Post Condición del sistema

| Escenario | Resultado |
| :--- | :--- |
| **Éxito** | Debe quedar un registro histórico de la notificación enviada. Los destinatarios reciben la notificación. |
| **Fallo** | |

---


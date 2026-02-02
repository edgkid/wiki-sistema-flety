## Caso de Uso: CU-076-MAS-EDNT - Editar notificaciones masivas

### 📋 Información General

| Sección | Descripción |
| :--- | :--- |
| **id** | CU-076-MAS-EDNT |
| **Caso de Uso** | Editar notificaciones masivas |
| **Actor Principal** | Usuario |
| **Actores Secundarios** | Software |
| **Objetivo** | Permite al usuario editar y guardar los mensajes de texto o notificaciones push previamente registrados y enviados a los distintos grupos de usuarios en la plataforma |
| **Prioridad** | |

---

### 🛠️ Precondiciones del Sistema
* El usuario inicia sesión de forma exitosa CU-001-ADM / CU-001-CLI
* El usuario cuenta con el rol y los permisos pertinentes
* El usuario seleccione la opción de Enviar notificación desde **CU-074-MAS-INBX**

---

### 🔄 Flujo del Sistema

| Actor principal (usuario) | Actor Secundario (sistema) |
| :--- | :--- |
| | El sistema presenta un formulario con los datos previamente cargados, estructura y parámetros permitidos de la notificación. |
| | El sistema presenta dos opciones de filtro; 1) grupo de destinatarios (Conductor y usuario), y 2) La región. |
| El usuario selecciona grupo de usuario para envío masivo de notificación. | |
| El usuario selecciona la región. | |
| El usuario indica el mensaje y guarda. | |
| | El sistema guarda la notificación creada. |
| | El sistema redirige a **CU-074-MAS-INBX**. |
| **Fin** | |

---

### 🔀 Flujo alternativo del sistema
N/A

---

### ✅ Post Condición del sistema

| Escenario | Resultado |
| :--- | :--- |
| **Éxito** | La nueva notificación aparece como el registro más reciente en la tabla de la vista anterior (**CU-074-MAS-INBX**). |
| **Fallo** | |

---

### 🔗 CU - Relacionado
* [CU-074-MAS-INBX](02%20Casos%20de%20uso/CU-074-MAS-INBX.md)
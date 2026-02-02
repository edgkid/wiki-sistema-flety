## Caso de Uso: CU-074-MAS-INBX - Inbox notificaciones masivas

### 📋 Información General

| Sección | Descripción |
| :--- | :--- |
| **id** | CU-074-MAS-INBX |
| **Caso de Uso** | Inbox notificaciones masivas |
| **Actor Principal** | Usuario |
| **Actores Secundarios** | Software |
| **Objetivo** | Permite visualizar, filtrar y buscar todas las notificaciones masivas que han sido enviadas previamente a través de la plataforma |
| **Prioridad** | |

---

### 🛠️ Precondiciones del Sistema
* El usuario inicia sesión de forma exitosa CU-001-ADM / CU-001-CLI
* El usuario cuenta con el rol y los permisos pertinentes

---

### 🔄 Flujo del Sistema

| Actor principal (usuario) | Actor Secundario (sistema) |
| :--- | :--- |
| | El sistema cara todas las notificaciones que han sido enviadas previamente en la plataforma |
| El usuario filtra y visualiza las notificaciones cargadas | |
| El usuario puede volver a enviar una de las notificaciones previamente creadas y enviadas | |
| | El sistema ejecuta el servicio de envío |
| **Fin** | |

---

### 🔀 Flujo alternativo del sistema

| Acción del Usuario | Reacción del Sistema |
| :--- | :--- |
| El usuario puede crear una nueva notificación | El sistema redirige a **CU-075-MAS-NWNT** |
| El usuario puede modificar los parámetros de una notificación creada o enviada | El sistema Redirige a **CU-076-MAS-EDNT** |

---

### ✅ Post Condición del sistema

| Escenario | Resultado |
| :--- | :--- |
| **Éxito** | El sistema mantiene la integridad de los filtros aplicados hasta que el usuario los limpie o refresque la página. Debe quedar un registro histórico de la notificación enviada. Los destinatarios reciben la notificación. |
| **Fallo** | |

---

### 🔗 CU - Relacionado
* [CU-075-MAS-NWNT](02%20Casos%20de%20uso/CU-075-MAS-NWNT.md)
* [CU-076-MAS-EDNT](02%20Casos%20de%20uso/CU-076-MAS-EDNT.md)
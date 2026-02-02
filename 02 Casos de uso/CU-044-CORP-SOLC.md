## Caso de Uso: CU-044-CORP-SOLC - Solicitudes Corporativas

Este caso de uso describe la funcionalidad que permite al administrador gestionar las solicitudes de nuevas entidades que desean registrarse como clientes corporativos, facilitando la revisión de su documentación y la toma de decisiones sobre su acceso a la plataforma.

### 📋 Información General

| Sección | Descripción |
| :--- | :--- |
| **ID** | CU-044-CORP-SOLC |
| **Caso de Uso** | Dashboard de usuarios |
| **Actor Principal** | Usuario |
| **Actor Secundario** | Software |
| **Objetivo** | Permite visualizar todos los registros de solicitudes corporativas pendientes por ser aprobadas o rechazadas. |
| **Prioridad** | Alta |

---

### 🛠️ Precondiciones del Sistema
* El usuario inició sesión de forma exitosa (**CU-001-ADM / CU-001-CLI**).
* El usuario cuenta con el rol y los permisos pertinentes.

---

### 🔄 Flujo del Sistema

| Actor Principal (Usuario) | Actor Secundario (Sistema) |
| :--- | :--- |
| | 1) El sistema despliega una tabla con los datos del solicitante: Nombre, Email, Teléfono, Ubicación (País, Ciudad, Dirección), Estado actual, Fecha de Registro y Documentos adjuntos. |
| 2) El administrador consulta la información. | |
| 3) El administrador puede aplicar filtros sobre la información obtenida. | 4) Se muestran los nuevos datos filtrados. |
| 5) El administrador puede aprobar una solicitud. | 6) Muestra un mensaje con el resultado de la operación. |
| 7) El administrador puede rechazar una solicitud. | 8) Muestra un mensaje con el resultado de la operación. |
| 9) Puede exportar en un excel la información de los solicitantes. | |
| **Fin** | |

---

### 🔀 Flujo Alternativo del Sistema
* El administrador puede visualizar los documentos adjuntos antes de tomar una decisión de aprobación o rechazo.

---

### ✅ Post-Condiciones

| Escenario | Resultado Esperado |
| :--- | :--- |
| **Éxito (Aprobación)** | Se aprueba y crea formalmente el perfil corporativo, se envía una notificación automática por correo al solicitante y se habilitan sus credenciales de acceso. |
| **Éxito (Rechazo)** | El registro permanece en el historial como "Rechazado". |
| **Fallo** | No son cargados los datos y la tabla se mantiene vacía. |

---

### 🔗 Casos de Uso Relacionados
* [CU-042-CORP-DASH](02%20Casos%20de%20uso/CU-042-CORP-DASH.md)
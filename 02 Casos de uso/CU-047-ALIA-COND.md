## Caso de Uso: CU-047-ALIA-COND - Conductores de un aliado

Este caso de uso describe la funcionalidad que permite al administrador visualizar y gestionar el listado de conductores vinculados a un aliado específico, facilitando la supervisión de su estado y el acceso a sus perfiles individuales.

### 📋 Información General

| Sección | Descripción |
| :--- | :--- |
| **ID** | CU-047-ALIA-COND |
| **Caso de Uso** | Conductores de un aliado |
| **Actor Principal** | Usuario |
| **Actor Secundario** | Software |
| **Objetivo** | Permite visualizar un listado con información de los conductores de un aliado. |
| **Prioridad** | Alta |

---

### 🛠️ Precondiciones del Sistema
* El usuario inicia sesión de forma exitosa (**CU-001-ADM / CU-001-CLI**).
* El usuario cuenta con el rol y los permisos pertinentes.
* El usuario hizo clic en "ver conductor" desde **CU-045-ALIA-DASH**.

---

### 🔄 Flujo del Sistema

| Actor Principal (Usuario) | Actor Secundario (Sistema) |
| :--- | :--- |
| | 1) El sistema carga un listado de conductores con información de nombre, email, teléfono y ciudad. |
| 2) El usuario puede aplicar filtros sobre los resultados. | |
| 3) El usuario visualiza la información. | |
| 4) El usuario puede aprobar a un conductor aliado. | 5) Muestra pop-up con información a enviar. |
| **Fin** | |

---

### 🔀 Flujo Alternativo del Sistema

| Acción del Usuario | Reacción del Sistema |
| :--- | :--- |
| El usuario puede editar el perfil del conductor. | El sistema redirige a **CU-022-CON-PERF**. |
| El usuario puede ver el historial del conductor. | El sistema redirige a **CU-024-CON-HIST**. |
| El usuario visualiza y edita los documentos del conductor de aliado. | El sistema redirige a **CU-033-CON-DOCE**. |

---

### ✅ Post-Condiciones

| Escenario | Resultado Esperado |
| :--- | :--- |
| **Éxito** | El usuario aplica los filtros y la información se muestra de forma adecuada. |
| **Fallo** | No existe coincidencia luego de ejecutarse la consulta; se muestra la tabla vacía. |

---

### 🔗 Casos de Uso Relacionados
* [CU-045-ALIA-DASH](02%20Casos%20de%20uso/CU-045-ALIA-DASH.md)
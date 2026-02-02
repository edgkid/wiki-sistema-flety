## Caso de Uso: CU-045-ALIA-DASH - Aliados dashboard

Este caso de uso describe la funcionalidad que permite centralizar y gestionar a los aliados registrados en la plataforma. A través de este dashboard, el administrador puede supervisar el rendimiento, validar documentación legal y financiera, y controlar el estado operativo de conductores y vehículos asociados.

### 📋 Información General

| Sección | Descripción |
| :--- | :--- |
| **ID** | CU-045-ALIA-DASH |
| **Caso de Uso** | Aliados dashboard |
| **Actor Principal** | Usuario |
| **Actor Secundario** | Software |
| **Objetivo** | Permite centralizar y mostrar los aliados registrados; esta tabla permite mostrar detalle de aliados, historial de operaciones, vehículos asociados y detalle de información bancaria. Se podrá aprobar y rechazar aliados. |
| **Prioridad** | Alta |

---

### 🛠️ Precondiciones del Sistema
* El usuario inicia sesión de forma exitosa (**CU-001-ADM / CU-001-CLI**).
* El usuario cuenta con el rol y los permisos pertinentes.

---

### 🔄 Flujo del Sistema

| Actor Principal (Usuario) | Actor Secundario (Sistema) |
| :--- | :--- |
| | 1) El sistema muestra una tabla con información de aliados: Nombre, Empresa, RIF, Cantidad de viajes completados, Vehículos activos y Choferes registrados. |
| 2) El administrador puede aplicar filtros para encontrar un aliado específico. | |
| 3) El administrador despliega el menú "Opciones" de un aliado para realizar tareas de supervisión. | |
| 4) El administrador puede eliminar un aliado. | 5) El sistema muestra un mensaje de confirmación. |
| 6) El administrador puede rechazar un aliado. | 7) El sistema muestra un mensaje con el resultado de la operación. |
| 8) El administrador puede aprobar un aliado. | 9) El sistema muestra un mensaje con el resultado de la operación. |
| 10) El administrador puede borrar un documento de identificación. | 11) El sistema muestra un mensaje con el resultado de la operación. |
| **Fin** | |

---

### 🔀 Flujo Alternativo del Sistema

| Acción del Usuario | Reacción del Sistema |
| :--- | :--- |
| Consultar la información detallada de un aliado. | El sistema redirige a **CU-046-ALIA-DETA**. |
| Consultar y gestionar los viajes completados. | El sistema redirige a **CU-008-EST-VIAC**. |
| Consultar y gestionar los vehículos asociados a un aliado. | El sistema redirige a **CU-034-CAM-DASH**. |
| Consultar y gestionar los conductores asociados a un aliado. | El sistema redirige a **CU-047-ALIA-COND**. |
| Detallar la información de cuenta de banco. | El sistema redirige a **CU-048-ALIA-BANC**. |
| Asignar una billetera a un usuario. | Muestra una ventana para agregar monto de billetera. |

---

### ✅ Post-Condiciones

| Escenario | Resultado Esperado |
| :--- | :--- |
| **Éxito (Operativo)** | Cualquier cambio realizado (como marcar como "Aprobado") se refleja de inmediato en el estado operativo del aliado. |
| **Éxito (Sincronización)** | Al modificar datos a través de "Vehículo" o "Conductor", el sistema actualiza automáticamente la disponibilidad de la flota. |
| **Fallo** | El sistema no logra actualizar el estado y se mantiene la información previa sin cambios. |

---

### 🔗 Casos de Uso Relacionados
* [CU-008-EST-VIAC](02%20Casos%20de%20uso/CU-008-EST-VIAC.md)
* [CU-034-CAM-DASH](02%20Casos%20de%20uso/CU-034-Camiones.md)
* [CU-047-ALIA-COND](02%20Casos%20de%20uso/CU-047-ALIA-COND.md)
* [CU-048-ALIA-BANC](02%20Casos%20de%20uso/CU-048-ALIA-BANC.md)
* [CU-046-ALIA-DETA](02%20Casos%20de%20uso/CU-046-ALIA-DETA.md)
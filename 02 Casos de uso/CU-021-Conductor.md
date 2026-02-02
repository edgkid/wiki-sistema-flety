## Caso de Uso: CU-021-CON-ENLI - Conductores en línea

Este caso de uso describe la funcionalidad que permite obtener una visión completa de los conductores que están actualmente "En Línea" (disponibles o activos en la aplicación). Facilita el monitoreo del rendimiento, la verificación de documentación y la ejecución de acciones de gestión inmediata.

### 📋 Información General

| Sección | Descripción |
| :--- | :--- |
| **ID** | CU-021-CON-ENLI |
| **Caso de Uso** | Conductores en Línea |
| **Actor Principal** | Usuario |
| **Actor Secundario** | Software |
| **Objetivo** | Permite obtener una visión completa de los conductores que están actualmente "En Línea" (disponibles o activos en la aplicación). Permite revisar su rendimiento histórico (Solicitudes, Completados, Cancelados), verificar su documentación y estado de aprobación, y tomar acciones de gestión inmediata (editar, rechazar, ver documentos). |
| **Prioridad** | Alta |

---

### 🛠️ Precondiciones del Sistema
* El usuario inicia sesión de forma exitosa (**CU-001-ADM / CU-001-CLI**).
* El usuario cuenta con el rol y los permisos pertinentes.
* Existen conductores registrados y actualmente con el estatus "En Línea".

---

### 🔄 Flujo del Sistema

| Actor Principal (Usuario) | Actor Secundario (Sistema) |
| :--- | :--- |
| | 1) Carga la información de los conductores en línea; item, nombre, solicitud, completado, cancelado, viaje asignado, ciudad, modelo camión, estatus y aliados. |
| 2) Consulta la información mostrada. | |
| 3) El usuario puede filtrar los datos mostrados en pantalla. | |
| **Fin** | |

---

### 🔀 Flujo Alternativo (Acciones de Gestión)

| Acción del Usuario | Reacción del Sistema |
| :--- | :--- |
| El usuario desea editar los detalles. | Redirige a **CU-022-CON-PERF**. |
| Puede consultar la información del vehículo. | Redirige a **CU-023-CON-VEHÍ**. |
| Puede consultar el historial. | Redirige a **CU-024-CON-HIST**. |
| Puede consultar el historial de referencias. | Redirige a **CU-025-CON-HISR**. |
| Puede consultar documentación. | Redirige a **CU-026-CON-DOC**. |
| Permite el rechazo del conductor. | Muestra mensaje con resultado de la operación. |
| Permite reactivar un conductor. | Muestra mensaje con resultado de la operación. |

---

### ✅ Post-Condiciones

| Escenario | Resultado Esperado |
| :--- | :--- |
| **Gestión Informativa** | El administrador tiene una comprensión clara del estado operativo y el rendimiento de los conductores. |
| **Exportación** | Se ha generado un archivo de reporte si se usó la función Exportar. |
| **Acciones Realizadas** | Si se realizaron acciones de gestión (Editar, Rechazar), el estatus del conductor ha sido actualizado. |

---

### 🔗 Casos de Uso Relacionados
* [CU-022-CON-PERF](02%20Casos%20de%20uso/CU-022-CON-PERF.md)
* [CU-023-CON-VEHÍ](02%20Casos%20de%20uso/CU-023-CON-VEHÍ.md)
* [CU-024-CON-HIST](02%20Casos%20de%20uso/CU-024-CON-HIST.md)
* [CU-025-CON-HISR](02%20Casos%20de%20uso/CU-025-CON-HISR.md)
* [CU-026-CON-DOC](02%20Casos%20de%20uso/CU-026-CON-DOC.md)
* [CU-027-CON-APRO](02%20Casos%20de%20uso/CU-027-CON-APRO.md)
* [CU-028-CON-NPRO](02%20Casos%20de%20uso/CU-028-CON-NPRO.md)
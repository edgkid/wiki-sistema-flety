## Caso de Uso: CU-024-CON-HIST - Historial del conductor

Este caso de uso describe la funcionalidad que permite a los usuarios administrativos consultar, buscar, filtrar y exportar el registro histórico detallado de todas las actividades realizadas por un conductor dentro del sistema, incluyendo transacciones y estados de viaje.

### 📋 Información General

| Sección | Descripción |
| :--- | :--- |
| **ID** | CU-024-CON-HIST |
| **Caso de Uso** | Historial del conductor |
| **Actor Principal** | Usuario |
| **Actor Secundario** | Software |
| **Objetivo** | Permite consultar, buscar, filtrar y exportar el historial detallado de las actividades de un conductor en el sistema. |
| **Prioridad** | Alta |

---

### 🛠️ Precondiciones del Sistema
* El usuario inicia sesión de forma exitosa (**CU-001-ADM / CU-001-CLI**).
* El usuario cuenta con el rol y los permisos pertinentes.
* El usuario hizo clic en editar desde **CU-023-CON-VEHI**.
* Debe existir información de las actividades realizadas por el conductor.

---

### 🔄 Flujo del Sistema

| Actor Principal (Usuario) | Actor Secundario (Sistema) |
| :--- | :--- |
| | 1) El sistema carga y muestra la tabla principal con los registros más recientes del historial: Ítem, usuario, fecha y hora, estatus, monto y forma de pago. |
| 2) Puede consultar la información mostrada. | |
| 3) El usuario puede filtrar los datos mostrados. | |
| **Fin** | |

---

### 🔀 Flujo Alternativo

| Actor Principal (Usuario) | Actor Secundario (Sistema) |
| :--- | :--- |
| 1) El usuario puede interactuar con otros módulos del sistema, aquellos que su rol le permita. | |
| 2) El usuario puede consultar los detalles del viaje en el mapa. | 3) Redirige a **CU-31-CON-MAPV**. |
| 4) El usuario puede detallar la factura del viaje realizado. | 5) Redirige a **CU-32-CON-FACT**. |

---

### ✅ Post-Condiciones

| Escenario | Resultado Esperado |
| :--- | :--- |
| **Consulta Exitosa** | El administrador visualiza correctamente el desglose de actividades y pagos del conductor. |
| **Filtro/Búsqueda** | El sistema actualiza la vista para mostrar únicamente los registros que coinciden con los criterios ingresados. |

---

### 🔗 Casos de Uso Relacionados
* [Conductor (CU-021)](02%20Casos%20de%20uso/CU-021-Conductor.md)
* [CU-027-CON-APRO](02%20Casos%20de%20uso/CU-027-CON-APRO.md)
* [CU-028-CON-NPRO](02%20Casos%20de%20uso/CU-028-CON-NPRO.md)
* [CU-31-CON-MAPV](02%20Casos%20de%20uso/CU-31-CON-MAPV.md)
* [CU-32-CON-FACT](02%20Casos%20de%20uso/CU-32-CON-FACT.md)
## Caso de Uso: CU-031-CON-MAPV - Ver Mapa del viaje

Este caso de uso describe la funcionalidad que permite al administrador visualizar de manera gráfica la trayectoria de un servicio individual ya completado. Proporciona detalles operativos precisos, ubicaciones geográficas de carga y descarga, y métricas de rendimiento del viaje sobre un mapa interactivo.

### 📋 Información General

| Sección | Descripción |
| :--- | :--- |
| **ID** | CU-031-CON-MAPV |
| **Caso de Uso** | Ver Mapa del viaje |
| **Actor Principal** | Usuario |
| **Actor Secundario** | Software |
| **Objetivo** | Permite revisar y validar todos los detalles operacionales, geográficos y de costo de un servicio individual ya completado. |
| **Prioridad** | Alta |

---

### 🛠️ Precondiciones del Sistema
* El usuario inicia sesión de forma exitosa (**CU-001-ADM / CU-001-CLI**).
* El usuario cuenta con el rol y los permisos pertinentes.
* El usuario hizo clic en editar desde **CU-024-CON-HIST**.
* El viaje existe en el sistema.

---

### 🔄 Flujo del Sistema

| Actor Principal (Usuario) | Actor Secundario (Sistema) |
| :--- | :--- |
| | 1) El sistema carga información asociada a la ruta del viaje. |
| | 2) El sistema carga ubicación geográfica en el mapa. |
| | 3) El sistema muestra datos del usuario, conductor, origen y destino de carga. |
| | 4) El sistema muestra información de costo del viaje, velocidad media, distancia media y método de pago de viaje. |
| 5) El usuario consulta la información. | |
| **Fin** | |

---

### 🔀 Flujo Alternativo

| Actor Principal (Usuario) | Actor Secundario (Sistema) |
| :--- | :--- |
| 1) El usuario puede interactuar con otros módulos del sistema, aquellos que su rol le permita. | |
| 2) El Usuario puede Optimizar el viaje. | |

---

### ✅ Post-Condiciones

| Escenario | Resultado Esperado |
| :--- | :--- |
| **Éxito** | El usuario puede interactuar con otros módulos del sistema, aquellos que su rol le permita. |

---

### 🔗 Casos de Uso Relacionados
* [Conductor (CU-021)](02%20Casos%20de%20uso/CU-021-Conductor.md)
* [CU-027-CON-APRO](02%20Casos%20de%20uso/CU-027-CON-APRO.md)
* [CU-028-CON-NPRO](02%20Casos%20de%20uso/CU-028-CON-NPRO.md)
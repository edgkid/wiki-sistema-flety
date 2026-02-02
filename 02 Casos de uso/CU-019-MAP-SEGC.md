## Caso de Uso: CU-019-MAP-SEGC - Seguimiento del conductor

Este caso de uso describe la funcionalidad que permite localizar la posición actual de un conductor específico para verificar su cumplimiento de ruta, coordinar una emergencia o dar soporte.

### 📋 Información General

| Sección | Descripción |
| :--- | :--- |
| **ID** | CU-019-MAP-SEGC |
| **Caso de Uso** | Seguimiento del conductor |
| **Actor Principal** | Usuario |
| **Actor Secundario** | Software |
| **Objetivo** | Permite localizar la posición actual de un conductor específico, para verificar su cumplimiento de ruta, coordinar una emergencia, o dar soporte. |
| **Prioridad** | Alta |

---

### 🛠️ Precondiciones del Sistema
* El usuario inicia sesión de forma exitosa (**CU-001-ADM / CU-001-CLI**).
* El usuario cuenta con el rol y los permisos pertinentes.
* Deben existir viajes por mostrar en el mapa.
* El conductor debe estar activo y con un viaje en curso.

---

### 🔄 Flujo del Sistema

| Actor Principal (Usuario) | Actor Secundario (Sistema) |
| :--- | :--- |
| | 1) Carga la ruta del conductor. |
| | 2) El sistema carga exitosamente la librería de Google Maps. |
| | 3) Muestra un mapa que abarca la ruta del conductor. |
| 4) El administrador monitorea y hace seguimiento. | |
| 5) El administrador puede aplicar filtros por tipo de vehículo y por actividad del conductor; activo, inactivo, esperando viaje, en viaje. | |
| 6) El administrador puede filtrar la ruta de seguimiento por ubicación. | |
| **Fin** | |

---

### 🔀 Flujo Alternativo

| Actor Principal (Usuario) | Actor Secundario (Sistema) |
| :--- | :--- |
| 1) Desea encontrar la ubicación de un conductor específico cuyo nombre conoce. | |
| 2) Ignora los filtros desplegables e ingresa el nombre o ID del conductor en el campo "Buscar...". | |
| | 3) El mapa se centra o se resalta el marcador del conductor buscado, ignorando otros filtros aplicados. |
| 4) Vuelve al flujo principal. | |

---

### ✅ Post-Condiciones

| Escenario de Éxito | Escenario de Fallo |
| :--- | :--- |
| El administrador ha logrado visualizar la ubicación específica del conductor. | El administrador ha confirmado un problema de configuración del sistema de mapas, impidiendo el seguimiento visual. |

---

### 🔗 Casos de Uso Relacionados
* [CU-017-MAP-MAV](02%20Casos%20de%20uso/CU-017-MAP-MAV.md)
* [CU-018-MAP-MAC](02%20Casos%20de%20uso/CU-018-MAP-MAC.md)

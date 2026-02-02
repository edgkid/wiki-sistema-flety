# ## Caso de Uso: CU-018-MAP-MAC - Mapas de viajes de conductores

Este caso de uso describe la funcionalidad que permite visualizar la ubicación geográfica de los conductores en tiempo real. El sistema integra herramientas de filtrado para que el administrador pueda monitorear grupos específicos según su tipo de vehículo o estado operativo.

### 📋 Información General

| Sección | Descripción |
| :--- | :--- |
| **ID** | CU-018-MAP-MAC |
| **Caso de Uso** | Mapas de viajes |
| **Actor Principal** | Usuario |
| **Actor Secundario** | Software |
| **Objetivo** | Permite mostrar una representación geográfica de la ubicación actual de los conductores, también permite aplicar filtros para centrar la atención en grupos específicos de conductores. |
| **Prioridad** | Alta |

---

### 🛠️ Precondiciones del Sistema
* El usuario inicia sesión de forma exitosa (**CU-001-ADM / CU-001-CLI**).
* El usuario cuenta con el rol y los permisos pertinentes.
* Deben existir viajes por mostrar en el mapa.

---

### 🔄 Flujo del Sistema

| Actor Principal (Usuario) | Actor Secundario (Sistema) |
| :--- | :--- |
| | 1) Se cargan los viajes existentes. |
| | 2) El sistema carga exitosamente la librería de Google Maps. |
| | 3) Muestra un mapa que abarca el área de operación de la flota. |
| 4) El administrador monitorea el movimiento general de la flota. | |
| 5) El administrador puede aplicar filtros por tipo de vehículo y por actividad del conductor: activo, inactivo, esperando viaje, en viaje. | |
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
| El administrador tiene una vista clara y filtrada de las ubicaciones de los conductores y camiones. | Se produce un fallo en la inicialización de la API de Google Maps. |

---

### 🔗 Casos de Uso Relacionados
* [CU-017-MAP-MAV](02%20Casos%20de%20uso/CU-017-MAP-MAV.md)
* [CU-019-MAP-SEGC](02%20Casos%20de%20uso/CU-019-MAP-SEGC.md)
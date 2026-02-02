## Caso de Uso: CU-017-MAP-MAV - Mapas de viajes

Este caso de uso describe la funcionalidad de visualización geográfica de los servicios. El sistema integra una API de mapas para renderizar las métricas y ubicaciones, permitiendo al usuario realizar un monitoreo visual de la flota y el estado de los viajes.

### 📋 Información General

| Sección | Descripción |
| :--- | :--- |
| **ID** | CU-017-MAP-MAV |
| **Caso de Uso** | Mapas de viajes |
| **Actor Principal** | Usuario |
| **Actor Secundario** | Software |
| **Objetivo** | Permite mostrar el conteo de los viajes en diferentes estados (Activos, Futuros, Completados) y las ubicaciones geográficas de todos los viajes activos de la flota. |
| **Prioridad** | Alta |

---

### 🛠️ Precondiciones del Sistema
* El usuario inició sesión de forma exitosa (**CU-001-ADM / CU-001-CLI**).
* El usuario cuenta con el rol y los permisos pertinentes.
* Deben existir viajes por mostrar en el mapa.

---

### 🔄 Flujo del Sistema

| Actor Principal (Usuario) | Actor Secundario (Sistema) |
| :--- | :--- |
| | 1) Se cargan métricas de viajes; viajes activos, viajes futuros, viajes completados y total de viajes / mes. |
| | 2) El sistema carga exitosamente la librería de Google Maps. |
| | 3) Muestra un mapa que abarca el área de operación de la flota. |
| 4) El administrador monitorea el movimiento general de la flota. | |
| **Fin** | |

---

### 🔀 Flujo Alternativo

| Escenario | Resultado |
| :--- | :--- |
| **1) Sin Información Disponible** | El sistema no puede mostrar el tablero con las métricas correctas y se cargan valores por default. |
| **2) Error de API** | Se produce un fallo en la inicialización de la API de Google Maps. El usuario visualiza el error: "Se produjo un error. Esta página no cargó bien Google Maps..." |

---

### ✅ Post-Condiciones

| Escenario de Éxito | Escenario de Fallo |
| :--- | :--- |
| El administrador ha obtenido una vista general y geolocalizada de la operación de la flota. | Puede que el administrador solo tiene acceso a las métricas. |

---

### 🔗 Casos de Uso Relacionados
* [CU-018-MAP-MAC](02%20Casos%20de%20uso/CU-018-MAP-MAC.md)
* [CU-019-MAP-SEGC](02%20Casos%20de%20uso/CU-019-MAP-SEGC.md)

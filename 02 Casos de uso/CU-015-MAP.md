## Caso de Uso: CU-015-MAP - Mapa

Este caso de uso describe la funcionalidad de visualización geográfica de los servicios. El sistema integra una API de mapas para renderizar las rutas, permitiendo al usuario realizar un seguimiento visual del origen, destino y paradas intermedias de los viajes, independientemente de su estado operativo.

---

## 📋 Información General

| Sección | Descripción |
| :--- | :--- |
| **ID** | CU-015-MAP |
| **Caso de Uso** | Mapa |
| **Actor Principal** | Usuario |
| **Actor Secundario** | Software |
| **Objetivo** | Permite ver la ruta de los viajes en curso, cancelados, entrantes y futuros. |
| **Prioridad** | Alta |

---

## 🛠️ Precondiciones del Sistema
* El usuario inició sesión de forma exitosa (**CU-001-ADM** / **CU-001-CLI**).
* El usuario está consultando el mapa desde: **CU-014-EST-VIAE**, **CU-007-EST-VIAA**, **CU-008-EST-VIAC** o **CU-009-EST-VIAF**.
* El usuario cuenta con el rol y los permisos pertinentes.
* Existe información de estadísticas y viajes registrados con coordenadas válidas.

---

## 🔄 Flujo del Sistema



| Actor Principal (Usuario) | Actor Secundario (Sistema) |
| :--- | :--- |
| | 1) El sistema carga la interfaz del Mapa a través de la API (Google Maps/Mapbox). |
| | 2) Marca la ruta dinámicamente según la información traída del módulo de origen correspondiente. |
| 3) Verifica la ruta sobre el mapa (Origen, Destino y Paradas externas) | 4) El sistema renderiza los puntos de interés y la trayectoria calculada. |

---

## 🔀 Flujo Alternativo

| Escenario | Resultado |
| :--- | :--- |
| **1) Sin Información Disponible** | El sistema muestra un mapa base sin rutas o valores por defecto. |
| **2) Interacción restringida** | El usuario interactúa únicamente con las herramientas de zoom y desplazamiento permitidas por su rol. |

---

## ✅ Post-Condiciones

| Escenario de Éxito | Escenario de Fallo |
| :--- | :--- |
| La vista de mapa se muestra completamente renderizada con la ruta cargada. | Se muestra mensaje de error de carga de la API o mapa en blanco. |
| Se visualizan claramente los marcadores de origen y destino. | Los valores de coordenadas se muestran por defecto (0,0). |

---

## 🔗 Casos de Uso Relacionados
* [CU-007-EST-VIAA](02%20Casos%20de%20uso/CU-007-EST-VIAA.md)
* [CU-008-EST-VIAC](02%20Casos%20de%20uso/CU-008-EST-VIAC.md) 
* [CU-009-EST-VIAF](02%20Casos%20de%20uso/CU-009-EST-VIAF.md)
* [CU-014-EST-VIAE](02%20Casos%20de%20uso/CU-014-EST-VIAE.md)
* [Estadísticas (CU-004)](02%20Casos%20de%20uso/CU-004%20-%20Dashboard.md)
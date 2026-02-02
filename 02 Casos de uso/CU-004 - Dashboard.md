## Caso de Uso: CU-004-EST-EST - Dashboard de Usuario - Estadísticas

Este caso de uso describe la visualización de la pantalla principal de indicadores clave de rendimiento (KPIs). El sistema consolida datos transaccionales de viajes y finanzas para presentarlos de forma gráfica y resumida, permitiendo a los usuarios (según su rol) tomar decisiones basadas en el comportamiento operativo de la plataforma.

---

## 📋 Información General

| Sección | Descripción |
| :--- | :--- |
| **ID** | CU-004-EST-EST |
| **Caso de Uso** | Dashboard de usuario - estadísticas generales |
| **Actor Principal** | Usuario |
| **Actor Secundario** | Software |
| **Objetivo** | Mostrar como dashboard principal las estadísticas contenidas dentro del módulo de estadísticas. La información depende del rol de usuario. |
| **Prioridad** | Alta |

---

## 🛠️ Precondiciones del Sistema
* El usuario inició sesión de forma exitosa (**CU-001-ADM** / **CU-001-CLI**).
* El usuario cuenta con el rol y los permisos pertinentes para visualizar datos sensibles.
* Existe información histórica de viajes y transacciones en la base de datos.
* Los servicios de consulta (APIs de analítica) se encuentran disponibles.

---

## 🔄 Flujo del Sistema



| Actor Principal (Usuario) | Actor Secundario (Sistema) |
| :--- | :--- |
| | 1) El sistema inicia la carga de la vista y la información predeterminada. |
| | 2) Permite la visualización de estadísticas principales según el rol detectado. |
| | 3) Muestra indicadores clave (KPIs): **Viajes Activos**, **Viajes Realizados**, **Facturado**, **KM Recorridos**. |
| 4) Puede filtrar la información por país | 5) Actualiza dinámicamente los gráficos y totales según el filtro seleccionado. |

---

## 🔀 Flujo Alternativo

| Escenario | Resultado |
| :--- | :--- |
| **1) Sin información a mostrar** | El sistema carga datos por default (totalizaciones en 0). |
| **2) Permisos restringidos** | El usuario solo visualiza los módulos y submódulos permitidos para su rol. |

---

## ✅ Post-Condiciones

| Escenario de Éxito | Escenario de Fallo |
| :--- | :--- |
| Es mostrada toda la información de estadísticas | El sistema muestra valores por defecto (ceros) |
| Se visualizan indicadores de rendimiento completos | Los gráficos no cargan o muestran error de conexión |
| El filtro de país se aplica correctamente | |

---

## 🔗 Casos de Uso Relacionados (Módulo Estadístico)
* [ Estadísticas (CU-004)](02%20Casos%20de%20uso/CU-004%20-%20Dashboard.md)
* [ CU-005-EST-DATF](02%20Casos%20de%20uso/CU-005-EST-DATF.md)
* [CU-006-EST-DATU](02%20Casos%20de%20uso/CU-006-EST-DATU.md)
* [CU-007-EST-VIAA](02%20Casos%20de%20uso/CU-007-EST-VIAA.md)
* [CU-008-EST-VIAC](02%20Casos%20de%20uso/CU-008-EST-VIAC.md) 
* [CU-009-EST-VIAF](02%20Casos%20de%20uso/CU-009-EST-VIAF.md)
* [CU-010-EST-HIT](02%20Casos%20de%20uso/CU-010-EST-HIT.md) 
* [CU-011-EST-RES](02%20Casos%20de%20uso/CU-011-EST-RES.md) 
* [CU-012-EST-MOC](02%20Casos%20de%20uso/CU-012-EST-MOC.md)
* [CU-013-EST-BILL](02%20Casos%20de%20uso/CU-013-EST-BILL.md)
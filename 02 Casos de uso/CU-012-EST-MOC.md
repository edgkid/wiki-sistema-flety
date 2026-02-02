## Caso de Uso: CU-012-EST-MOC - Motivo de Cancelación

Este caso de uso describe la funcionalidad para auditar los servicios que no llegaron a completarse. El sistema permite identificar patrones de abandono o problemas operativos mediante el análisis de las razones declaradas por los actores (usuarios o conductores) al momento de anular un viaje.

---

## 📋 Información General

| Sección | Descripción |
| :--- | :--- |
| **ID** | CU-012-EST-MOC |
| **Caso de Uso** | Motivo de cancelación |
| **Actor Principal** | Usuario |
| **Actor Secundario** | Software |
| **Objetivo** | Permite supervisar y analizar todos los viajes que han sido cancelados. |
| **Prioridad** | Alta |

---

## 🛠️ Precondiciones del Sistema
* El usuario inició sesión de forma exitosa (**CU-001-ADM** / **CU-001-CLI**).
* El usuario cuenta con el rol y los permisos pertinentes.
* Existe información de estadísticas y registros de cancelaciones en el sistema.

---

## 🔄 Flujo del Sistema



| Actor Principal (Usuario) | Actor Secundario (Sistema) |
| :--- | :--- |
| | 1) El sistema ejecuta una consulta y muestra un listado con la información de viajes cancelados existentes. |
| | 2) Se muestra: ID del viaje, Fecha de cancelación, ID del usuario, Usuario, Número de Cédula, Conductor, Razón de cancelación y Cancelado por. |
| 3) Puede filtrar los resultados por Ítems de resultado, fecha y rango de fecha | 4) El sistema actualiza la lista según los filtros aplicados. |

---

## 🔀 Flujo Alternativo

| Escenario | Resultado |
| :--- | :--- |
| **1) Interacción restringida** | El usuario interactúa únicamente con los módulos que puede visualizar según su rol. |

---

## ✅ Post-Condiciones

| Escenario de Éxito | Escenario de Fallo |
| :--- | :--- |
| Es mostrada toda la información de estadísticas de cancelaciones. | El sistema muestra valores por defecto. |

---

## 🔗 Casos de Uso Relacionados
* [Estadísticas (CU-004)](02%20Casos%20de%20uso/CU-004%20-%20Dashboard.md)
* [ CU-005-EST-DATF](02%20Casos%20de%20uso/CU-005-EST-DATF.md) 
* [CU-006-EST-DATU](02%20Casos%20de%20uso/CU-006-EST-DATU.md) 
* [CU-007-EST-VIAA](02%20Casos%20de%20uso/CU-007-EST-VIAA.md)
* [CU-008-EST-VIAC](02%20Casos%20de%20uso/CU-008-EST-VIAC.md)  
* [CU-009-EST-VIAF](02%20Casos%20de%20uso/CU-009-EST-VIAF.md) 
* [CU-010-EST-HIT](02%20Casos%20de%20uso/CU-010-EST-HIT.md) 
* [CU-011-EST-RES](02%20Casos%20de%20uso/CU-011-EST-RES.md) 
* [CU-013-EST-BILL](02%20Casos%20de%20uso/CU-013-EST-BILL.md) 
* [CU-014-EST-VIAE](02%20Casos%20de%20uso/CU-014-EST-VIAE.md)
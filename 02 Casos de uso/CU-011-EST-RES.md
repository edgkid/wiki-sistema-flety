## Caso de Uso: CU-011-EST-HIST - Reseñas

Este caso de uso describe la funcionalidad para supervisar la calidad del servicio a través de las calificaciones cruzadas. El sistema permite auditar la experiencia tanto del cliente como del conductor para cada trayecto finalizado, facilitando la detección de incidencias o niveles de servicio excepcionales.

---

## 📋 Información General

| Sección | Descripción |
| :--- | :--- |
| **ID** | CU-011-EST-RES |
| **Caso de Uso** | Dashboard de usuario - Reseñas |
| **Actor Principal** | Usuario |
| **Actor Secundario** | Software |
| **Objetivo** | Permite acceder, filtrar y analizar la retroalimentación de calidad proporcionada por los usuarios (clientes) y los conductores (aliados) sobre los viajes completados. |
| **Prioridad** | Alta |

---

## 🛠️ Precondiciones del Sistema
* El usuario inició sesión de forma exitosa (**CU-001-ADM** / **CU-001-CLI**).
* El usuario cuenta con el rol y los permisos pertinentes.
* Existe información de estadísticas en el sistema.

---

## 🔄 Flujo del Sistema



| Actor Principal (Usuario) | Actor Secundario (Sistema) |
| :--- | :--- |
| | 1) El sistema ejecuta una consulta y muestra un listado con la información de las reseñas existentes. |
| | 2) Se muestra: ID del viaje, Fecha, Correo electrónico del usuario, Calificación del usuario, Correo electrónico del conductor y Calificación del conductor. |
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
| Es mostrada toda la información de estadísticas de reseñas. | El sistema muestra valores por defecto. |

---

## 🔗 Casos de Uso Relacionados
* [Estadísticas (CU-004)](02%20Casos%20de%20uso/CU-004%20-%20Dashboard.md)
* [CU-005-EST-DATF](02%20Casos%20de%20uso/CU-005-EST-DATF.md) 
* [CU-006-EST-DATU](02%20Casos%20de%20uso/CU-006-EST-DATU.md) 
* [CU-007-EST-VIAA](02%20Casos%20de%20uso/CU-007-EST-VIAA.md)
* [CU-008-EST-VIAC](02%20Casos%20de%20uso/CU-008-EST-VIAC.md)  
* [CU-009-EST-VIAF](02%20Casos%20de%20uso/CU-009-EST-VIAF.md) 
* [CU-010-EST-HIT](02%20Casos%20de%20uso/CU-010-EST-HIT.md) 
* [CU-012-EST-MOC](02%20Casos%20de%20uso/CU-012-EST-MOC.md)  
* [CU-013-EST-BILL](02%20Casos%20de%20uso/CU-013-EST-BILL.md)
* [CU-014-EST-VIAE](02%20Casos%20de%20uso/CU-014-EST-VIAE.md)
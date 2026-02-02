## Caso de Uso: CU-013-EST-BILL - Billetes de Ferry

Este caso de uso describe la gestión y supervisión de los costos asociados al transporte marítimo (Ferry). El sistema permite controlar los pagos realizados por este concepto, diferenciando por tipo de corporativo y estatus del pago, lo cual es fundamental para la liquidación final de los viajes que requieren este servicio.

---

## 📋 Información General

| Sección | Descripción |
| :--- | :--- |
| **ID** | CU-013-EST-BILL |
| **Caso de Uso** | Dashboard - billetes de ferry |
| **Actor Principal** | Usuario |
| **Actor Secundario** | Software |
| **Objetivo** | Permite supervisar, registrar y administrar todas las transacciones relacionadas con la compra o gestión de billetes de ferry. |
| **Prioridad** | Alta |

---

## 🛠️ Precondiciones del Sistema
* El usuario inició sesión de forma exitosa (**CU-001-ADM** / **CU-001-CLI**).
* El usuario cuenta con el rol y los permisos pertinentes para la gestión administrativa.
* Existe información de estadísticas y registros de transacciones de ferry en el sistema.

---

## 🔄 Flujo del Sistema



| Actor Principal (Usuario) | Actor Secundario (Sistema) |
| :--- | :--- |
| | 1) El sistema ejecuta una consulta y muestra un listado con la información de los registros existentes. |
| | 2) Se muestra: Ítem, Tipo Corporativo, Monto y Estatus. |
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
| Es mostrada toda la información de estadísticas de billetes de ferry. | El sistema muestra valores por defecto. |

---

## 🔗 Casos de Uso Relacionados
* [Estadísticas (CU-004)](02%20Casos%20de%20uso/CU-004%20-%20Dashboard.md)
* [CU-005-EST-DATF](02%20Casos%20de%20uso/CU-005-EST-DATF.md) 
* [CU-006-EST-DATU](02%20Casos%20de%20uso/CU-006-EST-DATU.md) 
* [CU-007-EST-VIAA](02%20Casos%20de%20uso/CU-007-EST-VIAA.md)
* [CU-008-EST-VIAC](02%20Casos%20de%20uso/CU-008-EST-VIAC.md)  
* [CU-009-EST-VIAF](02%20Casos%20de%20uso/CU-009-EST-VIAF.md) 
* [CU-010-EST-HIT](02%20Casos%20de%20uso/CU-010-EST-HIT.md) 
* [CU-011-EST-RES](02%20Casos%20de%20uso/CU-011-EST-RES.md) 
* [CU-012-EST-MOC](02%20Casos%20de%20uso/CU-012-EST-MOC.md)  
* [CU-014-EST-VIAE](02%20Casos%20de%20uso/CU-014-EST-VIAE.md)
## Caso de Uso: CU-014-EST-VIAE - Viajes Entrantes

Este caso de uso describe la funcionalidad de supervisión de los viajes entrantes al sistema. Permite al personal operativo monitorear las solicitudes que están ingresando a la plataforma en tiempo real, facilitando la asignación, clasificación y la gestión administrativa temprana de los servicios antes de su despacho definitivo.

---

## 📋 Información General

| Sección | Descripción |
| :--- | :--- |
| **ID** | CU-014-EST-VIAE |
| **Caso de Uso** | Dashboard de usuario - Viajes entrantes |
| **Actor Principal** | Usuario |
| **Actor Secundario** | Software |
| **Objetivo** | Mostrar la lista en tiempo real de todos los viajes entrantes; monitoreo, clasificación y gestión de operaciones sobre viajes activos. |
| **Prioridad** | Alta |

---

## 🛠️ Precondiciones del Sistema
* El usuario inició sesión de forma exitosa (**CU-001-ADM** / **CU-001-CLI**).
* El usuario cuenta con el rol y los permisos pertinentes.
* Existe información de estadísticas y viajes registrados en estado entrante o curso.

---

## 🔄 Flujo del Sistema



| Actor Principal (Usuario) | Actor Secundario (Sistema) |
| :--- | :--- |
| | 1) Ejecuta una consulta y muestra un listado de viajes entrantes. |
| | 2) Se visualiza: Fecha Creación, Usuario, Unidad, Ruta, Detalles, Estatus y Total de Pagos. |
| 3) Filtra resultados por ítems, fecha y rango | 4) El sistema actualiza la lista según los filtros. |
| 5) Selecciona **Ver Mapa** | 6) Redirige a la vista de geolocalización (**CU-015-MAP**). |
| 7) Selecciona **Cancelar viaje** | 8) Muestra alerta para confirmar la cancelación. |
| 9) Selecciona **Ver detalle** | 10) Muestra un popup con el detalle técnico del viaje. |
| 11) Selecciona **Editar información** | 12) Redirige a la vista de edición de datos (**CU-016-EDV**). |
| 13) Gestiona Pagos (Cliente/Aliado/Preliquidar) | 14) Muestra popups de confirmación para cada acción financiera. |
| 15) Selecciona **Reiniciar viaje** o **Nota** | 16) Muestra popups para reiniciar o agregar notas al viaje. |
| 17) Selecciona **Exportar CSV** | 18) Genera los datos para descarga en formato CSV. |

---

## 🔀 Flujo Alternativo

| Escenario | Resultado |
| :--- | :--- |
| **1) Sin Información Disponible** | El sistema muestra valores por defecto (tabla vacía). |
| **2) Interacción con módulos** | El usuario interactúa solo con funciones permitidas según su rol. |

---

## ✅ Post-Condiciones

| Escenario de Éxito | Escenario de Fallo |
| :--- | :--- |
| La vista de viajes activos se muestra completamente renderizada con todas las opciones de gestión. | Se muestra mensaje de error y valores por defecto. |

---

## 🔗 Casos de Uso Relacionados
* [Estadísticas (CU-004)](02%20Casos%20de%20uso/CU-004%20-%20Dashboard.md)
* [CU-009-EST-VIAF](02%20Casos%20de%20uso/CU-009-EST-VIAF.md)
* [CU-015-MAP](02%20Casos%20de%20uso/CU-015-MAP.md)
* [CU-016-EDV](02%20Casos%20de%20uso/CU-016-EDV.md)
* [CU-005-EST-DATF](02%20Casos%20de%20uso/CU-005-EST-DATF.md) 
* [CU-006-EST-DATU](02%20Casos%20de%20uso/CU-006-EST-DATU.md) 
* [CU-007-EST-VIAA](02%20Casos%20de%20uso/CU-007-EST-VIAA.md)
* [CU-008-EST-VIAC](02%20Casos%20de%20uso/CU-008-EST-VIAC.md)  
* [CU-010-EST-HIT](02%20Casos%20de%20uso/CU-010-EST-HIT.md)  
* [CU-011-EST-RES](02%20Casos%20de%20uso/CU-011-EST-RES.md)
* [CU-012-EST-MOC](02%20Casos%20de%20uso/CU-012-EST-MOC.md)  
* [CU-013-EST-BILL](02%20Casos%20de%20uso/CU-013-EST-BILL.md)
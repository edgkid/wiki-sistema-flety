## Caso de Uso: CU-009-EST-VIAF - Dashboard de Usuario - Viajes Futuros

Este caso de uso describe la funcionalidad de supervisión y planificación de servicios programados para fechas posteriores. Permite a los administradores y usuarios gestionar la logística anticipada, asegurar la disponibilidad de unidades y realizar ajustes administrativos antes de que el viaje pase a estado activo.

---

## 📋 Información General

| Sección | Descripción |
| :--- | :--- |
| **ID** | CU-009-EST-VIAF |
| **Caso de Uso** | Dashboard de usuario - Viajes futuros |
| **Actor Principal** | Usuario |
| **Actor Secundario** | Software |
| **Objetivo** | Mostrar la lista en tiempo real de todos los viajes futuros; monitoreo, clasificación y gestión de operaciones sobre la planificación de servicios. |
| **Prioridad** | Alta |

---

## 🛠️ Precondiciones del Sistema
* El usuario inició sesión de forma exitosa (**CU-001-ADM** / **CU-001-CLI**).
* El usuario cuenta con el rol y los permisos pertinentes para la gestión de flota y despachos.
* Existe información de estadísticas en el sistema.
* Existen viajes registrados con estatus de reserva o programados (futuros).

---

## 🔄 Flujo del Sistema



| Actor Principal (Usuario) | Actor Secundario (Sistema) |
| :--- | :--- |
| | 1) Ejecuta una consulta y muestra un listado de viajes futuros con: Fecha Creación, Usuario, Unidad, Ruta, Detalles, Estatus y Pagos. |
| 2) Filtra resultados por ítems, fecha y rango | 3) Actualiza la visualización de la lista según los filtros aplicados. |
| 4) Hace click en **Ver Mapa** | 5) Redirige a la vista de geolocalización para visualizar la ruta proyectada (**CU-015-MAP**). |
| 6) Selecciona **Cancelar viaje** | 7) Muestra alerta de confirmación para cancelar la programación del viaje. |
| 8) Selecciona **Ver detalle** | 9) Muestra un popup con la información detallada de la reserva. |
| 10) Selecciona **Editar información** | 11) Redirige a la vista de edición de datos básicos del viaje (**CU-016-EDV**). |
| 12) Gestiona Pagos (Cliente/Aliado/Preliquidar) | 13) Muestra popups de confirmación para validar transacciones anticipadas. |
| 14) Selecciona **Reiniciar viaje** o **Agregar nota** | 15) Muestra popups para reinicio de parámetros o registro de observaciones. |
| 16) Selecciona **Exportar CSV** | 17) Genera y descarga el archivo con la programación de viajes en formato CSV. |

---

## 🔀 Flujo Alternativo

| Escenario | Resultado |
| :--- | :--- |
| **1) Sin Información Disponible** | El sistema muestra la tabla con valores por defecto. |
| **2) Interacción con módulos** | El usuario interactúa únicamente con las funciones habilitadas para su rol. |

---

## ✅ Post-Condiciones

| Escenario de Éxito | Escenario de Fallo |
| :--- | :--- |
| La vista de viajes futuros se muestra renderizada con todas las herramientas de gestión. | Se muestra mensaje de error y la tabla carga valores por defecto. |
| Se permite la exportación correcta de la agenda de viajes. | Las acciones de edición o cancelación no se sincronizan con la base de datos. |

---

## 🔗 Casos de Uso Relacionados
* [Estadísticas (CU-004)](02%20Casos%20de%20uso/CU-004%20-%20Dashboard.md)
* [CU-007-EST-VIAA](02%20Casos%20de%20uso/CU-007-EST-VIAA.md)
* [CU-008-EST-VIAC](02%20Casos%20de%20uso/CU-008-EST-VIAC.md) 
* [CU-015-MAP](02%20Casos%20de%20uso/CU-015-MAP.md)
* [CU-016-EDV](02%20Casos%20de%20uso/CU-016-EDV.md)
## Caso de Uso: CU-006-EST-DATU - Dashboard de Usuario - Datos de Usuarios

Este caso de uso describe la visualización de las métricas demográficas y de crecimiento de la base de datos de usuarios. El sistema segmenta la información entre Clientes y Transportistas, permitiendo un análisis detallado de la captación de usuarios por región.

---

## 📋 Información General

| Sección | Descripción |
| :--- | :--- |
| **ID** | CU-006-EST-DATU |
| **Caso de Uso** | Dashboard de usuario - Datos de usuarios |
| **Actor Principal** | Usuario |
| **Actor Secundario** | Software |
| **Objetivo** | Mostrar las métricas de los tipos de usuarios registrados en el sistema (Clientes y Transportistas). |
| **Prioridad** | Alta |

---

## 🛠️ Precondiciones del Sistema
* El usuario inició sesión de forma exitosa (**CU-001-ADM** / **CU-001-CLI**).
* El usuario cuenta con el rol y los permisos pertinentes para visualizar datos de usuarios.
* Existe información de registros en la base de datos.
* Los servicios de consulta se encuentran disponibles.

---

## 🔄 Flujo del Sistema



| Actor Principal (Usuario) | Actor Secundario (Sistema) |
| :--- | :--- |
| 1) Se encuentra en el módulo Estadísticas (Navegando desde **CU-004**) | |
| 2) Hace click en el submódulo **Datos de Usuario** | 3) El sistema valida el rol y permite la visualización de los módulos correspondientes. |
| | 4) Muestra los indicadores específicos de datos de usuario (Nuevos registros, activos vs inactivos). |
| 5) El usuario puede filtrar los resultados por país | 6) El sistema actualiza los indicadores según la región seleccionada. |

---

## 🔀 Flujo Alternativo

| Escenario | Resultado |
| :--- | :--- |
| **1) Sin Información Disponible** | El sistema muestra valores por defecto (Gráficos vacíos o en cero). |
| **2) Interacción restringida** | El usuario solo interactúa con los módulos que su rol permite visualizar. |

---

## ✅ Post-Condiciones

| Escenario de Éxito | Escenario de Fallo |
| :--- | :--- |
| Es mostrada toda la información de estadísticas de usuarios | El sistema muestra valores por defecto |
| Los filtros de país se aplican correctamente | Los datos no cargan debido a problemas de permisos o conexión |

---

## 🔗 Casos de Uso Relacionados
* [Estadísticas (CU-004)](02%20Casos%20de%20uso/CU-004%20-%20Dashboard.md)
* [CU-005-EST-DATF](02%20Casos%20de%20uso/CU-005-EST-DATF.md) 
* [CU-007-EST-VIAA](02%20Casos%20de%20uso/CU-007-EST-VIAA.md)
* [CU-008-EST-VIAC](02%20Casos%20de%20uso/CU-008-EST-VIAC.md) 
* [CU-009-EST-VIAF](02%20Casos%20de%20uso/CU-009-EST-VIAF.md)
* [CU-010-EST-HIT](02%20Casos%20de%20uso/CU-010-EST-HIT.md)  
* [CU-011-EST-RES](02%20Casos%20de%20uso/CU-011-EST-RES.md)
* [CU-012-EST-MOC](02%20Casos%20de%20uso/CU-012-EST-MOC.md) 
* [CU-013-EST-BILL](02%20Casos%20de%20uso/CU-013-EST-BILL.md) 
* [CU-014-EST-VIAE](02%20Casos%20de%20uso/CU-014-EST-VIAE.md)
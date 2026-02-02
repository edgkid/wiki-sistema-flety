## Caso de Uso: CU-036-USU-DASH - Dashboard de usuarios

Este caso de uso describe la funcionalidad que permite visualizar, filtrar y gestionar los perfiles de los usuarios registrados, permitiendo el acceso a su historial de actividad y documentos legales dentro de la plataforma.

### 📋 Información General

| Sección | Descripción |
| :--- | :--- |
| **ID** | CU-036-USU-DASH |
| **Caso de Uso** | Dashboard de usuarios |
| **Actor Principal** | Usuario |
| **Actor Secundario** | Software |
| **Objetivo** | Visualizar, filtrar y gestionar los perfiles de los usuarios registrados, permitiendo el acceso a su historial de actividad y documentos legales. |
| **Prioridad** | Alta |

---

### 🛠️ Precondiciones del Sistema
* El usuario inicia sesión de forma exitosa (**CU-001-ADM / CU-001-CLI**).
* El usuario cuenta con el rol y los permisos pertinentes.

---

### 🔄 Flujo del Sistema

| Actor Principal (Usuario) | Actor Secundario (Sistema) |
| :--- | :--- |
| | 1) El sistema recupera la lista de usuarios y muestra los siguientes campos por registro: Item (ID), Perfil, Nombre, Teléfono, Solicitud, Completado, Cancelado, Ciudad, Portafolio, Versión del App, y Fecha de Registro. |
| 2) Visualiza la información mostrada. | |
| 3) Filtra la información mostrada, indica parámetros como: rango de fecha, ubicación y datos de la tabla. | |
| 4) Puede agregar una billetera a un usuario. | 5) Muestra una ventana para agregar monto de billetera y muestra mensaje de confirmación. |
| 6) Puede rechazar a un usuario. | 7) Rechaza y muestra un mensaje de éxito. |
| 8) Puede eliminar un usuario. | 9) Muestra un mensaje de confirmación. |
| **Fin** | |

---

### 🔀 Flujo Alternativo del Sistema

| Acción del Usuario | Reacción del Sistema |
| :--- | :--- |
| Puede editar los datos del usuario. | Es redirigido a **CU-037-USU-EDIT**. |
| Puede consultar el historial de operaciones del usuario. | Es redirigido a **CU-038-USU-HIST**. |
| Puede consultar el historial de referencia de los usuarios. | Es redirigido a **CU-039-USU-HIRF**. |
| Puede consultar la documentación del usuario. | Es redirigido a **CU-040-USU-UDOC**. |

---

### ✅ Post-Condiciones

| Escenario de Éxito | Escenario de Fallo |
| :--- | :--- |
| Cualquier cambio realizado a través del menú de opciones (como "Rechazado") se refleja inmediatamente. | La tabla se mantiene vacía. |
| Si se aplica un filtro, este se mantiene activo hasta que se realice una nueva búsqueda o se limpie el filtro. | |

---

### 🔗 Casos de Uso Relacionados
* [CU-037-USU-EDIT](02%20Casos%20de%20uso/CU-037-USU-EDIT.md)
* [CU-038-USU-HIST](02%20Casos%20de%20uso/CU-038-USU-HIST.md)
* [CU-039-USU-HIRF](02%20Casos%20de%20uso/CU-039-USU-HIRF.md)
* [CU-040-USU-UDOC](02%20Casos%20de%20uso/CU-040-USU-UDOC.md)
* [CU-041-USU-BLUS](02%20Casos%20de%20uso/CU-041-USU-BLUS.md)
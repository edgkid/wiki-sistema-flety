## Caso de Uso: CU-042-CORP-DASH - Dashboard de usuarios corporativos

Este caso de uso describe la funcionalidad que permite al administrador visualizar, filtrar, buscar y gestionar las acciones administrativas de todos los usuarios corporativos registrados en la plataforma.

### 📋 Información General

| Sección | Descripción |
| :--- | :--- |
| **ID** | CU-042-CORP-DASH |
| **Caso de Uso** | Dashboard de usuarios corporativos |
| **Actor Principal** | Usuario |
| **Actor Secundario** | Software |
| **Objetivo** | Permite al administrador visualizar, filtrar, buscar y gestionar las acciones administrativas (editar, aprobar, eliminar) de todos los usuarios corporativos registrados. |
| **Prioridad** | Alta |

---

### 🛠️ Precondiciones del Sistema
* El usuario inició sesión de forma exitosa (**CU-001-ADM / CU-001-CLI**).
* El usuario cuenta con el rol y los permisos pertinentes.

---

### 🔄 Flujo del Sistema

| Actor Principal (Usuario) | Actor Secundario (Sistema) |
| :--- | :--- |
| | 1) El sistema recupera la lista de usuarios y muestra los siguientes campos por registro: Item (ID), Perfil, Nombre, Teléfono, Solicitud, Completado, Cancelado, Ciudad, Portafolio, Versión del App, y Fecha de Registro. |
| 2) Visualiza la información mostrada. | |
| 3) Filtra la información mostrada, indica parámetros como: rango de fecha, ubicación y datos de la tabla. | |
| 4) Puede aprobar. | 5) Muestra mensaje de éxito. |
| 6) Puede rechazar a un usuario. | 7) Rechaza y muestra un mensaje de éxito. |
| 8) Puede eliminar un usuario. | 9) Muestra un mensaje de confirmación. |
| **Fin** | |

---

### 🔀 Flujo Alternativo del Sistema

| Acción del Usuario | Reacción del Sistema |
| :--- | :--- |
| Puede editar los datos del usuario. | Es redirigido a **CU-043-CORP-EDIT**. |
| Puede consultar el historial de operaciones del usuario. | Es redirigido a **CU-008-EST-VIAC**. |
| Puede exportar la información. | Genera un archivo en formato **.xlsx**. |
| Puede aplicar filtros sobre la información obtenida. | Refresca la tabla según los parámetros indicados. |

---

### ✅ Post-Condiciones

| Escenario de Éxito | Escenario de Fallo |
| :--- | :--- |
| Se actualizan los estados o datos de los usuarios en la base de datos según la acción realizada. | La tabla se mantiene vacía. |
| Se genera un archivo descargable si se utilizó la función de exportación. | |

---

### 🔗 Casos de Uso Relacionados
* [CU-043-CORP-EDIT](02%20Casos%20de%20uso/CU-043-CORP-EDIT.md)
* [CU-008-EST-VIAC](02%20Casos%20de%20uso/CU-008-EST-VIAC.md)
* [CU-044-CORP-SOLC](02%20Casos%20de%20uso/CU-044-CORP-SOLC.md)
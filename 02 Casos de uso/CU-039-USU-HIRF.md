## Caso de Uso: CU-039-USU-HIRF - Historial de Referencias

Este caso de uso describe la funcionalidad que permite al usuario visualizar una lista detallada de sus referidos y gestionar dicha información mediante filtros temporales para un mejor control de su red.

### 📋 Información General

| Sección | Descripción |
| :--- | :--- |
| **ID** | CU-039-USU-HIRF |
| **Caso de Uso** | Historial de Referencias |
| **Actor Principal** | Usuario |
| **Actor Secundario** | Software |
| **Objetivo** | Permite al usuario visualizar una lista detallada de sus referidos y filtrar dicha información por rangos de fechas específicos. |
| **Prioridad** | Alta |

---

### 🛠️ Precondiciones del Sistema
* El usuario inicia sesión de forma exitosa (**CU-001-ADM / CU-001-CLI**).
* El usuario cuenta con el rol y los permisos pertinentes.
* El usuario indicó que desea visualizar los datos, haciendo clic en el desplegable de opciones en **CU-036-USU-DASH**.

---

### 🔄 Flujo del Sistema

| Actor Principal (Usuario) | Actor Secundario (Sistema) |
| :--- | :--- |
| | 1) El sistema carga la tabla de referidos mostrando las columnas: Item, Nombre, Teléfono y Fecha de Creación. |
| 2) El usuario interactúa con la sección "FILTRO DE FECHA" seleccionando un rango. | 3) El sistema procesa la solicitud y refresca la tabla mostrando únicamente los registros que coinciden. |
| **Fin** | |

---

### 🔀 Flujo Alternativo del Sistema
* El usuario puede navegar a otros módulos del sistema si su rol lo permite sin aplicar filtros.

---

### ✅ Post-Condiciones

| Escenario | Resultado Esperado |
| :--- | :--- |
| **Éxito** | El usuario visualiza de manera organizada la información de contacto y fecha de registro de sus referidos filtrados. |
| **Fallo** | El sistema no muestra registros si el rango de fechas no posee datos asociados. |

---

### 🔗 Casos de Uso Relacionados
* [CU-036-USU-DASH](02%20Casos%20de%20uso/CU-036-USU-DASH.md)
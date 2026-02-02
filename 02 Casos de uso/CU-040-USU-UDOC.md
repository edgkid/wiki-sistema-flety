## Caso de Uso: CU-040-USU-UDOC - Dashboard de usuarios

Este caso de uso describe la funcionalidad que permite al usuario visualizar el estado de sus documentos legales cargados, verificar fechas de vencimiento y descargar los archivos almacenados en el servidor para asegurar la vigencia de su documentación.

### 📋 Información General

| Sección | Descripción |
| :--- | :--- |
| **ID** | CU-040-USU-UDOC |
| **Caso de Uso** | Dashboard de usuarios |
| **Actor Principal** | Usuario |
| **Actor Secundario** | Software |
| **Objetivo** | Permite al usuario visualizar el estado de sus documentos legales cargados, verificar fechas de vencimiento y descargar los archivos almacenados en el servidor. |
| **Prioridad** | Alta |

---

### 🛠️ Precondiciones del Sistema
* El usuario inicia sesión de forma exitosa (**CU-001-ADM / CU-001-CLI**).
* El usuario cuenta con el rol y los permisos pertinentes.
* El usuario indicó que desea editar los datos, haciendo clic en el desplegable de opciones en **CU-036-USU-DASH**.

---

### 🔄 Flujo del Sistema

| Actor Principal (Usuario) | Actor Secundario (Sistema) |
| :--- | :--- |
| | 1) El sistema despliega una tabla con los documentos registrados: Cédula, RIF. |
| | 2) El sistema muestra para cada registro: Fecha de Vencimiento, Código Único y el documento cargado. |
| 3) El usuario visualiza la información. | |
| 4) El usuario puede descargar cada uno de los documentos. | |
| **Fin** | |

---

### 🔀 Flujo Alternativo del Sistema
* El usuario puede interactuar con otros módulos del sistema si su rol lo permite.

---

### ✅ Post-Condiciones

| Escenario | Resultado Esperado |
| :--- | :--- |
| **Éxito** | El usuario obtiene una copia local del documento solicitado. |
| **Fallo** | El sistema no logra recuperar el archivo del servidor o la tabla se encuentra vacía. |

---

### 🔗 Casos de Uso Relacionados
* [CU-036-USU-DASH](02%20Casos%20de%20uso/CU-036-USU-DASH.md)
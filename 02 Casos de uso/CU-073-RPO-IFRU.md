# CU-073-Informe de Referencia de Usuarios

## Caso de Uso: CU-073-RPO-IFRU - Informe de Referencia de Usuarios

Este caso de uso describe la funcionalidad que permite al administrador supervisar la base de usuarios captados por la plataforma. El informe centraliza datos de contacto y métricas de actividad, facilitando el análisis del comportamiento del cliente y el volumen de uso de los servicios.

### 📋 Información General

| Sección | Descripción |
| :--- | :--- |
| **ID** | CU-073-RPO-IFRU |
| **Caso de Uso** | Informe de Referencia de Usuarios |
| **Actor Principal** | Usuario |
| **Actor Secundario** | Software |
| **Objetivo** | El sistema permite mostrar un listado detallado de los usuarios captados, identificando sus datos de contacto y el volumen de actividad (uso total) generado. |
| **Prioridad** | Media |

---

### 🛠️ Precondiciones del Sistema
* El usuario inicia sesión de forma exitosa (**CU-001-ADM / CU-001-CLI**).
* El usuario cuenta con el rol y los permisos pertinentes para acceder al módulo de reportes.

---

### 🔄 Flujo del Sistema

| Actor Principal (Usuario) | Actor Secundario (Sistema) |
| :--- | :--- |
| | 1) El sistema consulta la base de datos y presenta una tabla con: Nombre, Email, Teléfono y Uso Total. |
| 2) El usuario consulta la información detallada en el listado. | |
| 3) El usuario puede aplicar filtros de búsqueda (nombre o identificador) para segmentar los datos. | 4) El sistema procesa los filtros y actualiza la vista de resultados. |
| **Fin** | |

---


---

### ✅ Post-Condiciones

| Escenario | Resultado Esperado |
| :--- | :--- |
| **Éxito** | El sistema despliega el listado de usuarios que cumplen con los criterios de fecha y búsqueda establecidos. |
| **Fallo** | En caso de no haber coincidencias, el sistema muestra la tabla vacía con un aviso de "No se encontraron registros". |

---


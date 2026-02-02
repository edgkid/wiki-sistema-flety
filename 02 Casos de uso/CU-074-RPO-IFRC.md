## Caso de Uso: CU-074-RPO-IFRC - Informe de Referencia de Conductor

Este caso de uso describe la funcionalidad que permite al administrador supervisar el desempeño y la captación de los conductores en la plataforma. Este reporte es fundamental para identificar a los socios conductores con mayor actividad y asegurar que los datos de contacto estén centralizados para fines operativos.

### 📋 Información General

| Sección | Descripción |
| :--- | :--- |
| **ID** | CU-074-RPO-IFRC |
| **Caso de Uso** | Informe de Referencia de Conductor |
| **Actor Principal** | Usuario |
| **Actor Secundario** | Software |
| **Objetivo** | Mostrar un listado detallado de los conductores registrados, sus datos de contacto y el volumen de servicios atendidos (uso total). |
| **Prioridad** | Media |

---

### 🛠️ Precondiciones del Sistema
* El usuario inicia sesión de forma exitosa (**CU-001-ADM / CU-001-CLI**).
* El usuario cuenta con el rol y los permisos pertinentes para el módulo de reportes.

---

### 🔄 Flujo del Sistema

| Actor Principal (Usuario) | Actor Secundario (Sistema) |
| :--- | :--- |
| | 1) El sistema consulta la base de datos de conductores y presenta una tabla con: Nombre, Email, Teléfono y Uso Total. |
| 2) El usuario consulta la información detallada en el reporte. | |
| 3) El usuario aplica filtros de búsqueda por nombre o criterios específicos. | 4) El sistema procesa la solicitud y actualiza el listado en pantalla. |
| **Fin** | |

---


---

### ✅ Post-Condiciones

| Escenario | Resultado Esperado |
| :--- | :--- |
| **Éxito** | El sistema despliega el listado de conductores que cumplen con los criterios de fecha y búsqueda establecidos. |
| **Fallo** | Si no hay datos que coincidan con los filtros, el sistema muestra un estado vacío en la tabla con la leyenda "No se encontraron resultados". |

---


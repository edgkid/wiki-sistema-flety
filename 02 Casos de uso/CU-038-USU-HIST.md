## Caso de Uso: CU-038-USU-HIST - Historial de usuarios

Este caso de uso describe la funcionalidad que permite al usuario visualizar, filtrar y exportar el registro histórico de sus actividades o servicios realizados en la plataforma para un seguimiento detallado de sus transacciones.

### 📋 Información General

| Sección | Descripción |
| :--- | :--- |
| **ID** | CU-038-USU-HIST |
| **Caso de Uso** | Dashboard de usuarios |
| **Actor Principal** | Usuario |
| **Actor Secundario** | Software |
| **Objetivo** | Permite al usuario visualizar, filtrar y exportar el registro histórico de sus actividades o servicios realizados en la plataforma. |
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
| | 1) El sistema carga de forma automática una tabla con las columnas: Item, Conductor, Fecha y Hora, Estatus, Monto, Modo de Pago, Estatus de Pago. |
| 2) El usuario puede aplicar criterios de búsqueda para refinar los resultados. | |
| 3) El usuario consulta los registros cargados. | |
| **Fin** | |

---

### 🔀 Flujo Alternativo del Sistema

| Acción del Usuario | Reacción del Sistema |
| :--- | :--- |
| El usuario puede descargar la información en formato .xlsx. | El sistema genera el archivo de descarga. |
| El usuario aplica filtros que no coinciden con registros. | El sistema muestra un mensaje: "No se encontraron resultados para los criterios seleccionados". |
| El usuario puede consultar la información de la ruta en un mapa. | Redirige al usuario al caso de uso **CU-017-MAP-MAV**. |

---

### ✅ Post-Condiciones

| Escenario | Resultado Esperado |
| :--- | :--- |
| **Éxito** | El usuario visualiza o exporta su historial de actividades sin errores. |
| **Fallo** | El sistema no logra recuperar la información de la base de datos. |

---

### 🔗 Casos de Uso Relacionados
* [CU-036-USU-DASH](02%20Casos%20de%20uso/CU-036-USU-DASH.md)
* [CU-042-USU-MAP](02%20Casos%20de%20uso/CU-042-USU-MAP.md)
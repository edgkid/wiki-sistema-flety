## Caso de Uso: CU-063-SERV-CPED - Editar capacidad

Este caso de uso describe el proceso para modificar los parámetros de un registro de capacidad ya existente en el sistema, permitiendo corregir errores de entrada o actualizar las métricas de carga asignadas a la flota.

### 📋 Información General

| Sección | Descripción |
| :--- | :--- |
| **ID** | CU-063-SERV-CPED |
| **Caso de Uso** | Editar capacidad |
| **Actor Principal** | Usuario |
| **Actor Secundario** | Software |
| **Objetivo** | Permite la edición de un registro de capacidad existente para mantener actualizada la información de carga del sistema. |
| **Prioridad** | Media |

---

### 🛠️ Precondiciones del Sistema
* El usuario inicia sesión de forma exitosa (**CU-001-ADM / CU-001-CLI**).
* El usuario cuenta con el rol y los permisos pertinentes.
* El usuario seleccionó la opción de editar capacidad desde **CU-061-SERV-CAPC**.

---

### 🔄 Flujo del Sistema

| Actor Principal (Usuario) | Actor Secundario (Sistema) |
| :--- | :--- |
| | 1) El sistema carga automáticamente la información actual del registro seleccionado en el formulario. |
| 2) El usuario puede modificar el nombre identificador de la capacidad. | |
| 3) El usuario ajusta la cantidad numérica asociada a la unidad de carga. | |
| 4) El usuario puede cambiar la métrica de medida (si hubo un error en la creación original). | |
| 5) El usuario guarda los cambios. | 6) El sistema deja persistencia del registro actualizado y redirige a **CU-061-SERV-CAPC**. |
| **Fin** | |

---

### 🔀 Flujo Alternativo del Sistema
* Si el usuario cancela la edición, el sistema regresa al listado general sin aplicar cambios ni afectar las métricas actuales de los vehículos.

---

### ✅ Post-Condiciones

| Escenario | Resultado Esperado |
| :--- | :--- |
| **Éxito** | Los cambios realizados se reflejan automáticamente en cualquier módulo que haga uso del registro (Tarifas, Tipos de Camiones y Filtros de Cliente). |
| **Fallo** | El sistema muestra un error de validación y mantiene los valores previos para evitar discrepancias en los cálculos de carga activos. |

---

### 🔗 Casos de Uso Relacionados
* [CU-061-SERV-CAPC](02%20Casos%20de%20uso/CU-061-SERV-CAPC.md)
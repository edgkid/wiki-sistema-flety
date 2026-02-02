## Caso de Uso: CU-067-SERV-SERV - Servicio

Este caso de uso describe la funcionalidad que permite al administrador supervisar y organizar el catálogo de servicios ofrecidos por la plataforma (ej. Agua Potable, Flete, Mudanza). Este módulo centraliza las etiquetas de servicio que posteriormente se vinculan a los modelos de vehículos y esquemas tarifarios.

### 📋 Información General

| Sección | Descripción |
| :--- | :--- |
| **ID** | CU-067-SERV-SERV |
| **Caso de Uso** | Servicio |
| **Actor Principal** | Usuario |
| **Actor Secundario** | Software |
| **Objetivo** | Permite mostrar y gestionar un listado de servicios existentes en la plataforma. |
| **Prioridad** | Alta |

---

### 🛠️ Precondiciones del Sistema
* El usuario inicia sesión de forma exitosa (**CU-001-ADM / CU-001-CLI**).
* El usuario cuenta con el rol y los permisos pertinentes.

---

### 🔄 Flujo del Sistema

| Actor Principal (Usuario) | Actor Secundario (Sistema) |
| :--- | :--- |
| | 1) **Listado**: El sistema presenta una tabla detallada con los servicios registrados: Ítem, Nombre y Estatus. |
| 2) El usuario puede clasificar la tabla por el campo "Ítem" (ascendente/descendente). | |
| 3) El usuario puede filtrar servicios específicos por nombre o identificador. | |
| **Fin** | |

---

### 🔀 Flujo Alternativo del Sistema

| Acción del Usuario | Reacción del Sistema |
| :--- | :--- |
| El usuario desea registrar un nuevo servicio. | El sistema redirige a **CU-068-SERV-NWSE**. |
| El usuario desea editar un registro de servicio. | El sistema redirige a **CU-069-SERV-SEED**. |

---

### ✅ Post-Condiciones

| Escenario | Resultado Esperado |
| :--- | :--- |
| **Éxito (Persistencia)** | Cualquier cambio en el nombre o estado del servicio se persiste inmediatamente en la base de datos. |
| **Éxito (Operativo)** | Los servicios marcados como "Activos" se habilitan automáticamente como opciones seleccionables en la creación de "Modelos" y en la configuración de "Tarifas". |
| **Fallo** | En caso de error de red, la tabla mantiene la última versión estable de los datos. |

---

### 🔗 Casos de Uso Relacionados
* [CU-068-SERV-NWSE](02%20Casos%20de%20uso/CU-068-SERV-NWSE.md)
* [CU-069-SERV-SEED](02%20Casos%20de%20uso/CU-069-SERV-SEED.md)
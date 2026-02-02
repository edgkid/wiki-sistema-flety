## Caso de Uso: CU-070-SERVA-SERVA - Servicios Adicionales

Este caso de uso describe la gestión del catálogo de servicios complementarios de la plataforma. A diferencia de los servicios principales, estos representan valores agregados o tareas adicionales (como maniobras de carga, embalaje o seguros extra) que se pueden anexar a un servicio base.

### 📋 Información General

| Sección | Descripción |
| :--- | :--- |
| **ID** | CU-070-SERVA-SERVA |
| **Caso de Uso** | Servicios Adicionales |
| **Actor Principal** | Usuario |
| **Actor Secundario** | Software |
| **Objetivo** | Permite mostrar y gestionar un listado de servicios complementarios a los mostrados en el catálogo principal (CU-067). |
| **Prioridad** | Media |

---

### 🛠️ Precondiciones del Sistema
* El usuario inicia sesión de forma exitosa (**CU-001-ADM / CU-001-CLI**).
* El usuario cuenta con el rol y los permisos pertinentes.

---

### 🔄 Flujo del Sistema

| Actor Principal (Usuario) | Actor Secundario (Sistema) |
| :--- | :--- |
| | 1) **Listado**: El sistema presenta una tabla detallada con: Ítem, Nombre, Notas y Estatus. |
| 2) El usuario puede clasificar la tabla por el campo "Ítem" (ascendente/descendente). | |
| 3) El usuario aplica filtros para localizar servicios adicionales específicos por nombre o ID. | |
| **Fin** | |

---

### 🔀 Flujo Alternativo del Sistema

| Acción del Usuario | Reacción del Sistema |
| :--- | :--- |
| El usuario desea registrar un nuevo servicio adicional. | El sistema redirige a **CU-071-SERVA-NWSA**. |
| El usuario desea editar un registro de servicio específico. | El sistema redirige a **CU-072-SERVA-SAED**. |

---

### ✅ Post-Condiciones

| Escenario | Resultado Esperado |
| :--- | :--- |
| **Éxito (Persistencia)** | Cualquier cambio en el nombre o estado del servicio se persiste inmediatamente. |
| **Éxito (Integración)** | Los servicios "Activos" se habilitan automáticamente en los formularios de "Modelos" y en la configuración de "Tarifas" por ciudad. |
| **Fallo** | El sistema mantiene la información previa y notifica que los cambios no pudieron ser procesados. |

---

### 🔗 Casos de Uso Relacionados
* [CU-071-SERVA-NWSA](02%20Casos%20de%20uso/CU-071-SERVA-NWSA.md)
* [CU-072-SERVA-SAED](02%20Casos%20de%20uso/CU-072-SERVA-SAED.md)
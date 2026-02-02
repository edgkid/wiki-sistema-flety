## Caso de Uso: CU-034-CAM-DASH - Dashboard de camiones

Este caso de uso describe la funcionalidad que permite al usuario visualizar, filtrar y gestionar la flota de vehículos registrados en el sistema para controlar su estado operativo y asignación.

### 📋 Información General

| Sección | Descripción |
| :--- | :--- |
| **ID** | CU-034-CAM-DASH |
| **Caso de Uso** | Dashboard de camiones |
| **Actor Principal** | Usuario |
| **Actor Secundario** | Software |
| **Objetivo** | Permitir al usuario visualizar, filtrar y gestionar la flota de vehículos registrados en el sistema para controlar su estado operativo y asignación. |
| **Prioridad** | Alta |

---

### 🛠️ Precondiciones del Sistema
* El usuario inicia sesión de forma exitosa (**CU-001-ADM / CU-001-CLI**).
* El usuario cuenta con el rol y los permisos pertinentes.
* Existe información previamente cargada de camiones registrados y asociados a un conductor.

---

### 🔄 Flujo del Sistema

| Actor Principal (Usuario) | Actor Secundario (Sistema) |
| :--- | :--- |
| | 1) El sistema consulta la base de datos y presenta una tabla con los camiones registrados, mostrando: Nro, Camión (modelo), Tipo de camión, Año, Placa, Aliado, Teléfono del socio, Ciudad y Estatus. |
| 2) Puede consultar la información mostrada. | |
| 3) Puede editar la información del vehículo asociado a un conductor. | 4) Es redirigido a **CU-030-CON-EDVH**. |
| 5) Puede filtrar la información indicando parámetros de: rango de fecha, tipo de vehículo, modelo y clasificación. | |
| **Fin** | |

---

### 🔀 Flujo Alternativo del Sistema

| Actor Principal (Usuario) | Actor Secundario (Sistema) |
| :--- | :--- |
| 1) Puede inactivar un vehículo. | 2) Muestra un mensaje de inactivación exitosa. |
| 3) Puede activar un vehículo (el sistema verifica que todos los documentos estén cargados previamente). | 4) Muestra un mensaje de activación exitosa. |
| 5) Puede mover un vehículo a lista Negra. | |
| 6) Puede mover un vehículo a lista blanca. | |
| 7) Puede consultar la documentación de un vehículo en la lista. | 8) Muestra un pop-up con los documentos alusivos al vehículo seleccionado (**CU-035-CAM-DOCU**). |

---

### ✅ Post-Condiciones

| Escenario de Éxito | Escenario de Fallo |
| :--- | :--- |
| El sistema mantiene el estado de los filtros aplicados y la paginación seleccionada. | El sistema no logra actualizar el estado del vehículo o cargar la lista. |

---

### 🔗 Casos de Uso Relacionados
* [CU-035-CAM-DOCU](02%20Casos%20de%20uso/CU-035-CAM-DOCU.md)
* [CU-030-CON-EDVH](02%20Casos%20de%20uso/CU-030-CON-DCVH.md)
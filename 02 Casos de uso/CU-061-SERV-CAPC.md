## Caso de Uso: CU-061-SERV-CAPC - Capacidad

Este caso de uso describe la funcionalidad que permite gestionar las unidades de medida y los valores de capacidad (Kilogramos, Pallets, Metros Cúbicos) asignados a los vehículos. Estas capacidades son fundamentales para que el algoritmo del sistema filtre las unidades aptas según la mercancía declarada por el cliente.

### 📋 Información General

| Sección | Descripción |
| :--- | :--- |
| **ID** | CU-061-SERV-CAPC |
| **Caso de Uso** | Capacidad |
| **Actor Principal** | Usuario |
| **Actor Secundario** | Software |
| **Objetivo** | Permite gestionar las unidades de medida y los valores de capacidad que se asignan a los vehículos para el filtrado algorítmico de unidades aptas. |
| **Prioridad** | Alta |

---

### 🛠️ Precondiciones del Sistema
* El usuario inicia sesión de forma exitosa (**CU-001-ADM / CU-001-CLI**).
* El usuario cuenta con el rol y los permisos pertinentes.

---

### 🔄 Flujo del Sistema

| Actor Principal (Usuario) | Actor Secundario (Sistema) |
| :--- | :--- |
| | 1) El sistema presenta una tabla con las capacidades registradas: Capacidad, Item, Valor y Estatus. |
| 2) El usuario puede clasificar la lista por Ítem (descendente) y realizar búsquedas por nombre o valor. | |
| 3) El usuario puede cambiar el estatus de un registro (Activo/Inactivo). | 4) El sistema actualiza el estado y muestra un mensaje de éxito. |
| **Fin** | |

---

### 🔀 Flujo Alternativo del Sistema

| Acción del Usuario | Reacción del Sistema |
| :--- | :--- |
| El usuario desea editar un registro de capacidad. | El sistema redirige a **CU-063-SERV-CPED**. |
| El usuario desea crear un nuevo parámetro de capacidad. | El sistema redirige a **CU-062-SERV-NWCP**. |

---

### ✅ Post-Condiciones

| Escenario | Resultado Esperado |
| :--- | :--- |
| **Éxito (Actualización)** | El listado se actualiza reflejando los nuevos valores o cambios de estatus. |
| **Éxito (Operativo)** | Las capacidades marcadas como "Inactivas" dejan de estar disponibles al registrar o editar vehículos (Camiones). |
| **Fallo** | El sistema no procesa el cambio de estatus y mantiene la configuración previa. |

---

### 🔗 Casos de Uso Relacionados
* [CU-062-SERV-NWCP](02%20Casos%20de%20uso/CU-062-SERV-NWCP.md)
* [CU-063-SERV-CPED](02%20Casos%20de%20uso/CU-063-SERV-CPED.md)
## Caso de Uso: CU-049-SERV-TIPO - Tipo de Servicios

Este caso de uso describe la funcionalidad que permite al administrador gestionar las categorías de vehículos que definen los tipos de servicio ofrecidos por la plataforma, facilitando la organización de la flota según el modelo de negocio.

### 📋 Información General

| Sección | Descripción |
| :--- | :--- |
| **ID** | CU-049-SERV-TIPO |
| **Caso de Uso** | Tipo de Servicios |
| **Actor Principal** | Usuario |
| **Actor Secundario** | Software |
| **Objetivo** | Permitir al administrador gestionar (visualizar, buscar y modificar) las categorías de vehículos que definen los tipos de servicio ofrecidos por la plataforma. |
| **Prioridad** | Alta |

---

### 🛠️ Precondiciones del Sistema
* El usuario inicia sesión de forma exitosa (**CU-001-ADM / CU-001-CLI**).
* El usuario cuenta con el rol y los permisos pertinentes.

---

### 🔄 Flujo del Sistema

| Actor Principal (Usuario) | Actor Secundario (Sistema) |
| :--- | :--- |
| | 1) El sistema muestra todos los tipos de vehículos registrados. |
| | 2) La información es presentada en tarjetas mostrando: modelo de camión, negocio y si está seleccionado por defecto. |
| 3) El usuario visualiza la información mostrada. | |
| 4) El usuario puede usar un filtro de búsqueda. | |
| **Fin** | |

---

### 🔀 Flujo Alternativo del Sistema

| Acción del Usuario | Reacción del Sistema |
| :--- | :--- |
| El usuario puede editar la información de cada tipo de tarjeta. | El sistema redirige a **CU-050-SERV-EDIT**. |
| El usuario puede agregar un tipo de servicio nuevo. | El sistema redirige a **CU-051-SERV-NWTS**. |

---

### ✅ Post-Condiciones

| Escenario | Resultado Esperado |
| :--- | :--- |
| **Éxito** | Los datos del tipo de vehículo se actualizan correctamente en la base de datos y los cambios se reflejan inmediatamente en la interfaz. |
| **Fallo** | El sistema mantiene los datos previos y genera un log de error si la transacción fue interrumpida por validaciones de servidor o fallas de red. |

---

### 🔗 Casos de Uso Relacionados
* [CU-050-SERV-EDIT](02%20Casos%20de%20uso/CU-050-SERV-EDIT.md)
* [CU-051-SERV-NWTS](02%20Casos%20de%20uso/CU-051-SERV-NWTS.md)
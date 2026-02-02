## Caso de Uso: CU-055-SERV-CITY - Ciudades

Este caso de uso describe la funcionalidad que permite al administrador visualizar y gestionar el listado de ciudades donde la plataforma presta servicios, permitiendo un control sobre la localización y las unidades de medida por región.

### 📋 Información General

| Sección | Descripción |
| :--- | :--- |
| **ID** | CU-055-SERV-CITY |
| **Caso de Uso** | Ciudades |
| **Actor Principal** | Usuario |
| **Actor Secundario** | Software |
| **Objetivo** | Permite listar las ciudades registradas para los servicios ofrecidos en la plataforma. |
| **Prioridad** | Alta |

---

### 🛠️ Precondiciones del Sistema
* El usuario inicia sesión de forma exitosa (**CU-001-ADM / CU-001-CLI**).
* El usuario cuenta con el rol y los permisos pertinentes.

---

### 🔄 Flujo del Sistema

| Actor Principal (Usuario) | Actor Secundario (Sistema) |
| :--- | :--- |
| | 1) El sistema muestra una tabla con información de ciudades mostrando los siguientes datos: País, Ciudad, Zona Horaria y Unidad de Distancia. |
| 2) El usuario visualiza la información mostrada. | |
| 3) El usuario puede aplicar filtros sobre la información para refinar los resultados. | |
| **Fin** | |

---

### 🔀 Flujo Alternativo del Sistema

| Acción del Usuario | Reacción del Sistema |
| :--- | :--- |
| El usuario desea editar la información de una ciudad. | El sistema redirige al caso de uso **CU-056-SERV-EDCY**. |
| El usuario desea registrar una nueva ciudad. | El sistema redirige al caso de uso **CU-057-SERV-NWCY**. |

---

### ✅ Post-Condiciones

| Escenario | Resultado Esperado |
| :--- | :--- |
| **Éxito** | El estado de la ciudad (ON/OFF) y los datos editados se actualizan en tiempo real en la interfaz. |
| **Fallo** | De no existir coincidencia en los filtros o no haber datos registrados, la tabla se muestra en blanco. |

---

### 🔗 Casos de Uso Relacionados
* [CU-056-SERV-EDCY](02%20Casos%20de%20uso/CU-056-SERV-EDCY.md)
* [CU-057-SERV-NWCY](02%20Casos%20de%20uso/CU-057-SERV-NWCY.md)
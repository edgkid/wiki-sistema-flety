## Caso de Uso: CU-064-SERV-MOD - Modelo

Este caso de uso describe la funcionalidad para supervisar y gestionar los modelos estructurales de los vehículos. En este módulo se definen las categorías físicas de las unidades, permitiendo que el sistema organice la oferta de servicios basándose en la naturaleza de la carga y el diseño del transporte.

### 📋 Información General

| Sección | Descripción |
| :--- | :--- |
| **ID** | CU-064-SERV-MOD |
| **Caso de Uso** | Modelo |
| **Actor Principal** | Usuario |
| **Actor Secundario** | Software |
| **Objetivo** | Permite visualizar y gestionar los modelos estructurales de los vehículos para organizar la oferta de servicios según la naturaleza de la carga. |
| **Prioridad** | Alta |

---

### 🛠️ Precondiciones del Sistema
* El usuario inicia sesión de forma exitosa (**CU-001-ADM / CU-001-CLI**).
* El usuario cuenta con el rol y los permisos pertinentes.

---

### 🔄 Flujo del Sistema

| Actor Principal (Usuario) | Actor Secundario (Sistema) |
| :--- | :--- |
| | 1) El sistema presenta una tabla con los modelos registrados: Ítem, Nombre, Número de secuencia y Estatus. |
| 2) El usuario puede clasificar los resultados y aplicar filtros sobre los registros. | |
| 3) El usuario puede cambiar el estatus (**Activo/Inactivo**) de cada registro. | 4) El sistema procesa el cambio y muestra un mensaje con el resultado de la operación. |
| **Fin** | |

---

### 🔀 Flujo Alternativo del Sistema

| Acción del Usuario | Reacción del Sistema |
| :--- | :--- |
| El usuario desea registrar un nuevo modelo. | El sistema redirige a **CU-065-SERV-NWMO**. |
| El usuario desea editar los datos de un modelo existente. | El sistema redirige a **CU-066-SERV-MOED**. |

---

### ✅ Post-Condiciones

| Escenario | Resultado Esperado |
| :--- | :--- |
| **Éxito (Interfaz)** | La tabla actualiza y muestra en tiempo real la información de estatus del registro. |
| **Éxito (Operativo)** | Los modelos activos aparecen como opciones seleccionables en el módulo de "Camiones" y en la configuración de "Tarifas". |
| **Fallo** | Si hay un error de comunicación, el estado anterior del modelo permanece inalterado. |

---

### 🔗 Casos de Uso Relacionados
* [CU-065-SERV-NWMO](02%20Casos%20de%20uso/CU-065-SERV-NWMO.md)
* [CU-066-SERV-MOED](02%20Casos%20de%20uso/CU-066-SERV-MOED.md)
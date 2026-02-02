## Caso de Uso: CU-032-CON-FACT - Factura de viaje

Este caso de uso describe la funcionalidad que permite al administrador consultar detalladamente y descargar en formato PDF los datos de facturación de un servicio específico ya realizado por un conductor.

### 📋 Información General

| Sección | Descripción |
| :--- | :--- |
| **ID** | CU-032-CON-FACT |
| **Caso de Uso** | Factura de viaje |
| **Actor Principal** | Usuario |
| **Actor Secundario** | Software |
| **Objetivo** | Permite consultar y descargar (formato pdf) los datos de factura por viaje consultado. |
| **Prioridad** | Alta |

---

### 🛠️ Precondiciones del Sistema
* El usuario inicia sesión de forma exitosa (**CU-001-ADM / CU-001-CLI**).
* El usuario cuenta con el rol y los permisos pertinentes.
* El usuario hizo clic en editar desde **CU-024-CON-HIST**.
* Debe existir factura cargada para el viaje seleccionado.

---

### 🔄 Flujo del Sistema

| Actor Principal (Usuario) | Actor Secundario (Sistema) |
| :--- | :--- |
| | 1) El sistema carga información asociados a la factura de un viaje. |
| 2) Visualiza nombre, rif y dirección. | |
| 3) Visualiza información del conductor; documento y nombre. | |
| 4) Visualiza origen y destino de carga. | |
| 5) Visualiza información del viaje; distancia, número de caletero, tiempo total, tiempo de espera, velocidad del conductor durante el viaje. | |
| 6) Visualiza información de costos: precio base, precio sobre distancia, precio sobre tiempo, información de Fee por aumento temporal de tarifa, impuestos, propinas, peajes y la totalización del costo de la factura. | |
| **Fin** | |

---

### 🔀 Flujo Alternativo

| Actor Principal (Usuario) | Actor Secundario (Sistema) |
| :--- | :--- |
| 1) El usuario puede interactuar con otros módulos del sistema, aquellos que su rol le permita. | |
| 2) El usuario puede descargar la factura en formato PDF. | |

---

### ✅ Post-Condiciones

| Escenario | Resultado Esperado |
| :--- | :--- |
| **Éxito** | El usuario puede interactuar con otros módulos del sistema, aquellos que su rol le permita. |

---

### 🔗 Casos de Uso Relacionados
* [Conductor (CU-021)](02%20Casos%20de%20uso/CU-021-Conductor.md)
* [CU-027-CON-APRO](02%20Casos%20de%20uso/CU-027-CON-APRO.md)
* [CU-028-CON-NPRO](02%20Casos%20de%20uso/CU-028-CON-NPRO.md)
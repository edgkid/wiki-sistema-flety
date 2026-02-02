## Caso de Uso: CU-048-ALIA-BANC - Detalle de banco

Este caso de uso describe la funcionalidad que permite al administrador visualizar y gestionar la información financiera y bancaria asociada a un aliado para la gestión de pagos y transferencias.

### 📋 Información General

| Sección | Descripción |
| :--- | :--- |
| **ID** | CU-048-ALIA-BANC |
| **Caso de Uso** | Detalle de banco |
| **Actor Principal** | Usuario |
| **Actor Secundario** | Software |
| **Objetivo** | Visualizar y gestionar la información de cuentas bancarias y datos de facturación asociados al aliado. |
| **Prioridad** | Alta |

---

### 🛠️ Precondiciones del Sistema
* El usuario inicia sesión de forma exitosa (**CU-001-ADM / CU-001-CLI**).
* El usuario cuenta con el rol y los permisos pertinentes.
* El usuario hizo clic en la opción de banco desde **CU-045-ALIA-DASH**.

---

### 🔄 Flujo del Sistema

| Actor Principal (Usuario) | Actor Secundario (Sistema) |
| :--- | :--- |
| | 1) El sistema consulta la base de datos y presenta los datos bancarios: Banco, Tipo de Cuenta, Número de Cuenta, Titular y RIF/Cédula. |
| 2) El usuario consulta la información mostrada. | |
| 3) El usuario puede validar los datos para procesos administrativos. | |
| **Fin** | |

---

### 🔀 Flujo Alternativo del Sistema
* Si el aliado no posee información bancaria registrada, el sistema muestra un mensaje indicando que no hay datos disponibles.

---

### ✅ Post-Condiciones

| Escenario | Resultado Esperado |
| :--- | :--- |
| **Éxito** | El usuario visualiza la información financiera de forma clara y precisa. |
| **Fallo** | El sistema no logra recuperar los datos bancarios debido a un error de conexión. |

---

### 🔗 Casos de Uso Relacionados
* [CU-045-ALIA-DASH](02%20Casos%20de%20uso/CU-045-ALIA-DASH.md)
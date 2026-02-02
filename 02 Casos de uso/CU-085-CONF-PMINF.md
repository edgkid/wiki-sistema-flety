## Caso de Uso: CU-085-CONF-PMINF - Información Promocional Usada

### 📋 Información General

| Sección | Descripción |
| :--- | :--- |
| **id** | CU-085-CONF-PMINF |
| **Caso de Uso** | Información Promocional Usada |
| **Actor Principal** | Usuario |
| **Actores Secundarios** | Software |
| **Objetivo** | Permite detallar la información de un código promocional en específico. |
| **Prioridad** | |

---

### 🛠️ Precondiciones del Sistema
* El usuario inicia sesión de forma exitosa CU-001-ADM / CU-001-CLI.
* El usuario cuenta con el rol y los permisos pertinentes.
* El usuario hizo clic en editar promoción desde **CU-085-CONF-PMINF**.

---

### 🔄 Flujo del Sistema

| Actor principal (usuario) | Actor Secundario (sistema) |
| :--- | :--- |
| | El sistema carga el detalle de la información promocional de un código promocional. |
| El usuario puede visualizar los datos principales del código promocional: código, tipo, valor, país y cantidad de usos. | |
| El usuario puede visualizar el detalle de consumo del código promocional seleccionado: Id del viaje, fecha, nombre, id del usuario, email, método de pago, tarifa del servicio, total y monto de la promoción. | |
| **Fin** | |

---

### 🔀 Flujo alternativo del sistema

| Acción del Usuario | Reacción del Sistema |
| :--- | :--- |
| El usuario puede regresar a la vista principal de códigos promocionales. | El sistema redirige a **CU-082-CONF-PRMO**. |

---

### ✅ Post Condición del sistema

| Escenario | Resultado |
| :--- | :--- |
| **Éxito** | |
| **Fallo** | |

---

### 🔗 CU - Relacionado
* [CU-082-CONF-PRMO](02%20Casos%20de%20uso/CU-082-CONF-PRMO.md)
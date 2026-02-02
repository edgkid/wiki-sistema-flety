## Caso de Uso: CU-046-ALIA-DETA - Detalle de aliado

Este caso de uso describe la funcionalidad que permite al administrador visualizar y editar la información detallada de un aliado específico registrado en la plataforma, asegurando la actualización de sus datos de contacto y corporativos.

### 📋 Información General

| Sección | Descripción |
| :--- | :--- |
| **ID** | CU-046-ALIA-DETA |
| **Caso de Uso** | Detalle de aliado |
| **Actor Principal** | Usuario |
| **Actor Secundario** | Software |
| **Objetivo** | Permite al administrador visualizar la información detallada de un usuario. |
| **Prioridad** | Alta |

---

### 🛠️ Precondiciones del Sistema
* El usuario inicia sesión de forma exitosa (**CU-001-ADM / CU-001-CLI**).
* El usuario cuenta con el rol y los permisos pertinentes.
* El usuario hizo clic en "ver detalle" desde **CU-045-ALIA-DASH**.

---

### 🔄 Flujo del Sistema

| Actor Principal (Usuario) | Actor Secundario (Sistema) |
| :--- | :--- |
| | 1) El sistema carga la información del aliado: nombre, apellido, teléfono, dirección, email, compañía e imagen. |
| 2) El usuario puede editar los datos mostrados. | |
| 3) El usuario guarda los cambios. | 4) El sistema deja la persistencia en caso exitoso y redirige a **CU-045-ALIA-DASH**. |
| **Fin** | |

---

### 🔀 Flujo Alternativo del Sistema
* El usuario puede cancelar la edición y regresar al dashboard sin guardar cambios.

---

### ✅ Post-Condiciones

| Escenario | Resultado Esperado |
| :--- | :--- |
| **Éxito** | Se persisten los cambios realizados por el usuario en la base de datos. |
| **Fallo** | El sistema muestra un mensaje indicando que falló la operación y no queda persistencia de los cambios. |

---

### 🔗 Casos de Uso Relacionados
* [CU-008-EST-VIAC](02%20Casos%20de%20uso/CU-008-EST-VIAC.md)
* [CU-034-Camiones](CU-034-Camiones.md)
* [CU-047-ALIA-COND](02%20Casos%20de%20uso/CU-047-ALIA-COND.md)
* [CU-048-ALIA-BANC](02%20Casos%20de%20uso/CU-048-ALIA-BANC.md)
* [CU-045-ALIA-DASH](02%20Casos%20de%20uso/CU-045-ALIA-DASH.md)
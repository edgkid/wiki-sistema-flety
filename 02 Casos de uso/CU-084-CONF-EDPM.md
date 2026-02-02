## Caso de Uso: CU-084-CONF-EDPM - Editar Promoción

### 📋 Información General

| Sección | Descripción |
| :--- | :--- |
| **id** | CU-084-CONF-EDPM |
| **Caso de Uso** | Editar Promoción |
| **Actor Principal** | Usuario |
| **Actores Secundarios** | Software |
| **Objetivo** | Permite la edición de los datos de un código promocional. |
| **Prioridad** | |

---

### 🛠️ Precondiciones del Sistema
* El usuario inicia sesión de forma exitosa CU-001-ADM / CU-001-CLI.
* El usuario cuenta con el rol y los permisos pertinentes.
* El usuario hizo clic en editar promoción desde **CU-082-CONF-PRMO**.

---

### 🔄 Flujo del Sistema

| Actor principal (usuario) | Actor Secundario (sistema) |
| :--- | :--- |
| | El sistema muestra un formulario con los datos precargados y que se requieren para crear un código nuevo promocional. |
| El usuario indica los nuevos datos de código promocional: código, valor, tipo, número de usos por usuarios, país, ciudad, servicio, fecha a partir de la cual se activa el código promocional, fecha de caducidad y números de viajes. | |
| El usuario indica que desea guardar los datos indicados. | |
| | El sistema deja persistencia de los datos actualizados. |
| | El sistema redirige a **CU-082-CONF-PRMO**. |
| **Fin** | |

---

### 🔀 Flujo alternativo del sistema
N/A

---

### ✅ Post Condición del sistema

| Escenario | Resultado |
| :--- | :--- |
| **Éxito** | El nuevo código promocional queda activo y disponible para los usuarios según los parámetros indicados. |
| **Fallo** | |

---

### 🔗 CU - Relacionado
* [CU-082-CONF-PRMO](02%20Casos%20de%20uso/CU-082-CONF-PRMO.md)
* [CU-083-CONF-NWPM](02%20Casos%20de%20uso/CU-083-CONF-NWPM.md)
* [CU-085-CONF-PMINF](02%20Casos%20de%20uso/CU-085-CONF-PMINF.md)
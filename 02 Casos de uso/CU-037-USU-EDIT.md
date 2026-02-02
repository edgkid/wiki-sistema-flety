## Caso de Uso: CU-037-USU-EDIT - Editar datos de usuario

Este caso de uso describe el proceso mediante el cual un usuario administrativo puede modificar la información personal, datos de contacto y fotografía de un perfil de usuario registrado en la plataforma.

### 📋 Información General

| Sección | Descripción |
| :--- | :--- |
| **ID** | CU-037-USU-EDIT |
| **Caso de Uso** | Editar datos de usuario |
| **Actor Principal** | Usuario |
| **Actor Secundario** | Software |
| **Objetivo** | Permite al usuario autenticado modificar su información personal, datos de contacto y fotografía dentro de la plataforma. |
| **Prioridad** | Alta |

---

### 🛠️ Precondiciones del Sistema
* El usuario inicia sesión de forma exitosa (**CU-001-ADM / CU-001-CLI**).
* El usuario cuenta con el rol y los permisos pertinentes.
* El usuario indicó que desea editar los datos, haciendo clic en el desplegable de opciones en **CU-036-USU-DASH**.

---

### 🔄 Flujo del Sistema

| Actor Principal (Usuario) | Actor Secundario (Sistema) |
| :--- | :--- |
| | 1) El sistema consulta la base de datos y despliega el formulario con la información actual: Nombre, Apellido, Email, Teléfono (Código de país y número), Dirección y País. |
| 2) El usuario realiza los cambios deseados. | |
| 3) El usuario hace clic en "Cambiar foto" para cargar un nuevo archivo de imagen. | |
| 4) El usuario presiona el botón de guardar. | 5) El sistema valida el formato de los datos, actualiza el registro en la base de datos, muestra un mensaje de éxito y redirige a **CU-036-USU-DASH**. |
| **Fin** | |

---

### 🔀 Flujo Alternativo del Sistema
* El usuario puede cancelar la operación en cualquier momento antes de guardar, manteniendo la información original sin cambios.

---

### ✅ Post-Condiciones

| Escenario | Resultado Esperado |
| :--- | :--- |
| **Éxito** | Se guarda la actualización del registro, se muestra un mensaje de éxito y el usuario es redirigido a **CU-036-USU-DASH**. |
| **Fallo** | Los datos no logran ser procesados y se muestra un mensaje de error. |

---

### 🔗 Casos de Uso Relacionados
* [CU-036-USU-DASH](02%20Casos%20de%20uso/CU-036-USU-DASH.md)
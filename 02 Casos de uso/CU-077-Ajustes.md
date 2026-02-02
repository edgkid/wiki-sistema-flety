## Caso de Uso: CU-077-CONF-IDM - Idiomas

### 📋 Información General

| Sección | Descripción |
| :--- | :--- |
| **id** | CU-077-CONF-IDM |
| **Caso de Uso** | Idiomas |
| **Actor Principal** | Usuario |
| **Actores Secundarios** | Software |
| **Objetivo** | Permite gestionar (listar, agregar y acceder a la edición) los idiomas disponibles en el sistema. |
| **Prioridad** | |

---

### 🛠️ Precondiciones del Sistema
* El usuario inicia sesión de forma exitosa CU-001-ADM / CU-001-CLI
* El usuario cuenta con el rol y los permisos pertinentes

---

### 🔄 Flujo del Sistema

| Actor principal (usuario) | Actor Secundario (sistema) |
| :--- | :--- |
| | El sistema muestra la lista de idiomas actuales (Nombre y Código) y un formulario de alta en la parte superior. |
| El usuario ingresa el Nombre del idioma (ej. "Francés"). | |
| El usuario ingresa el Código ISO del idioma (ej. "FR"). | |
| El usuario hace clic en el botón "Agregar idioma". | |
| | El sistema valida los datos, guarda el nuevo registro y actualiza la tabla de resultados. |
| | El sistema deja persistencia del nuevo registro. |
| El usuario consulta la lista de idiomas disponible en el sistema. | |
| **Fin** | |

---

### 🔀 Flujo alternativo del sistema

| Acción del Usuario | Reacción del Sistema |
| :--- | :--- |
| El usuario puede editar el detalle Nombre de idioma codigo. | El sistema carga los datos del idioma seleccionado en el formulario superior. |
| El usuario ingresa los nuevos datos y presiona guardar. | El sistema deja persistencia del nuevo registro. |
| **Fin** | |

---

### ✅ Post Condición del sistema

| Escenario | Resultado |
| :--- | :--- |
| **Éxito** | Se registra un nuevo idioma en la base de datos o se redirige al usuario a la vista de edición de un idioma existente. |
| **Fallo** | |

---


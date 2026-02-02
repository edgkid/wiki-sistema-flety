## Caso de Uso: CU-068-SERV-NWSE - Nuevo Servicio

Este caso de uso describe el proceso para dar de alta una nueva categoría de servicio en la plataforma. Al definir el nombre y la naturaleza logística (courier y distribución), se sientan las bases para la posterior asignación de vehículos y el cálculo de costos para el cliente final.

### 📋 Información General

| Sección | Descripción |
| :--- | :--- |
| **ID** | CU-068-SERV-NWSE |
| **Caso de Uso** | Nuevo Servicio |
| **Actor Principal** | Usuario |
| **Actor Secundario** | Software |
| **Objetivo** | Permite crear un nuevo registro de servicio definiendo su naturaleza logística. |
| **Prioridad** | Alta |

---

### 🛠️ Precondiciones del Sistema
* El usuario inicia sesión de forma exitosa (**CU-001-ADM / CU-001-CLI**).
* El usuario cuenta con el rol y los permisos pertinentes.
* El usuario seleccionó la opción de agregar nuevo servicio desde **CU-067-SERV-SERV**.

---

### 🔄 Flujo del Sistema

| Actor Principal (Usuario) | Actor Secundario (Sistema) |
| :--- | :--- |
| | 1) El sistema entrega un formulario de registro en blanco. |
| 2) El usuario carga la información de: **Nombre de servicio**, **Tipo de courier** y **Distribución de carga**. | |
| 3) El usuario solicita guardar la información. | 4) El sistema deja persistencia de los datos en la base de datos central. |
| | 5) El sistema redirige automáticamente a **CU-067-SERV-SERV**. |
| **Fin** | |

---

### 📦 Atributos del Servicio
* **Tipo de Courier**: Define si el servicio es para mensajería ligera o paquetería estándar.
* **Distribución de Carga**: Especifica la modalidad de reparto (ej. última milla, carga pesada, etc.).



---

### ✅ Post-Condiciones

| Escenario | Resultado Esperado |
| :--- | :--- |
| **Éxito (Administrativo)** | El nuevo servicio aparece en el listado maestro y queda habilitado para ser vinculado a "Modelos" de camiones y para la creación de "Tarifas" por ciudad. |
| **Éxito (Operativo)** | Una vez activo y tarifado, el servicio se vuelve visible para los usuarios finales en la aplicación móvil. |
| **Fallo** | El sistema impide el guardado si hay duplicidad de nombres o campos vacíos, notificando al usuario para su corrección. |

---

### 🔗 Casos de Uso Relacionados
* [CU-067-SERV-SERV](02%20Casos%20de%20uso/CU-067-SERV-SERV.md)
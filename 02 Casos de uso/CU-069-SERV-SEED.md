## Caso de Uso: CU-069-SERV-SEED - Edición de Servicio

Este caso de uso describe el proceso para modificar los atributos de un servicio existente. Permite ajustar el nombre comercial y la naturaleza logística (courier y distribución), asegurando que los cambios se propaguen a los modelos de transporte y tarifas asociadas.

### 📋 Información General

| Sección | Descripción |
| :--- | :--- |
| **ID** | CU-069-SERV-SEED |
| **Caso de Uso** | Edición de Servicio |
| **Actor Principal** | Usuario |
| **Actor Secundario** | Software |
| **Objetivo** | Permite editar los datos de un registro de servicio existente para mantener actualizada la oferta logística. |
| **Prioridad** | Media |

---

### 🛠️ Precondiciones del Sistema
* El usuario inicia sesión de forma exitosa (**CU-001-ADM / CU-001-CLI**).
* El usuario cuenta con el rol y los permisos pertinentes.
* El usuario seleccionó la opción de editar servicio desde **CU-067-SERV-SERV**.

---

### 🔄 Flujo del Sistema

| Actor Principal (Usuario) | Actor Secundario (Sistema) |
| :--- | :--- |
| | 1) El sistema entrega un formulario precargado con los datos del registro de servicio seleccionado. |
| 2) El usuario actualiza la información: **Nombre de servicio**, **Tipo de courier** y **Distribución de carga**. | |
| 3) El usuario solicita guardar la información modificada. | 4) El sistema deja persistencia de los nuevos datos en la base de datos central. |
| | 5) El sistema redirige automáticamente a **CU-067-SERV-SERV**. |
| **Fin** | |

---

### 🔀 Flujo Alternativo del Sistema
* Si el usuario decide cancelar la edición antes de guardar, el sistema regresa al listado general sin alterar la configuración previa del servicio.

---

### ✅ Post-Condiciones

| Escenario | Resultado Esperado |
| :--- | :--- |
| **Éxito (Administrativo)** | Los cambios aparecen en el listado maestro y se mantienen los vínculos con los "Modelos" de camiones y "Tarifas" por ciudad. |
| **Éxito (Operativo)** | La actualización es visible para los usuarios finales en la aplicación de forma inmediata tras la persistencia. |
| **Fallo** | Si ocurre un error de transacción, los parámetros anteriores del servicio permanecen intactos para evitar interrupciones operativas. |

---

### 🔗 Casos de Uso Relacionados
* [CU-067-SERV-SERV](02%20Casos%20de%20uso/CU-067-SERV-SERV.md)
## Caso de Uso: CU-072-SERVA-SAED - Editar Servicio Adicional

Este caso de uso describe el proceso para modificar la información de un servicio complementario ya existente. Permite actualizar el nombre comercial y las especificaciones técnicas (notas), asegurando que la oferta de servicios adicionales se mantenga alineada con las necesidades operativas de la plataforma.

### 📋 Información General

| Sección | Descripción |
| :--- | :--- |
| **ID** | CU-072-SERVA-SAED |
| **Caso de Uso** | Editar Servicio Adicional |
| **Actor Principal** | Usuario |
| **Actor Secundario** | Software |
| **Objetivo** | Permite editar los datos de un registro de servicio complementario específico. |
| **Prioridad** | Media |

---

### 🛠️ Precondiciones del Sistema
* El usuario inicia sesión de forma exitosa (**CU-001-ADM / CU-001-CLI**).
* El usuario cuenta con el rol y los permisos pertinentes.
* El usuario seleccionó la opción de editar servicio desde **CU-070-SERVA-SERVA**.

---

### 🔄 Flujo del Sistema

| Actor Principal (Usuario) | Actor Secundario (Sistema) |
| :--- | :--- |
| | 1) El sistema entrega un formulario con los datos precargados del servicio seleccionado. |
| 2) El usuario actualiza la información del **Nombre de servicio** y las **Notas** descriptivas. | |
| 3) El usuario solicita guardar los cambios realizados. | 4) El sistema deja persistencia de los nuevos datos en la base de datos central. |
| | 5) El sistema redirige automáticamente al listado maestro **CU-070-SERVA-SERVA**. |
| **Fin** | |

---

### 🔀 Flujo Alternativo del Sistema
* Si el usuario cancela la operación, el sistema regresa al listado general sin aplicar cambios, manteniendo la integridad de la configuración previa.

---

### ✅ Post-Condiciones

| Escenario | Resultado Esperado |
| :--- | :--- |
| **Éxito (Administrativo)** | Los datos actualizados aparecen en el listado maestro y mantienen su vinculación con "Modelos" y "Tarifas" por ciudad. |
| **Éxito (Operativo)** | Una vez persistido y tarifado, el servicio actualizado se vuelve visible para los usuarios finales en la aplicación. |
| **Fallo** | En caso de error de sistema, los datos no se sobrescriben y se notifica al usuario para reintentar la operación. |

---

### 🔗 Casos de Uso Relacionados
* [CU-070-SERVA-SERVA](02%20Casos%20de%20uso/CU-070-SERVA-SERVA.md)
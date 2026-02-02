## Caso de Uso: CU-066-SERV-MOED - Editar Modelo

Este caso de uso describe el proceso para modificar la información técnica e imágenes de un modelo de vehículo ya existente en la plataforma, asegurando que la representación visual y operativa de la flota se mantenga actualizada.

### 📋 Información General

| Sección | Descripción |
| :--- | :--- |
| **ID** | CU-066-SERV-MOED |
| **Caso de Uso** | Editar Modelo |
| **Actor Principal** | Usuario |
| **Actor Secundario** | Software |
| **Objetivo** | Permite editar los datos de modelo registrados para mantener actualizada la oferta visual y operativa. |
| **Prioridad** | Media |

---

### 🛠️ Precondiciones del Sistema
* El usuario inicia sesión de forma exitosa (**CU-001-ADM / CU-001-CLI**).
* El usuario cuenta con el rol y los permisos pertinentes.
* El usuario seleccionó la opción de editar modelo desde **CU-064-SERV-MOD**.

---

### 🔄 Flujo del Sistema

| Actor Principal (Usuario) | Actor Secundario (Sistema) |
| :--- | :--- |
| | 1) El sistema redirige al formulario de edición y precarga los datos actuales del modelo seleccionado. |
| 2) El usuario edita los datos del registro (nombre, secuencia, categoría) e imagen asociada. | |
| 3) El usuario hace clic en el botón de guardar. | 4) El sistema deja persistencia de los datos actualizados y redirige a **CU-064-SERV-MOD**. |
| **Fin** | |

---

### 🔀 Flujo Alternativo del Sistema
* Si el usuario decide cancelar la edición, el sistema descarta los cambios y regresa al listado general sin afectar los registros vigentes.

---

### ✅ Post-Condiciones

| Escenario | Resultado Esperado |
| :--- | :--- |
| **Éxito (Visual)** | Los datos editados del modelo aparecen inmediatamente en el tablero principal de modelos. |
| **Éxito (Operativo)** | La nueva configuración queda disponible para ser enlazada en el módulo de "Camiones" y para la creación de nuevas "Tarifas" por ciudad. |
| **Fallo** | El sistema muestra un mensaje de error si el formato de imagen no es válido o si faltan campos obligatorios; la configuración anterior persiste. |

---

### 🔗 Casos de Uso Relacionados
* [CU-064-SERV-MOD](02%20Casos%20de%20uso/CU-064-SERV-MOD.md)
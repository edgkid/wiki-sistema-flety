## Caso de Uso: CU-071-SERVA-NWSA - Nuevo Servicio Adicional

Este caso de uso describe el proceso para dar de alta servicios complementarios o de valor agregado en la plataforma. Estos registros permiten extender la oferta comercial más allá del transporte base, incluyendo conceptos como maniobras, seguros específicos o servicios de ayudantes.

### 📋 Información General

| Sección | Descripción |
| :--- | :--- |
| **ID** | CU-071-SERVA-NWSA |
| **Caso de Uso** | Nuevo Servicio Adicional |
| **Actor Principal** | Usuario |
| **Actor Secundario** | Software |
| **Objetivo** | Permite crear un nuevo registro de servicio complementario en el sistema. |
| **Prioridad** | Media |

---

### 🛠️ Precondiciones del Sistema
* El usuario inicia sesión de forma exitosa (**CU-001-ADM / CU-001-CLI**).
* El usuario cuenta con el rol y los permisos pertinentes.
* El usuario seleccionó la opción de agregar nuevo servicio desde **CU-070-SERVA-SERVA**.

---

### 🔄 Flujo del Sistema

| Actor Principal (Usuario) | Actor Secundario (Sistema) |
| :--- | :--- |
| | 1) El sistema entrega un formulario de registro en blanco para el servicio adicional. |
| 2) El usuario carga la información del **Nombre de servicio** y las **Notas** descriptivas. | |
| 3) El usuario solicita guardar la información. | 4) El sistema deja persistencia de los datos en la base de datos. |
| | 5) El sistema redirige automáticamente a **CU-070-SERVA-SERVA**. |
| **Fin** | |

---

### 📝 Notas y Observaciones
* **Descripción del Servicio**: Las notas cargadas sirven de guía interna o informativa para detallar en qué consiste el cargo adicional.
* **Disponibilidad**: Al crearse, el registro queda disponible para su posterior activación y tarifado por región.

---

### ✅ Post-Condiciones

| Escenario | Resultado Esperado |
| :--- | :--- |
| **Éxito (Administrativo)** | El nuevo servicio aparece en el listado maestro y queda habilitado para ser vinculado a "Modelos" y para la creación de "Tarifas" por ciudad. |
| **Éxito (Operativo)** | Una vez activo y tarifado, el servicio se vuelve visible y seleccionable para los usuarios finales en la aplicación. |
| **Fallo** | El sistema no guarda el registro y notifica si faltan datos obligatorios, manteniendo al usuario en el formulario. |

---

### 🔗 Casos de Uso Relacionados
* [CU-070-SERVA-SERVA](02%20Casos%20de%20uso/CU-070-SERVA-SERVA.md)
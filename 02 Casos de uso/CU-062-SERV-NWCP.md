## Caso de Uso: CU-062-SERV-NWCP - Nueva capacidad

Este caso de uso describe el proceso para definir y registrar nuevos límites de carga en el sistema. Estos parámetros son esenciales para categorizar la flota y asegurar que el algoritmo de asignación vincule correctamente los vehículos con los requerimientos de carga del cliente.

### 📋 Información General

| Sección | Descripción |
| :--- | :--- |
| **ID** | CU-062-SERV-NWCP |
| **Caso de Uso** | Nueva capacidad |
| **Actor Principal** | Usuario |
| **Actor Secundario** | Software |
| **Objetivo** | Permite definir los límites de carga que podrán ser asignados a los distintos tipos de vehículos en el sistema. |
| **Prioridad** | Alta |

---

### 🛠️ Precondiciones del Sistema
* El usuario inicia sesión de forma exitosa (**CU-001-ADM / CU-001-CLI**).
* El usuario cuenta con el rol y los permisos pertinentes.
* El usuario seleccionó la opción de agregar/nueva capacidad desde **CU-061-SERV-CAPC**.

---

### 🔄 Flujo del Sistema

| Actor Principal (Usuario) | Actor Secundario (Sistema) |
| :--- | :--- |
| | 1) El sistema despliega el formulario de registro en blanco. |
| 2) El usuario define el **Nombre de capacidad** (etiqueta descriptiva para identificarla en otros módulos). | |
| 3) El usuario indica la **Cantidad numérica máxima** permitida para este tipo de capacidad. | |
| 4) Se indica la **Unidad de medida** (peso/volumen) que soportará la nueva capacidad. | |
| 5) El usuario solicita guardar los cambios del nuevo registro. | 6) El sistema valida los campos, deja persistencia del nuevo registro y redirige a **CU-061-SERV-CAPC**. |
| **Fin** | |

---

### ⚙️ Parámetros de Registro
* **Etiqueta Identificadora**: Nombre que aparecerá en los selectores de "Tipos de Camiones" y "Tarifas".
* **Valor Numérico**: Valor entero o decimal que representa el límite físico.
* **Unidad Logística**: Vinculación con estándares como Kg, Lbs, Ton, Pallets o $m^3$.



---

### ✅ Post-Condiciones

| Escenario | Resultado Esperado |
| :--- | :--- |
| **Éxito (Registro)** | El sistema redirige automáticamente al listado de capacidades donde se visualiza el nuevo registro con estado "Activo" por defecto. |
| **Éxito (Integración)** | El nuevo tipo de capacidad queda disponible para ser seleccionado en la configuración de tarifas y tipos de camiones. |
| **Fallo** | El sistema muestra alertas de validación y no permite guardar el registro hasta que los datos sean consistentes. |

---

### 🔗 Casos de Uso Relacionados
* [CU-061-SERV-CAPC](02%20Casos%20de%20uso/CU-061-SERV-CAPC.md)
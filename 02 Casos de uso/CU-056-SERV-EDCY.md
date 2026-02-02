## Caso de Uso: CU-056-SERV-EDCY - Editar datos de ciudad

Este caso de uso describe el proceso para modificar los parámetros operativos de una ciudad específica, incluyendo su estado de servicio, zona horaria y unidades de medida.

### 📋 Información General

| Sección | Descripción |
| :--- | :--- |
| **ID** | CU-056-SERV-EDCY |
| **Caso de Uso** | Editar datos de ciudad |
| **Actor Principal** | Usuario |
| **Actor Secundario** | Software |
| **Objetivo** | Permitir la modificación de los parámetros de configuración y el estado operativo de una ciudad registrada en el sistema. |
| **Prioridad** | Alta |

---

### 🛠️ Precondiciones del Sistema
* El usuario inicia sesión de forma exitosa (**CU-001-ADM / CU-001-CLI**).
* El usuario cuenta con el rol y los permisos pertinentes.
* El usuario seleccionó la opción de editar ciudad desde **CU-055-SERV-CITY**.

---

### 🔄 Flujo del Sistema

| Actor Principal (Usuario) | Actor Secundario (Sistema) |
| :--- | :--- |
| | 1) El sistema recupera los datos actuales de la ciudad: País asociado, Nombre, Zona Horaria y Unidad de Distancia (Km/Millas). |
| 2) El usuario modifica el estado de la ciudad (ON/OFF) mediante el interruptor de negocio. | |
| 3) El usuario ajusta los campos permitidos como la Zona Horaria o la Unidad de Medida. | |
| 4) El usuario presiona el botón "Guardar". | 5) El sistema valida los datos, guarda los cambios en la base de datos y redirige a **CU-055-SERV-CITY**. |
| **Fin** | |

---

### 🔀 Flujo Alternativo del Sistema
* El usuario puede cancelar la operación en cualquier momento, regresando al dashboard de ciudades sin aplicar cambios.

---

### ✅ Post-Condiciones

| Escenario | Resultado Esperado |
| :--- | :--- |
| **Éxito** | Los cambios se ven reflejados inmediatamente en la configuración regional de la ciudad para todos los servicios activos. |
| **Fallo** | Si ocurre un error de conexión, se muestra un mensaje de advertencia y los datos permanecen sin cambios. |

---

### 🔗 Casos de Uso Relacionados
* [CU-055-SERV-CITY](02%20Casos%20de%20uso/CU-055-SERV-CITY.md)
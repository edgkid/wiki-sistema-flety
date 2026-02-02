## Caso de Uso: CU-060-SERV-NWTA - Creación de tarifas

Este caso de uso describe el proceso para dar de alta una nueva estructura de costos en el sistema. El administrador define desde los precios base y beneficios del conductor hasta parámetros fiscales y multiplicadores por alta demanda u horarios especiales.

### 📋 Información General

| Sección | Descripción |
| :--- | :--- |
| **ID** | CU-060-SERV-NWTA |
| **Caso de Uso** | Creación de tarifas |
| **Actor Principal** | Usuario |
| **Actor Secundario** | Software |
| **Objetivo** | Permite al administrador dar de alta una nueva estructura de costos para un tipo de vehículo en una ciudad específica. |
| **Prioridad** | Alta |

---

### 🛠️ Precondiciones del Sistema
* El usuario inicia sesión de forma exitosa (**CU-001-ADM / CU-001-CLI**).
* El usuario cuenta con el rol y los permisos pertinentes.
* El usuario seleccionó la opción de agregar tarifa desde **CU-058-SERV-TARF**.

---

### 🔄 Flujo del Sistema

| Actor Principal (Usuario) | Actor Secundario (Sistema) |
| :--- | :--- |
| 1) **Definición de Identidad**: Selecciona el País, la Ciudad, el Tipo de precio y el Tipo de vehículo. | |
| 2) **Configuración de Costos Base**: Ingresa el Beneficio del conductor, Tarifa mínima, Precio base, y precios por unidad de distancia/tiempo. | |
| 3) **Parámetros Fiscales y Operativos**: Ingresa Impuestos, Tarifas misceláneas, Costo del seguro, Precio de cancelación y Paradas gratuitas. | |
| 4) **Configuración de Aumentos Temporales**: Activa el switch de "Horario de aumento", selecciona días y define el multiplicador (ej. 1.5x). | |
| 5) Presiona el botón "Enviar". | 6) El sistema deja persistencia de la nueva tarifa y redirige a **CU-058-SERV-TARF**. |
| **Fin** | |

---

### ⚙️ Componentes de la Tarifa
* **Métricas de Cálculo**: Basadas en la combinación de distancia recorrida y tiempo de servicio (minutos).
* **Gestión de Impuestos**: Desglose de cargas fiscales tanto para el cliente final como para el prestador del servicio.
* **Tarifa Dinámica**: Capacidad de programar bloques horarios con multiplicadores específicos para optimizar la oferta y demanda.

---

### ✅ Post-Condiciones

| Escenario | Resultado Esperado |
| :--- | :--- |
| **Éxito (Registro)** | Se crea un nuevo registro en el listado maestro de tarifas. |
| **Éxito (Expansión)** | El sistema habilita automáticamente las pestañas de "Tarifa camiones" y "Precio zona a zona" para esta ciudad tras el guardado. |
| **Fallo** | El sistema notifica errores de validación (campos obligatorios) y no permite la creación del registro. |

---

### 🔗 Casos de Uso Relacionados
* [CU-058-SERV-TARF](02%20Casos%20de%20uso/CU-058-SERV-TARF.md)
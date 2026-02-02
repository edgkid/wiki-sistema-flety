## Caso de Uso: CU-059-SERV-TAED - Edición y configuración de tarifas

Este caso de uso describe el proceso detallado para que el administrador modifique los parámetros financieros y logísticos de una tarifa. La interfaz está diseñada mediante pestañas funcionales para gestionar de forma granular costos base, seguros, precios por zona y esquemas de alquiler.

### 📋 Información General

| Sección | Descripción |
| :--- | :--- |
| **ID** | CU-059-SERV-TAED |
| **Caso de Uso** | Edición y configuración de tarifas por ciudad |
| **Actor Principal** | Usuario |
| **Actor Secundario** | Software |
| **Objetivo** | Permite al administrador modificar los parámetros financieros y logísticos de una tarifa existente segmentada en pestañas funcionales. |
| **Prioridad** | Alta |

---

### 🛠️ Precondiciones del Sistema
* El usuario inicia sesión de forma exitosa (**CU-001-ADM / CU-001-CLI**).
* El usuario cuenta con el rol y los permisos pertinentes.
* El usuario seleccionó la opción de editar tarifa desde **CU-058-SERV-TARF**.

---

### 🔄 Flujo del Sistema (Configuración por Pestañas)

| Actor Principal (Usuario) | Actor Secundario (Sistema) |
| :--- | :--- |
| | 1) El sistema despliega una interfaz con múltiples pestañas de configuración técnica. |
| **Pestaña: General/Ciudad** | |
| 2) El usuario edita valores críticos: Beneficio del conductor, Tarifa mínima, Costo del seguro y Paradas gratuitas. | 3) El sistema muestra los datos fijos (País, Ciudad, Tipo) y guarda la persistencia de impuestos. |
| **Pestaña: Precio por Zona** | |
| 4) Ingresa costos por zona para: Pernoctar, Ayudante, Modelo de camión y Paradas adicionales. | 5) El sistema deja persistencia de la configuración de tarifas por zonas geográficas. |
| **Pestaña: Origen/Destino** | |
| 6) Configura precios específicos para trayectos Aeropuerto-Ciudad y Ciudad-Ciudad. | 7) El sistema facilita selectores independientes para ambos tipos de trayecto. |
| **Pestaña: Alquileres** | |
| 8) Configura el precio de alquiler de camiones y tarifas por vehículo mediante la creación de paquetes. | |
| **Fin** | |

---

### ⚙️ Segmentación de Costos
* **Logística Base**: Gestión de paradas gratuitas y seguros obligatorios por viaje.
* **Matriz de Zonas**: Diferenciación de precios según la peligrosidad o distancia de la zona.
* **Paquetes de Alquiler**: Estructura de cobro por tiempo o disponibilidad de flota.

---

### ✅ Post-Condiciones

| Escenario | Resultado Esperado |
| :--- | :--- |
| **Éxito** | Los nuevos valores de la matriz de precios se aplican instantáneamente a las cotizaciones de nuevos servicios realizados por los clientes. |
| **Fallo** | El sistema impide el guardado si hay campos vacíos obligatorios; las tarifas vigentes no se alteran. |

---

### 🔗 Casos de Uso Relacionados
* [CU-058-SERV-TARF](02%20Casos%20de%20uso/CU-058-SERV-TARF.md)
## Caso de Uso: CU-080-CONF-BSIC - Ajustes Básicos

### 📋 Información General

| Sección | Descripción |
| :--- | :--- |
| **id** | CU-080-CONF-BSIC |
| **Caso de Uso** | Ajustes básicos |
| **Actor Principal** | Usuario |
| **Actores Secundarios** | Software |
| **Objetivo** | Configurar y actualizar los parámetros globales que rigen el comportamiento de la aplicación móvil y la consola administrativa. |
| **Prioridad** | |

---

### 🛠️ Precondiciones del Sistema
* El usuario inicia sesión de forma exitosa CU-001-ADM / CU-001-CLI
* El usuario cuenta con el rol y los permisos pertinentes

---

### 🔄 Flujo del Sistema

| Actor principal (usuario) | Actor Secundario (sistema) |
| :--- | :--- |
| | El sistema presenta cinco secciones principales: Configuración básica, Configuración de viaje, Configuración de las notificaciones, Ajustes de tema y Certificados iOS. |
| El usuario define el país (ej. Venezuela), moneda (VEF/Bs), zona horaria y datos de contacto del administrador. | |
| El usuario ajusta parámetros operativos como: Radios de búsqueda, permisos de cambio de dirección, paradas múltiples, viajes compartidos y pagos divididos. | |
| El usuario activa/desactiva mediante switches las alertas por SMS, correo electrónico y verificaciones de seguridad. | |
| El usuario carga archivos JPG para el Logo, Ícono de título, Imagen de correo y Firma autorizada. | |
| El usuario selecciona el modo del certificado (Producción/Desarrollo) y carga el archivo Push P8 para iOS. | |
| El usuario hace clic en el botón "Actualizar cambios". | |
| | El sistema procesa la información y muestra un mensaje de éxito. |
| **Fin** | |

---

### 🔀 Flujo alternativo del sistema

| Acción del Usuario | Reacción del Sistema |
| :--- | :--- |
| En la sección Ajustes de tema, el usuario hace clic en "Browse..." para seleccionar un archivo local. | El sistema muestra la ruta del archivo seleccionado. |

---

### ✅ Post Condición del sistema

| Escenario | Resultado |
| :--- | :--- |
| **Éxito** | Los cambios se aplican en tiempo real para los usuarios finales (conductores y pasajeros). |
| **Fallo** | |

---


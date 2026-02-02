## Caso de Uso: CU-081-CONF-STNG - Datos de instalación

### 📋 Información General

| Sección | Descripción |
| :--- | :--- |
| **id** | CU-081-CONF-STNG |
| **Caso de Uso** | Datos de instalación |
| **Actor Principal** | Usuario |
| **Actores Secundarios** | Software |
| **Objetivo** | Configurar los parámetros de instalación técnica, incluyendo el país de administración, credenciales de Apple y datos de contacto globales. |
| **Prioridad** | |

---

### 🛠️ Precondiciones del Sistema
* El usuario inicia sesión de forma exitosa CU-001-ADM / CU-001-CLI
* El usuario cuenta con el rol y los permisos pertinentes

---

### 🔄 Flujo del Sistema

| Actor principal (usuario) | Actor Secundario (sistema) |
| :--- | :--- |
| El usuario accede al panel y expande la sección "Configuración básica de la aplicación". | |
| El usuario puede ajustar los datos de configuración del ESME: Identificador, token, numero y url. | |
| Indica que desea actualizar los datos. | El sistema deja persistencia. |
| Indica otros valores de configuración de mensajería como: APikEy, url, código, nivel de importancia para el acuse recibo. | |
| Indica que desea actualizar los datos. | El sistema deja persistencia. |
| El usuario puede cargar los parámetros de configuración de métodos de pago como stripe, payu y paystack. | |
| Indica que desea actualizar los datos. | El sistema deja persistencia. |
| El usuario puede configurar los parámetros de configuración de correo: correo, dominio y contraseña. | |
| Indica que desea actualizar los datos. | El sistema deja persistencia. |
| El usuario realiza la configuración de API GCM. | |
| Indica que desea actualizar los datos. | El sistema deja persistencia. |
| El usuario puede configurar las claves API de Google Places. | |
| Indica que desea actualizar los datos. | El sistema deja persistencia. |
| El usuario puede realizar la configuración del hosting de firebase. | |
| Indica que desea actualizar los datos. | El sistema deja persistencia. |
| El usuario puede realizar la configuración de la aplicación Android y iOS: url de aplicación cliente y conductor. | |
| Indica que desea actualizar los datos. | El sistema deja persistencia. |
| El usuario puede configurar la información del panel del aplicativo y versiones de la APP. | |
| Indica que desea actualizar los datos. | El sistema deja persistencia. |
| **Fin** | |

---

### 🔀 Flujo alternativo del sistema
N/A

---

### ✅ Post Condición del sistema

| Escenario | Resultado |
| :--- | :--- |
| **Éxito** | Se actualizan las variables de entorno que permiten el envío de notificaciones push en iOS y la visualización correcta de moneda y teléfonos en las apps. |
| **Fallo** | |

---


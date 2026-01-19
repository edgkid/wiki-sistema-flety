## Caso de Uso: CU-002-ADM - Recuperar Contraseña

Este caso de uso describe el procedimiento mediante el cual un usuario solicita la restauración de sus credenciales de acceso. El proceso se activa cuando el usuario no recuerda su contraseña y requiere un mecanismo de validación externo (vía email) para establecer una nueva clave y recuperar el acceso a su cuenta en el modelo `User`.

---

## 📋 Información General

| Sección | Descripción |
| :--- | :--- |
| **ID** | CU-002-ADM |
| **Caso de Uso** | Recuperar contraseña |
| **Actor Principal** | Usuario |
| **Actores Secundarios** | Software |
| **Objetivo** | Permitir que un usuario registrado solicite un enlace o código temporal para ingresar al sistema, recuperar o cambiar su contraseña. |
| **Prioridad** | Alta |

---

## 🛠️ Precondiciones del Sistema
* El usuario debe estar registrado previamente en el sistema (existencia en la colección `User`).
* El usuario debe haber sido redirigido desde el flujo de **CU-001-ADM** (Inicio de Sesión).

---

## 🔄 Flujo del Sistema



| Actor Principal (Usuario) | Actor Secundario (Sistema) |
| :--- | :--- |
| | 1) Muestra la vista "Has olvidado tu contraseña" con el campo "Email". |
| 2) Introduce el correo electrónico asociado a su cuenta | |
| 3) Presiona el botón "Enviar" | 4) El servicio de Autenticación verifica si el email existe en la base de datos. |
| | 5) Se procede a procesar el cambio de contraseña (envío de instrucciones/token). |

---

## 🔀 Flujo Alternativo

| Escenario | Resultado |
| :--- | :--- |
| **1) Email no registrado** | 2) El sistema muestra un mensaje de validación indicando que el correo no existe. |
| **2) Información inválida** | 2) El sistema muestra un mensaje de validación (ej: formato de correo incorrecto). |

---

## ✅ Post-Condiciones

| Escenario de Éxito | Escenario de Fallo |
| :--- | :--- |
| Se envía el correo de recuperación exitosamente | El sistema no emite ninguna comunicación externa |
| El sistema genera un token temporal de recuperación | El usuario visualiza mensajes de error de validación |
| Se registra el intento en los logs del sistema | El estado de la contraseña en el modelo `User` permanece intacto |

---

## 🔗 Casos de Uso Relacionados
* [Usuarios (CU-001)](02%20Casos%20de%20uso/CU-001-Usuarios.md)


## Caso de Uso: CU-002-CLI - Recuperar Contraseña

Este caso de uso describe el proceso mediante el cual un usuario que ha olvidado sus credenciales puede solicitar el restablecimiento de su acceso. El sistema valida la existencia de la cuenta y gestiona el envío de un mecanismo de recuperación para garantizar la continuidad del servicio al usuario.

---

## 📋 Información General

| Sección | Descripción |
| :--- | :--- |
| **ID** | CU-002-CLI |
| **Caso de Uso** | Recuperar contraseña |
| **Actor Principal** | Usuario |
| **Actor Secundario** | Software |
| **Objetivo** | Permitir que un usuario registrado solicite un enlace o código temporal para ingresar al sistema, recuperar o cambiar su contraseña. |
| **Prioridad** | Alta |

---

## 🛠️ Precondiciones del Sistema
* El usuario está registrado en el sistema.
* El usuario fue redirigido desde el flujo **CU-001-CLI** (Inicio de Sesión).

---

## 🔄 Flujo del Sistema



| Actor Principal (Usuario) | Actor Secundario (Sistema) |
| :--- | :--- |
| | 1) Muestra la vista "Has olvidado tu contraseña" con el campo "Email". |
| 2) Indica el correo asociado a la cuenta de usuario | |
| 3) Presiona el botón "Enviar" | 4) El servicio de Autenticación verifica si el email existe. |
| | 5) Se procede a procesar el cambio de contraseña. |

---

## 🔀 Flujo Alternativo

| Escenario | Resultado |
| :--- | :--- |
| **1) Email no registrado** | 2) El sistema muestra un mensaje de validación indicando que el correo no existe. |
| **2) Información inválida** | 2) El sistema muestra un mensaje de validación sobre el formato del dato ingresado. |

---

## ✅ Post-Condiciones

| Escenario de Éxito | Escenario de Fallo |
| :--- | :--- |
| Se inicia el proceso de recuperación de contraseña | Credenciales inválidas, no se puede procesar el cambio |
| Se envía el enlace/código al usuario | El usuario permanece en la interfaz de recuperación |
| | Se muestra un mensaje de error explicativo |

---

## 🔗 Casos de Uso Relacionados
*[Usuarios (CU-001)](02%20Casos%20de%20uso/CU-001-Usuarios.md)
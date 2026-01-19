## Caso de Uso: CU-003-REG - Registro de Usuario

Este caso de uso describe el proceso mediante el cual un nuevo prospecto se incorpora a la plataforma. El flujo incluye la captura de datos personales, la gestión de documentos obligatorios para la validación de identidad y la creación de las entradas correspondientes en la base de datos para habilitar el acceso futuro.

---

## 📋 Información General

| Sección | Descripción |
| :--- | :--- |
| **ID** | CU-003-REG |
| **Caso de Uso** | Registro de usuario |
| **Actor Principal** | Usuario |
| **Actor Secundario** | Software |
| **Objetivo** | Permitir el registro de un nuevo usuario en el sistema. |
| **Prioridad** | Alta |

---

## 🛠️ Precondiciones del Sistema
* El usuario **no debe estar registrado** previamente en el sistema (validación de email y teléfono).
* El servicio de almacenamiento de archivos debe estar operativo para la carga de documentos.

---

## 🔄 Flujo del Sistema



| Actor Principal (Usuario) | Actor Secundario (Sistema) |
| :--- | :--- |
| | 1) Muestra un formulario de registro con campos requeridos y de carga de documentos. |
| 2) Indica los datos en los campos del formulario | |
| 3) Pulsa el botón "Registrar" | 4) Valida la integridad y formato de los datos indicados. |
| | 5) Registra la información en la base de datos y redirige a la vista de inicio de sesión. |

---

## 🔀 Flujo Alternativo

| Escenario | Resultado |
| :--- | :--- |
| **1) Datos incorrectos o incompletos** | 2) El sistema resalta los campos faltantes y muestra un mensaje de validación. |
| **2) Email o teléfono ya existente** | 2) El sistema indica que el usuario ya posee una cuenta y sugiere recuperar contraseña. |

---

## ✅ Post-Condiciones

| Escenario de Éxito | Escenario de Fallo |
| :--- | :--- |
| El usuario es registrado exitosamente en el sistema | El usuario no es registrado en el sistema |
| Se solicita la confirmación de la cuenta creada (vía OTP/Email) | Se mantienen los datos en el formulario para su corrección |
| Se crean los registros de `User_Document` pendientes | |

---

## 🔗 Casos de Uso Relacionados
*[👤 Usuarios (CU-001)](02%20Casos%20de%20uso/CU-001-Usuarios.md)
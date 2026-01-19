# Caso de Uso: CU-001-ADM - Inicio de Sesión de Usuario

Este caso de uso describe el proceso mediante el cual un usuario registrado accede al sistema validando sus credenciales (email/teléfono y contraseña). El flujo garantiza que solo los usuarios autorizados obtengan un token de autenticación para interactuar con el dashboard y las funcionalidades protegidas de la aplicación.

---

### 📋 Información General
| Sección | Descripción |
| :--- | :--- |
| **ID** | CU-001-ADM |
| **Caso de Uso** | Inicio de Sesión (login) |
| **Actor Principal** | Usuario |
| **Actores Secundarios** | Software |
| **Objetivo** | Permitir al Usuario acceder al sistema, previa validación de sus credenciales |
| **Prioridad** | Alta |

### 🛠️ Precondiciones del Sistema
* El usuario debe estar registrado en el sistema.
* El servicio de autenticación debe estar disponible.

### 🔄 Flujo del Sistema
| Actor Principal (Usuario) | Actor Secundario (Sistema) |
| :--- | :--- |
| | 1) Se muestra la vista de inicio de sesión |
| 2) Introduce las credenciales (usuario y password) | |
| 3) Presiona "Iniciar sesión" | 4) Se envían las credenciales al servicio de autenticación |
| | 5) El servicio verifica las credenciales |
| | 6) Si las credenciales son válidas, se genera un token de autenticación |
| | 7) Se redirige al usuario al dashboard del sistema |
| 8) El usuario ingresa al dashboard | |

### 🔀 Flujo Alternativo
| Escenario | Resultado |
| :--- | :--- |
| **1) Credenciales incorrectas** | 2) No se genera token de autenticación. <br> 3) Se muestra mensaje de error. |
| **2) Olvido de contraseña** | 2) El sistema redirige al **CU-002 - Olvidó su contraseña**. |

### ✅ Post-Condiciones
| Escenario de Éxito | Escenario de Fallo |
| :--- | :--- |
| Se genera token de autenticación | El usuario permanece en la interfaz de login |
| El usuario es redirigido al dashboard | Se muestra mensaje de error explicativo |
| Se actualiza la sesión del usuario | |

### 🔗 Casos de Uso Relacionados 
* [ CU-002-Recuperar Contraseña](02%20Casos%20de%20uso/CU-002-Recuperar%20Contraseña.md) 
* [ CU-004 - Dashboard](02%20Casos%20de%20uso/CU-004%20-%20Dashboard.md)

# CU-001-Usuarios

## Caso de Uso: CU-001-CLI - Inicio de Sesión de Usuario

Este caso de uso describe el proceso mediante el cual un usuario registrado accede al sistema validando sus credenciales (email/teléfono y contraseña). El flujo garantiza que solo los usuarios autorizados obtengan un token de autenticación para interactuar con el dashboard y las funcionalidades protegidas de la aplicación.

---

## 📋 Información General

| Sección | Descripción |
| :--- | :--- |
| **ID** | CU-001-CLI |
| **Caso de Uso** | Inicio de Sesión (login) |
| **Actor Principal** | Usuario |
| **Actores Secundarios** | Software |
| **Objetivo** | Permitir al Usuario acceder al sistema, previa validación de sus credenciales. |
| **Prioridad** | Alta |

---

## 🛠️ Precondiciones del Sistema
* El usuario debe estar registrado en el sistema.
* El servicio de autenticación debe estar disponible.

---

## 🔄 Flujo del Sistema

| Actor Principal (Usuario) | Actor Secundario (Sistema) |
| :--- | :--- |
| | 1) Se muestra la vista de inicio de sesión |
| 2) Introduce las credenciales (usuario y password) | |
| 3) Presiona "Iniciar sesión" | 4) Se envían las credenciales al servicio de autenticación |
| | 5) El servicio verifica las credenciales |
| | 6) Si las credenciales son válidas, se genera un token de autenticación |
| | 7) Se redirige al usuario al dashboard del sistema |
| 8) El usuario ingresa al dashboard | |

---

## 🔀 Flujo Alternativo

| Escenario | Resultado |
| :--- | :--- |
| **1) Credenciales incorrectas** | 2) No se genera token de autenticación.<br>3) Se muestra mensaje de error. |
| **2) Olvido de contraseña** | 2) El sistema redirige al **CU-002 - Olvidó su contraseña**. |
| **3) Registro de usuario** | 2) El sistema redirige al **CU-003 - Registrar usuario**. |

---

## ✅ Post-Condiciones

| Escenario de Éxito | Escenario de Fallo |
| :--- | :--- |
| Se genera token de autenticación | El usuario permanece en la interfaz de login |
| El usuario es redirigido al dashboard | Se muestra mensaje de error explicativo |
| Se actualiza la sesión del usuario | |

---

## 🔗 Casos de Uso Relacionados
* [ CU-002-Recuperar Contraseña](02%20Casos%20de%20uso/CU-002-Recuperar%20Contraseña.md)
* [ CU-003-Registrar de Usuario](02%20Casos%20de%20uso/CU-003-Registrar%20de%20Usuario.md)
*  [ CU-004 - Dashboard](02%20Casos%20de%20uso/CU-004%20-%20Dashboard.md)


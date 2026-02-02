## Caso de Uso: CU-054-SERV-NWPA - Nuevo país

Este caso de uso describe el proceso para dar de alta una nueva entidad territorial en la plataforma, estableciendo los cimientos operativos como la moneda local, la pasarela de pagos y las políticas de incentivos por referidos.

### 📋 Información General

| Sección | Descripción |
| :--- | :--- |
| **ID** | CU-054-SERV-NWPA |
| **Caso de Uso** | Nuevo país |
| **Actor Principal** | Usuario |
| **Actor Secundario** | Software |
| **Objetivo** | Permite registrar una nueva entidad territorial (país) definiendo sus reglas de negocio, moneda y métodos de pago. |
| **Prioridad** | Alta |

---

### 🛠️ Precondiciones del Sistema
* El usuario inicia sesión de forma exitosa (**CU-001-ADM / CU-001-CLI**).
* El usuario cuenta con el rol y los permisos pertinentes.
* El usuario seleccionó la opción de agregar país desde **CU-052-SERV-PAÍS**.

---

### 🔄 Flujo del Sistema

| Actor Principal (Usuario) | Actor Secundario (Sistema) |
| :--- | :--- |
| | 1) El sistema despliega un formulario en blanco para el registro de la nueva entidad. |
| 2) El usuario activa el switch de "País de Negocio" y selecciona el nombre del país desde un menú desplegable. | |
| 3) Se ingresa el código de moneda (ej. USD, PEN), el símbolo correspondiente y el código de teléfono internacional. | |
| 4) El usuario selecciona el método de pago para conductores: **Banco** (requiere día de transferencia y zona horaria) o **Pago manual efectivo**. | |
| 5) El usuario activa los switches de "Referencia de usuario" y "Referencia del conductor" y define montos y límites. | |
| 6) Se selecciona la pasarela activa para el país (Stripe, Paystack o Payu). | |
| 7) El usuario presiona "Enviar". | 8) El sistema deja persistencia de los datos y redirige a **CU-052-SERV-PAÍS**. |
| **Fin** | |

---

### ⚙️ Parámetros de Configuración Regional

* **Gestión de Transferencias**: Define si la liquidación a conductores es automatizada por el sistema o gestionada manualmente en efectivo.
* **Motor de Crecimiento**: Configuración de bonos de referidos para usuarios y conductores de forma independiente.
* **Pasarela de Pago**: Enlace técnico con el proveedor de servicios financieros habilitado para la región.



---

### ✅ Post-Condiciones

| Escenario | Resultado Esperado |
| :--- | :--- |
| **Éxito** | El país queda registrado y aparece como una nueva tarjeta en la vista general, permitiendo configurar Ciudades y Tarifas asociadas a él. |
| **Fallo** | No se crea el registro; el sistema mantiene el formulario con los datos ingresados para que el administrador corrija el error. |

---

### 🔗 Casos de Uso Relacionados
* [CU-052-SERV-PAÍS](02%20Casos%20de%20uso/CU-052-SERV-PAÍS.md)
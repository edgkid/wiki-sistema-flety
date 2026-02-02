## Caso de Uso: CU-065-SERV-NWMO - Nuevo Modelo

Este caso de uso describe el proceso para definir y dar de alta los modelos estructurales de los vehículos en la plataforma. Este registro es esencial para establecer la identidad visual y operativa de las unidades que componen la flota.

### 📋 Información General

| Sección | Descripción |
| :--- | :--- |
| **ID** | CU-065-SERV-NWMO |
| **Caso de Uso** | Nuevo Modelo |
| **Actor Principal** | Usuario |
| **Actor Secundario** | Software |
| **Objetivo** | Permite definir los modelos estructurales de los vehículos y sus características físicas generales. |
| **Prioridad** | Alta |

---

### 🛠️ Precondiciones del Sistema
* El usuario inicia sesión de forma exitosa (**CU-001-ADM / CU-001-CLI**).
* El usuario cuenta con el rol y los permisos pertinentes.
* El usuario seleccionó la opción de agregar modelo desde **CU-064-SERV-MOD**.

---

### 🔄 Flujo del Sistema

| Actor Principal (Usuario) | Actor Secundario (Sistema) |
| :--- | :--- |
| 1) El usuario ingresa el nombre descriptivo en el campo correspondiente. | |
| 2) El usuario hace clic en "Subir Imagen" para seleccionar el archivo visual del modelo. | |
| 3) El usuario indica la categoría operativa del modelo creado. | |
| 4) El usuario indica el número de secuencia para el ordenamiento en la App. | |
| 5) El usuario solicita guardar la información. | 6) El sistema deja persistencia del nuevo modelo y redirige a **CU-064-SERV-MOD**. |
| **Fin** | |

---

### 🎨 Atributos del Modelo
* **Identidad Visual**: La imagen cargada será la que visualicen los clientes al seleccionar el tipo de servicio.
* **Jerarquía de Visualización**: El número de secuencia determina la posición del modelo en el carrusel de selección de la aplicación móvil.
* **Categorización**: Clasificación técnica que permite agrupar vehículos similares para fines de reporte.



---

### ✅ Post-Condiciones

| Escenario | Resultado Esperado |
| :--- | :--- |
| **Éxito (Registro)** | El modelo aparece inmediatamente en el tablero principal de modelos (**CU-064**). |
| **Éxito (Integración)** | La configuración queda disponible para ser enlazada en el módulo de "Camiones" y para nuevas "Tarifas" por ciudad. |
| **Fallo** | El sistema no crea el registro y solicita corregir los campos obligatorios (nombre o imagen). |

---

### 🔗 Casos de Uso Relacionados
* [CU-064-SERV-MOD](02%20Casos%20de%20uso/CU-064-SERV-MOD.md)
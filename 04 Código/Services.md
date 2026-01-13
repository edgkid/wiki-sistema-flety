# 🛠️ Capa de Servicios (`/services`)

La capa de **Services** (`services/`) encapsula toda la **lógica de negocio** y las reglas operacionales de la aplicación. Su función principal es abstraer la complejidad de las operaciones de datos y algoritmos de decisión, actuando como un mediador entre los controladores y la capa de acceso a datos (Modelos).
### Responsabilidades clave:

* **Abstracción de Lógica
* **Independencia:** No conoce la existencia de los objetos `req` (petición) o `res` (respuesta) de Express.
* **Integridad de Datos:** Asegura que las reglas de negocio se cumplan antes de realizar cambios persistentes en la base de datos.
* **Interacción con Modelos:** Realiza consultas directas a las colecciones de MongoDB a través de Mongoose.

---

### 📋 Listado de Objetos Service

* [✈️ Trip Service ](04%20Código/Trip%20Service.md)
* 🌎 [Country Service](04%20Código/Country%20Service.md)
* 🔍 [Filter Service](04%20Código/Filter%20Service.md)
* * 📁 [File Upload Service](04%20Código/File%20Upload%20Service.md)

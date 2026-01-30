La capa de **Controllers** (`controllers/`) actúa como el intermediario entre las rutas y la lógica de negocio. Su función principal es recibir las solicitudes del cliente (HTTP requests), procesar los parámetros de entrada y coordinar la respuesta adecuada, delegando la carga de trabajo pesada a los **Services**.

# 📂 Estructura del Directorio de Controladores

Esta tabla detalla la organización de los archivos del sistema, facilitando la localización de la lógica de negocio según su categoría.

## 1. Controller (Raíz)

| Archivo | Responsabilidad Principal |
| :--- | :--- |
| [Admin.js](04%20Código/Controller-Principal/Admin.md) | Configuración global y gestión del panel administrativo. |
| [Bank_Detail.js](04%20Código/Controller-Principal/Bank_Detail.md) | Administración de cuentas bancarias. |
| [Card.js](04%20Código/Controller-Principal/Card.md) | Ciclo de vida de métodos de pago. |
| [City.js](04%20Código/Controller-Principal/City.md) | Catálogo maestro de ciudades operativas por país. |
| [CityType.js](04%20Código/Controller-Principal/CityType.md) | Definición de tipos de vehículos, servicios y tarifas locales. |
| [Country.js](04%20Código/Controller-Principal/Country.md) | Gestión de configuración regional y jerarquía geográfica. |
| [Crons.js](04%20Código/Controller-Principal/Crons.md) | Automatización de tareas programadas. |
| [Emergency_Contact.js](04%20Código/Controller-Principal/Emergency_Contact.md) | Gestión de contactos de emergencia. |
| [Provider.js](04%20Código/Controller-Principal/Provider.md) | Gestión del perfil y estado del conductor. |
| [Provider_Analytics.js](04%20Código/Controller-Principal/Provider_Analytics.md) | Registro de métricas de desempeño del proveedor. |
| [Provider_Document.js](04%20Código/Controller-Principal/Provider_Document.md) | Validación y almacenamiento de documentación del proveedor. |
| [Provider_Earning.js](04%20Código/Controller-Principal/Provider_Earning.md) | Cálculo diario de ingresos y reportes de ganancias. |
| [Shedule_Trip.js](04%20Código/Controller-Principal/Shedule_trip.md) | Lógica para la reserva y activación de viajes. |
| [Trip.js](04%20Código/Controller-Principal/Trip.md) | Gestión de viajes en tiempo real (Solicitud → Fin). |
| [User.js](04%20Código/Controller-Principal/User.md) | Registro, autenticación y gestión del perfil del usuarios. |
| [User_document.js](04%20Código/Controller-Principal/UserDocument.md) | Verificación de identidad y documentos de usuarios. |
| [Wallet_History.js](04%20Código/Controller-Principal/Wallet_History.md) | Gestión de los movimientos de la billetera. |

---

## 2. Corporate Controller

| Archivo | Responsabilidad Principal |
| :--- | :--- |
| [Corporate_Api.js](04%20Código/Corporate_Controller/Corporate_Api.md) | Gestión de endpoints para integración de socios. |
| [Corporate.js](04%20Código/Corporate_Controller/Corporate.md) | Gestión general de cuentas de socios corporativos. |
| [Corporate_Payments.js](04%20Código/Corporate_Controller/Corporate_Payments.md) | Métodos de pago, facturación y control de saldo empresarial. |
| [Corporate_Static_Api.js](04%20Código/Corporate_Controller/Corporate_Static_Api.md) | Dashboards y analítica visual para usuarios corporativos. |

---

## 3. Admin Controller

| Archivo                                                                                         | Responsabilidad Principal                                        |
| :---------------------------------------------------------------------------------------------- | :--------------------------------------------------------------- |
| [Weekly_Earning.js](04%20Código/Admin_Controller/Weekly_Earning.md)                             | Liquidación y dispersión de pagos acumulados semanalmente.       |
| [Admin_Partner_Weekly_Earning.js](04%20Código/Admin_Controller/Admin_Partner_Weekly_Earning.md) | Supervisa la liquidación de las ganancias de los asociados.      |
| [Bank_Detail.js](04%20Código/Admin_Controller/Bank_Detail.md)                                   | Gestión de información de cuentas bancarias en la plataforma.    |
| [City_Service.js](04%20Código/Admin_Controller/City_Service.md)                                 | Configuración de la lógica de servicios y tarifas por ciudad.    |
| [City.js](04%20Código/Admin_Controller/City.md)                                                 | Gestión de la creación y estado de ciudades operativas.          |
| [Corporate_Admin.js](04%20Código/Admin_Controller/Corporate_Admin.md)                           | Administración y supervisión de las cuentas corporativas.        |
| [Country.js](04%20Código/Admin_Controller/Country.md)                                           | Gestión de los países donde la plataforma tiene presencia.       |
| [Daily_Earning.js](04%20Código/Admin_Controller/Daily_Earning.md)                               | Auditoría y control de las ganancias diarias del sistema.        |
| [Dashboard.js](04%20Código/Admin_Controller/Dashboard.md)                                       | Visualización de estadísticas globales y métricas clave.         |
| [Dispatcher.js](04%20Código/Admin_Controller/Dispatcher.md)                                     | Consola para la asignación manual de viajes a conductores.       |
| [Documents.js](04%20Código/Admin_Controller/Documents.md)                                       | Gestión maestra de documentos requeridos por la plataforma.      |
| [Email_Detail.js](04%20Código/Admin_Controller/Email_Detail.md)                                 | Gestión de plantillas y configuración de envío de correos.       |
| [Ferry_Ticket.js](04%20Código/Admin_Controller/Ferry_Ticket.md)                                 | Gestión y validación de tickets de transporte especial.          |
| [Guest_Token.js](04%20Código/Admin_Controller/Guest_Token.md)                                   | Generación y control de tokens para acceso de invitados.         |
| [Inbox_Notifications.js](04%20Código/Admin_Controller/Inbox_Notifications.md)                   | Centro de mensajería y notificaciones push del sistema.          |
| [Languages.js](04%20Código/Admin_Controller/Languages.md)                                       | Administración de los idiomas soportados por la interfaz.        |
| [Map_View.js](04%20Código/Admin_Controller/Map_View.md)                                         | Monitorización en tiempo real de la ubicación de la flota.       |
| [Partner_Earning.js](04%20Código/Admin_Controller/Partner_Earning.md)                           | Gestión financiera y auditoría desde la vista de asociados.      |
| [Partner_Payments.js](04%20Código/Admin_Controller/Partner_Payments.md)                         | Gestión de pasarela de pagos y billetera para socios.            |
| [Partner.js](04%20Código/Admin_Controller/Partner.md)                                           | Gestión del ciclo de vida (alta/baja) de los asociados.          |
| [Promo_Code.js](04%20Código/Admin_Controller/Promo_Code.md)                                     | Creación y monitoreo de campañas con códigos promocionales.      |
| [Provider_Daily_Earning.js](04%20Código/Admin_Controller/Provider_Daily_Earning.md)             | Desglose de ingresos diarios por conductor individual.           |
| [Provider_Earning.js](04%20Código/Admin_Controller/Provider_Earning.md)                         | Reportes generales de ganancias para proveedores.                |
| [Provider_Weekly_Earning.js](04%20Código/Admin_Controller/Provider_Weekly_Earning.md)           | Reportes semanales de ganancias para proveedores.                |
| [Provider.js](04%20Código/Admin_Controller/Provider.md)                                         | Gestión administrativa del perfil y estado de proveedores.       |
| [Request.js](04%20Código/Admin_Controller/Request.md)                                           | Auditoría y seguimiento de solicitudes de servicio.              |
| [Review.js](04%20Código/Admin_Controller/Review.md)                                             | Moderación de calificaciones y comentarios de servicios.         |
| [Shedule.js](04%20Código/Admin_Controller/Shedule.md)                                           | Administración de la agenda de viajes futuros programados.       |
| [Send_Mass_Notifications.js](04%20Código/Admin_Controller/Send_Mass_Notifications.md)           | Herramienta de difusión masiva de notificaciones.                |
| [Service_Specifications.js](04%20Código/Admin_Controller/Service_Specifications.md)             | Gestión de detalles técnicos y requisitos del servicio.          |
| [Service_Type.js](04%20Código/Admin_Controller/Service_Type.md)                                 | Clasificación de tipos de vehículos por categoría de servicio.   |
| [Setting.js](04%20Código/Admin_Controller/Setting.md)                                           | Panel de configuración global (API Keys, Legales, Marca).        |
| [Sms_Detail.js](04%20Código/Admin_Controller/Sms_Detail.md)                                     | Gestión de plantillas para comunicaciones vía SMS.               |
| [Transaction_History.js](04%20Código/Admin_Controller/Transaction_History.md)                   | Gestión de auditoría del historial de transferencias y pagos     |
| [Trip_Earning.js](04%20Código/Admin_Controller/Trip_Earning.md)                                 | Gestión de detalles de pago por viaje realizado.                 |
| [Truck.js](04%20Código/Admin_Controller/Truck.md)                                               | Gestión de la flota de vehículos                                 |
| [Type_Capacity.js](04%20Código/Admin_Controller/Type_Capacity.md)                               | Gestión de escalas de capacidad logística de servicios/vehiculos |
| [Type_Models.js](04%20Código/Admin_Controller/Type_Models.md)                                   | Catálogo maestro de modelos de vehículos registrados.            |
| [Type_Services.js](04%20Código/Admin_Controller/Type_Services.md)                               | Administración de tipo de servicio técnico.                      |
| [User.js](04%20Código/Admin_Controller/User.md)                                                 | Gestión y auditoría administrativa de usuarios finales.          |
| [Wallet_History.js](04%20Código/Admin_Controller/Wallet_History.md)                             | Historial maestro de movimientos en billeteras.                  |

---

## 4. Provider Controller

| Archivo                                                    | Responsabilidad Principal                                              |
| :--------------------------------------------------------- | :--------------------------------------------------------------------- |
| [Payment.js](04%20Código/Provider_Controller/Payment.md)   | Gestión de métodos de pago y recargas de saldo del conductor.          |
| [Provider.js](04%20Código/Provider_Controller/Provider.md) | Perfil, autenticación y carga de documentos del conductor.             |
| [Trip.js](04%20Código/Provider_Controller/Trip.md)         | Gestión operativa de solicitudes, ingresos y exportación de historial. |

---

## 5. Otros Controllers

| Archivo                                                                           | Responsabilidad Principal       |
| :-------------------------------------------------------------------------------- | :------------------------------ |
| [Selects_Controller.js](04%20Código/Controller_Api_Partner/Selects_Controller.md) | Se gestionan utilitarios varios |
|                                                                                   |                                 |
|                                                                                   |                                 |
|                                                                                   |                                 |












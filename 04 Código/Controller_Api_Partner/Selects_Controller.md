# Archivo: `Capacities_Types.js`

## Descripción General
Función utilitaria para asociar vehículo y capacidad de vehículo

---

## Funciones del Servicio

| Función                     | Tipo  | Entrada               | Salida           | Descripción                                                                                                                                        |
| :-------------------------- | :---- | :-------------------- | :--------------- | :------------------------------------------------------------------------------------------------------------------------------------------------- |
| `getTypeCapacitiesByTypeId` | Async | `{ typeId }` (Object) | Array de Objetos | Permite buscar un tipo de vehículo por su ID, cruzarlo con la colección de capacidades y retornar una lista detallada de capacidades por vehículo. |

# Archivo: `Cars_Types.js`

## Descripción General
Este controlador se encarga de validar si la plataforma opera en la ubicación del usuario (País y Ciudad) y filtrar los tipos de servicios (vehículos) disponibles y clientes 

---

## Funciones del Motor Lógico

| Función               | Tipo  | Entrada                                         | Salida       | Descripción                                                                                                                   |
| :-------------------- | :---- | :---------------------------------------------- | :----------- | :---------------------------------------------------------------------------------------------------------------------------- |
| `getCountry`          | Async | `subAdminCountry`, `countryCode`                | Objeto (Doc) | Busca en la base de datos un país que coincida con el nombre o código proporcionado .                                         |
| `getCityDetails`      | Async | `countryname`, `cityname`                       | Objeto (Doc) | Recupera los detalles de configuración de una ciudad específica dentro de un país, validando que esté habilitada para operar. |
| `getFinalCityDetails` | Sync  | `cityDetails`, `currentCityLatLong`             | Objeto (ID)  | Compara las coordenadas del usuario con el radio o polígono de la ciudad para confirmar si está dentro del área de servicio.  |
| `getUserType`         | Sync  | `corporateDetails`                              | Número (ID)  |                                                                                                                               |
| `getCityTypesItems`   | Async | `countryId`, `cityId`, `userType`, `userTypeId` | Array        |                                                                                                                               |

# Archivo: `Get_Cars_Models.js`

## Descripción General
Este archivo exporta una función  encargada de filtrar y retornar el catálogo de modelos de vehículos registrados en el sistema

---

## Funciones del Módulo

| Función         | Tipo  | Entrada                   | Salida | Descripción                                                                                                                           |
| :-------------- | :---- | :------------------------ | :----- | :------------------------------------------------------------------------------------------------------------------------------------ |
| `getModelsCars` | Async | `req.body.modelsTypesIds` | JSON   | Recibe un array de IDs de modelos, consulta la base de datos y retorna los objetos detallados que coincidan con esos identificadores. |


# Archivo: `get_Type_By_Type.js`

## Descripción General
Este controlador funciona como un servicio de consulta para la configuración de servicios por ciudad.

---

## Funciones del Servicio

| Función           | Tipo  | Entrada                               | Salida       | Descripción                                                                                  |
| :---------------- | :---- | :------------------------------------ | :----------- | :------------------------------------------------------------------------------------------- |
| `getCityDetails`  | Async | `countryname`, `cityname`             | Objeto (Doc) | Busca y retorna los datos de configuración de una ciudad específica.                         |
| `getTypeByTypeId` | Async | `req.body` (token, typeId, ubicación) | JSON         | Valida al cliente, localiza la ciudad y obtiene el detalle completo del servicio solicitado. |

# Archivo: `Models_Types.js`

## Descripción General
Este controlador permite manejar datos entre los tipos de vehículos y tipos de servicios.

---

## Funciones del Módulo

| Función                 | Tipo  | Entrada               | Salida           | Descripción                                                                                                            |
| :---------------------- | :---- | :-------------------- | :--------------- | :--------------------------------------------------------------------------------------------------------------------- |
| `getTypeModelsByTypeId` | Async | `{ typeId }` (Object) | Array de Objetos | Encuentra un Tipo por ID y lo cruza con sus modelos vinculados, luego retornar una lista detallada de modelos activos. |


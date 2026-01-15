Descripción del servicio:
Servicio encardo de gestionar la lógica de negocio relacionada con las entidades de **Países (Country)** y su relación con las **Ciudades (City)**. Actúa como intermediaria entre los modelos de Mongoose y los controladores, facilitando la obtención de datos filtrados y la agregación de información geográfica.

### Función: getCityListCountries (Async)

**Descripción:**
Obtiene una lista de países adjunta con sus respetivas ciudades, para esto la funcion recibe una lista de objetos.

| Etapa       | Campo                 | Tipo                         | Descripción                                                         |
| :---------- | :-------------------- | :--------------------------- | :------------------------------------------------------------------ |
| **Entrada** | `countries`           | Array                        | Lista de objetos de países                                          |
| **Salida**  | `countriesWithCities` | {Promise\<Array\<Object\>\>} | Promesa que resuelve a un array de países con el campo `city_list`. |
### Función: getCountries (Async)

**Descripción:**
Obtiene países activos para el negocio, filtrados por ID o nombre.

| Etapa | Campo | Tipo | Descripción |
| :--- | :--- | :--- | :--- |
| **Entrada** | `country_id` | String | ID único del país |
| **Entrada** | `country_name` | String | Nombre del país |
| **Salida** | `countries` | Promise\<Array\<Object\>\> | Lista de países con campos seleccionados |
### Función: getCityListCountry (Async)

**Descripción:**
Obtiene la lista de documentos de ciudades pertenecientes a un país específico.

| Etapa       | Campo        | Tipo                       | Descripción                                                            |
| :---------- | :----------- | :------------------------- | :--------------------------------------------------------------------- |
| **Entrada** | `country_id` | String                     | ID único del país                                                      |
| **Salida**  | `cityList`   | Promise\<Array\<Object\>\> | Lista de objetos con la identificación de nombre de ciudad y código Id |
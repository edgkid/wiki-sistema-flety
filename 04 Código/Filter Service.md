Descripción del servicio: 
Servicio encargado de centraliza la lógica de filtrado y búsqueda . aqui se construyen objetos de búsqueda dinámicos (`$match` para agregaciones de MongoDB), manejando búsquedas por nombres y haciendo uso de expresiones regulares, estados de pago y tipos de usuario.

### Función: handleSearch (Sync)

**Descripción:**
Función principal y punto de entrada principal. Determina qué tipo de filtro aplicar basándose en el campo de búsqueda solicitado.

| Etapa       | Campo         | Tipo               | Descripción                                    |
| :---------- | :------------ | :----------------- | :--------------------------------------------- |
| **Entrada** | `search_item` | String             | Nombre del campo por el cual se va a filtrar   |
| **Entrada** | `value`       | String             | El valor que el usuario ingresó en la búsqueda |
| **Entrada** | `userType`    | String             | El tipo de usuario que realiza la acción       |
| **Salida**  | `Objeto`      | { "$match": { } }; | Objeto de agregación de MongoDB                |
### Función: generateNameQueries (Sync)

**Descripción:**
Crea una consulta de búsqueda flexible para nombres y apellidos utilizando Regex.

| Etapa       | Campo    | Tipo               | Descripción                                |
| :---------- | :------- | :----------------- | :----------------------------------------- |
| **Entrada** | `field`  | String             | Nombre del objeto en el esquema            |
| **Entrada** | `valuye` | String             | Nombre buscado                             |
| **Salida**  | `Objeto` | { "$match": { } }; | objeto de agregación de MongoDB tipo Regex |
### Función: getPaidType (Sync)

**Descripción:**
Determina qué nombre de campo en la base de datos corresponde al registro de pagos según el tipo de usuario.

| Etapa       | Campo                              | Tipo   | Descripción                                                  |
| :---------- | :--------------------------------- | :----- | :----------------------------------------------------------- |
| **Entrada** | `userType`                         | Number | código del tipo de usuario                                   |
| **Salida**  | `'paid_client'` o `'paid_partner'` | String | objeto de agregación de MongoDB tipo `{ "$match": { ... } }` |
### Función: getSearchHandlers (Sync)

**Descripción:**
Permite manejar un diccionario de funciones que mapea campos de búsqueda.

| Etapa       | Campo       | Tipo   | Descripción                                                  |
| :---------- | :---------- | :----- | :----------------------------------------------------------- |
| **Entrada** | `paid_type` | String | El campo de pago obtenido previamente                        |
| **Salida**  | `$match`    | Objeto | objeto de agregación de MongoDB tipo `{ "$match": { ... } }` |
### Función: addQueries (Sync)

**Descripción:**
Esta función inserta expresiones regulares en un arreglo de consultas.

| Etapa       | Campo      | Tipo   | Descripción                                   |
| :---------- | :--------- | :----- | :-------------------------------------------- |
| **Entrada** | `queries`  | Array  | Arreglo donde se almacenan las consultas      |
| **Entrada** | `field`    | String | El prefijo del objeto                         |
| **Entrada** | `namepart` | String | La palabra o fragmento de texto a buscar      |
| **Salida**  | -          | -      | Actualiza el arreglo `queries` por referencia |
### Función: validateFullName (Sync)

**Descripción:**
Valida si el valor ingresado es un nombre simple (una palabra) o compuesto.

| Etapa | Campo | Tipo | Descripción |
| :--- | :--- | :--- | :--- |
| **Entrada** | `value` | String | El texto a evaluar |
| **Salida** | - | Boolean | true si el nombre tiene menos de 2 palabras, false en caso contrario |
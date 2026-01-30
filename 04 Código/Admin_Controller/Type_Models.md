# Archivo: `Type_Models.js`

## Descripción General
Este controlador gestiona el catálogo de modelos de vehículos . Su función principal es definir los modelos vinculados con los servicios técnicos que pueden prestar. 

---

## Funciones del Controlador

### 1. Catálogo

| Función               | Tipo  | Entrada              | Salida     | Descripción                                                                                                                        |
| :-------------------- | :---- | :------------------- | :--------- | :--------------------------------------------------------------------------------------------------------------------------------- |
| `type_model_list`     | Async | `req.body` (filtros) | Vista HTML | Recupera y muestra la lista de modelos de vehículos registrados.                                                                   |
| `add_type_model_form` | Async | N/A                  | Vista HTML | Prepara el entorno para crear un modelo nuevo vinculando sus respectivos servicios.                                                |
| `edit`                | Async | `req.body.id`        | Vista HTML | Obtiene los datos de un modelo y la lista de servicios activos para cargar con la finalidad de presentar un formulario de edición. |

### 2. Operaciones de Datos

| Función          | Tipo  | Entrada                 | Salida      | Descripción                           |
| :--------------- | :---- | :---------------------- | :---------- | :------------------------------------ |
| `add_type_model` | Async | `req.body`, `req.files` | Redirección | Crea un nuevo registro de modelo      |
| `update`         | Sync  | `req.body`, `req.files` | Redirección | Actualiza la información de un modelo |
| `act`            | Async | `id`, `state`           | Redirección | Cambia el estatus  del modelo.        |

### 3. Reportes

| Función                     | Tipo  | Entrada              | Salida        | Descripción                                              |
| :-------------------------- | :---- | :------------------- | :------------ | :------------------------------------------------------- |
| `generate_type_model_excel` | Async | `req.body` (filtros) | Archivo Excel | Exporta la base de datos de modelos a un archivo `.xlsx` |
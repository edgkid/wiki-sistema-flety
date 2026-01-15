Descripción del servicio: 
Servicio encargado de la lógica para realizar la carga de archivos en el servidor. Su función principal es procesar archivos binarios (imágenes) recibidos desde el navegador, almacenarlos en el sistema de archivos y retornar las rutas accesibles (URLs).

### Función: validateLocation (Async)

**Descripción:**
Verifica si una ubicación geográfica (coordenadas) es válida dentro de un estado específico.

| Etapa | Campo | Tipo | Descripción |
| :--- | :--- | :--- | :--- |
| **Entrada** | `coordinates` | Object | Objeto con latitud y longitud |
| **Entrada** | `stateNumber` | Number | Identificador único del estado |
| **Salida** | `boolean` | `found` | Retorna `true` si la ubicación es válida, `false` en caso contrario |

**Archivo:** `trip.js`

### Función: `create_trip` (Async)

**Descripción:**
Procesar la creación de solicitudes de viaje individuales o masivas.

|             | Campo             | Tipo     | Descripción                                                        |
| :---------- | :---------------- | :------- | :----------------------------------------------------------------- |
| **Entrada** | `user_data`       | Object   | Datos del usuario que solicita el servicio                         |
| **Entrada** | `trip_type`       | Number   | Tipo de viaje                                                      |
| **Entrada** | `service_type_id` | ObjectId | Identificador del tipo de servicio                                 |
| **Entrada** | `req_data`        | Object   | Detalles del viaje (coordenadas, direcciones, pago)                |
| **Entrada** | `req`             | Object   | Objeto de solicitud de Express                                     |
| **Entrada** | `response`        | Function | Call back para retornar resultados                                 |
| **Salida**  | `Objeto`          | Object   | **Promesa {** `success`, `trip`, `multiple_trips`, `message` **}** |

---


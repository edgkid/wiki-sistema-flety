Descripción del Servicio:
Servicio encargado de la lógica de negocio relacionada con los viajes y  cálculos de tarifas por distancia, validación de coordenadas geográficas  y ajustes de precios según el tipo de transporte, servicio y region.

### Función: calculateTariff (Async)

**Descripción:**
Calcular precio por unidad de distancia y rango tarifario.

|             | Campo                | Tipo                                           | Descripción                       |
| :---------- | :------------------- | :--------------------------------------------- | :-------------------------------- |
| **Entrada** | `distanceKmMile`     | Number                                         | Distancia del viaje               |
| **Entrada** | `model_pricing_type` | Object                                         | definición de tarifa              |
| **Salida**  | `Objeto`             | Promesa { `price_per_unit_distance`, `range` } | Precio unitario e índice de rango |

### Función: recalculateTariff (Async)

**Descripción:**
Recalcula la tarifa comparando el precio previo con un nuevo cálculo de rango.

|             | Campo                         | Tipo                                                                                                                                                     | Descripción                                     |
| :---------- | :---------------------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------- | :---------------------------------------------- |
| **Entrada** | `previusTotal`                | Number                                                                                                                                                   | Total anterior del viaje                        |
| **Entrada** | `model_pricing_type`          | Object                                                                                                                                                   | Configuración de precios                        |
| **Entrada** | `distanceKmMile`              | Number                                                                                                                                                   | Distancia actual                                |
| **Entrada** | `pricePerUnitDistancePrevius` | Number                                                                                                                                                   | Precio por unidad anterior                      |
| **Salida**  | `Objeto`                      | Promesa { <br> `pricePerUnit`, <br> `recalculate.price_per_unit_distance`, <br> `price: fixedPrice`, <br> `fixed: false`, <br> `distanceFixed: 0` <br> } | Objeto con el nuevo precio y banderas de ajuste |


### Función: validateLocation (Async)

**Descripción:**
Calcular precio por unidad de distancia y rango tarifario.

| Etapa | Campo | Tipo | Descripción |
| :--- | :--- | :--- | :--- |
| **Entrada** | `coordinates` | Object | Objeto de coordenadas |
| **Entrada** | `stateNumber` | Number | Id de estado |
| **Salida** | `boolean` | found | True si las coordenadas son correctas |

### Función: tariffRecalculateRange (Async)

**Descripción:**
Ajusta la distancia si cae en umbrales específicos.

| Etapa | Campo | Tipo | Descripción |
| :--- | :--- | :--- | :--- |
| **Entrada** | `distanceKmMile` | Number | Distancia a evaluar |
| **Entrada** | `model_pricing_type` | Object | Configuraciónd de precios |
| **Salida** | `Object` | Promise { <br> `price_per_unit_distance`, <br> `distanceKmMile: newDistanceKmMile`, <br> `fixedRange` <br> } | Información del ajuste de tarifa |

### Función: calculateTransitPrice (Sync)

**Descripción:**
Calcula el costo total para operaciones específicas.

| Etapa | Campo | Tipo | Descripción |
| :--- | :--- | :--- | :--- |
| **Entrada** | `selected_transit_type_number` | Number | transito |
| **Entrada** | `country_name` | String | Nombre de estado y/o ciudad |
| **Entrada** | `ti_price` | Number | Precio base |
| **Salida** | `Number` | `ti_total_price` | Precio total de tránsito calculado |



# Archivo: `corporate_statistics_api.js`

## Descripción General
Este controlador actúa como una interfaz de análisis para el perfil corporativo. Su función es consolidar grandes volúmenes de datos de viajes realizados bajo una cuenta de empresa y transformarlos en métricas clave para la toma de decisiones y el control de presupuestos.

---

## Funciones del Controlador

| Función | Tipo | Entrada | Salida | Descripción |
| :--- | :--- | :--- | :--- | :--- |
| `corporate_statistics_api` | Async | `req.session.corporate` | JSON con métricas | Valida la sesión de la empresa y retorna un resumen detallado que incluye contadores de viajes, sumas totales de inversión, distancias recorridas y promedios de uso. |
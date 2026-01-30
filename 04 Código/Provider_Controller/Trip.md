# Archivo: `Trip.js`

## Descripción General
Este controlador gestiona los viajes y finanzas, proporciona al conductor una visibilidad completa sobre sus solicitudes de servicio (pendientes y aceptadas), su historial de ingresos detallado por movimientos de billetera y la capacidad de exportar sus registros de actividad.

---

## Funciones del Controlador

| Función                         | Tipo | Entrada                             | Salida        | Descripción                                                             |
| :------------------------------ | :--- | :---------------------------------- | :------------ | :---------------------------------------------------------------------- |
| `provider_request`              | Sync | `req.body` (filtros), `req.session` | Vista HTML    | Gestiona la lista de solicitudes de viaje.                              |
| `provider_wallet_history`       | Sync | `req.session.provider`              | Vista HTML    | Recupera y muestra todos los movimientos  en la billetera del proveedor |
| `provider_history_export_excel` | Sync | `req.body` (filtros)                | Archivo Excel | Genera un reporte detallado en formato `.xlsx`                          |
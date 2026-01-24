# Archivo: `wallet_history.js`

## Descripción General
Este controlador tiene como propósito principal servir a la interfaz de consulta para el historial de movimientos de la billetera  dentro de la plataforma.

---

## Funciones del Controlador

| Función | Tipo | Entrada (req.body) | Salida | Descripción |
| :--- | :--- | :--- | :--- | :--- |
| `get_wallet_history` | Async | `user_id`, `token`, `type` (Usuario / Proveedor) | JSON con array `wallet_history` | Recupera todos los movimientos de la billetera (ingresos, egresos, transferencias) asociados a una cuenta específica. |
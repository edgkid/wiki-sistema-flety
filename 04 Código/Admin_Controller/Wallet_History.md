# Archivo: `Wallet_history.js`

## Descripción General
Este controlador gestiona el historia de la billetera virtual para todos los actores de la plataforma (Usuarios, Proveedores y Socios/Partners). Su función principal es proporcionar una auditoría  de cada movimiento de saldo.

---

## Funciones del Controlador

| Función                         | Tipo | Entrada                             | Salida        | Descripción                                                                         |
| :------------------------------ | :--- | :---------------------------------- | :------------ | :---------------------------------------------------------------------------------- |
| `admin_wallet_history`          | Sync | `req.body` (filtros), `req.session` | Vista HTML    | Recupera el historial detallado de transacciones de billetera.                      |
| `generate_wallet_history_excel` | Sync | `req.body` (filtros)                | Archivo Excel | Procesa los registros financieros filtrados y genera un reporte en formato `.xlsx`. |
# Archivo: `Transaction_History.js`

## Descripción General
Este controlador se encarga de la gestión y auditoría del historial de transferencias y Transacciones realizadas a través de la plataforma. 

---

## Funciones del Controlador

| Función                              | Tipo | Entrada                             | Salida        | Descripción                                                                                         |
| :----------------------------------- | :--- | :---------------------------------- | :------------ | :-------------------------------------------------------------------------------------------------- |
| `admin_transaction_history`          | Sync | `req.body` (filtros), `req.session` | Vista HTML    | Recupera el listado de  movimientos  realizados. P                                                  |
| `generate_transaction_history_excel` | Sync | `req.body` (filtros)                | Archivo Excel | Procesa los datos de las transacciones filtradas y genera un reporte descargable en formato `.xlsx` |

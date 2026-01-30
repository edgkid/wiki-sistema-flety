# Archivo: `Partner_Earning.js`

## Descripción General
Este controlador para la gestión financiera desde de los asociados, permite que un asociado consulte y desglose sus ganancias acumuladas a través de la actividad de su flota de conductores. 

---

## Funciones del Controlador

| Función                            | Tipo  | Entrada                 | Salida      | Descripción                                                                                    |
| :--------------------------------- | :---- | :---------------------- | :---------- | :--------------------------------------------------------------------------------------------- |
| `partner_earning`                  | Async | `req.session`           | Redirección | Redirecciona al Socio a su perfil, asegurando que el acceso a datos financieros esté validado. |
| `partner_weekly_earning_statement` | Async | `ID proveedor`, `fecha` | Vista HTML  | Genera un estado de cuenta semanal de un conductor específico.                                 |
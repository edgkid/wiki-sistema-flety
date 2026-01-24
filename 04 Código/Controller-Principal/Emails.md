# Archivo: `emails.js`

## Descripción General
Este archivo centraliza la lógica de envío de correos electrónicos. Funge como un motor de **plantillas dinámicas** que recupera diseños HTML predefinidos y reemplaza variables (como nombres, fechas o IDs de viaje) antes de realizar el envío a través de los servicios de mensajería configurados.

---

## Funciones del Controlador

| Función | Tipo | Entrada | Salida | Descripción |
| :--- | :--- | :--- | :--- | :--- |
| `sendEmail` | Sync | `req`, `provider`, `user`, `emailID`, `extraParam` | Envío de Correo | Procesa y despacha correos electrónicos basados en plantillas preconfiguradas para usuarios o conductores. |
| `sendEmailNotification` | Sync | `req`, `email_data`, `extraParam`, `email`, `name` | HTML Renderizado | Realiza el envío de una notificación formal, renderizando el contenido HTML dinámicamente. |
| `sendAdminEmail` | Async | `admin_id`, `subject`, `content` | Éxito / Error | Envía notificaciones directas al panel administrativo sobre eventos críticos del sistema. |
| `email_notification` | Async | `to`, `subject`, `text`, `html` | Status de transporte | Interfaz de bajo nivel que se comunica con el servidor SMTP (u otros servicios como SendGrid) para despachar el mensaje. |
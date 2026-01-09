El proyecto EBER (Backend Flety) en su versión 1.0.0 definida y según su package.json. Refleja un sistema montado sobre un patrón MVC  y segmentado por roles de usuario, corporativo, transportista/chofer y administrador. Su principal stock tecnológico es Node.js 16 y Express 4.x.

El proyecto integra:

1. socket.io y @socket.io/redis-adapter para comunicación en tiempo real    
2. cron-cluster y node-schedule para la ejecución de tareas programadas
3. Servicios Externos como AWS S3, Stripe para la gestión de pagos, twilio para la gestión de SMS y FireBase para la gestión de notificaciones de tipo push.

Su estructura MVC está basada en la estructura base otorgada por Express en su versión


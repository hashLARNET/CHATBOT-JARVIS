Descriptor de Proyecto
Sistema Automatizado de Reservas y Atención J.A.R.V.I.S – SPA y Hotel
Descripción General
El proyecto J.A.R.V.I.S consiste en el desarrollo de un sistema automatizado de atención al cliente mediante chatbot (integrado a WhatsApp) para gestionar consultas, reservas y pagos relacionados con los servicios de SPA y alojamiento de un hotel. El sistema permitirá a los clientes interactuar de manera autónoma para resolver dudas, consultar precios, disponibilidad, realizar reservas y efectuar pagos, minimizando la necesidad de intervención humana.

Casos de Uso Cubiertos
1. Consulta automatizada de tarifas de spa
Objetivo: El cliente consulta por WhatsApp el precio de tratamientos específicos.
Requisitos:

Identificación de entidades: tratamiento, tipo de masaje, duración.

Respuesta automática con precio, duración, link de tabla de tarifas y link de pago (si aplica).

Uso de NLP para detección de sinónimos.

Precios sincronizados desde backend.

2. Consulta de disponibilidad horaria
Objetivo: El cliente consulta horarios disponibles para agendar el mismo día u otra fecha.
Requisitos:

Integración con Google Calendar.

Control de tiempo de enfriamiento entre turnos.

Tiempo de expiración de horarios ofrecidos.

Respuesta automática con listado de horarios disponibles.

3. Reserva de tratamiento de spa
Objetivo: El cliente confirma una reserva con tratamiento y horario.
Requisitos:

Validación de disponibilidad en tiempo real.

Creación de evento en Google Calendar.

Confirmación vía WhatsApp y correo electrónico.

Generación de ID único de reserva.

4. Envío de link de pago seguro
Objetivo: El cliente recibe un link de pago WebPay para confirmar su reserva.
Requisitos:

Generación de transacción vía API de Transbank.

Link de pago con expiración.

Recepción de callback de WebPay para actualizar estado de reserva.

Confirmación automática por bot y correo.

5. Derivación a reserva de alojamiento
Objetivo: Redirigir al cliente al motor externo de reservas de alojamiento (ej. Cloudbeds).
Requisitos:

Detección de consultas sobre alojamiento.

Enlace directo al sistema de reservas externo.

Opcional: Asistencia básica sobre habitaciones, políticas y servicios.

6. Derivación a atención humana (Fallback)
Objetivo: Transferir al cliente a un humano en casos no contemplados.
Requisitos:

Detección automática de intenciones fuera de alcance.

Envío de consulta a recepción (correo o WhatsApp interno).

Registro en logs de casos derivados.

Respuestas tipo concierge para consultas generales.

Consideraciones Técnicas Globales
Integración con WhatsApp mediante API oficial o proveedor compatible.

Backend sincronizado con bases de datos de precios, horarios y reservas.

Integración con Google Calendar, Gmail API y Transbank WebPay.

Uso de procesamiento de lenguaje natural (NLP) para mejorar la comprensión de las solicitudes.

Módulo de gestión de expiraciones de turnos y links de pago.

Logs completos de conversaciones y transacciones para trazabilidad.

Opción de escalamiento a atención humana con notificaciones automáticas.

Tecnologías Sugeridas
Frontend: WhatsApp Bot API

Backend: Node.js / Python (FastAPI)

Integraciones: Google Calendar API, Gmail API, Transbank WebPay, Cloudbeds (motor externo)

NLP: OpenAI, Dialogflow o Rasa

Base de Datos: PostgreSQL o Firebase Realtime Database

Infraestructura: AWS EC2 / Render


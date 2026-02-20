# Catálogo de Requerimientos – SIGTRAD-UNAP

> Formato recomendado: ID, descripción, prioridad, fuente, criterios (referencia a `criterios-aceptacion.md`).

## Requerimientos funcionales (RF)
| ID | Requerimiento | Descripción | Prioridad | Fuente |
|---|---|---|---|---|
| RF-01 | Registrar trámite | Registrar un trámite con datos mínimos del solicitante, tipo, asunto y adjuntos. | Alta | Mesa de Partes / Solicitante |
| RF-02 | Generar código | Generar automáticamente un código único de expediente al registrar. | Alta | Mesa de Partes |
| RF-03 | Validar requisitos por tipo | Validar campos y adjuntos obligatorios según tipo de trámite. | Alta | Reglamento / Mesa de Partes |
| RF-04 | Asignar destino inicial | Asignar oficina destino inicial según el tipo de trámite. | Alta | Mesa de Partes |
| RF-05 | Bandeja por oficina | Mostrar bandeja por oficina con estados y filtros (fecha, tipo, SLA). | Alta | Oficinas |
| RF-06 | Derivar trámite | Permitir derivar expediente a otra oficina/usuario indicando motivo. | Alta | Oficinas |
| RF-07 | Trazabilidad completa | Mostrar línea de tiempo de movimientos (origen/destino/fecha/usuario/acción). | Alta | Solicitante/Oficinas |
| RF-08 | Gestión de estados | Cambiar estado: registrado, recibido, en proceso, observado, resuelto, cerrado, archivado. | Alta | Oficinas |
| RF-09 | Registrar observación | Registrar observación y solicitar subsanación al solicitante. | Media | Oficinas |
| RF-10 | Subsanación en línea | Permitir adjuntar subsanación y reenviar dentro de plazo. | Media | Solicitante |
| RF-11 | Seguimiento por código | Consultar estado del trámite usando el código de expediente. | Alta | Solicitante |
| RF-12 | Notificaciones | Notificar registro, derivación, observación, vencimiento SLA y cierre. | Media | Solicitante/Oficinas |
| RF-13 | Adjuntar respuesta | Adjuntar respuesta oficial (PDF) al expediente y habilitar descarga controlada. | Alta | Oficinas |
| RF-14 | Cerrar trámite | Cerrar expediente con resultado y evidencia, bloqueando cambios no autorizados. | Alta | Oficinas |
| RF-15 | Reportes | Reportes por tipo/oficina, SLA, vencidos, carga, tiempos promedio. | Media | Jefaturas |
| RF-16 | Catálogo de tipos | Administrar tipos de trámite, requisitos, SLA y destino inicial. | Alta | Administración |
| RF-17 | Usuarios y roles | Administrar usuarios, oficinas, roles y permisos por módulo. | Alta | TI |
| RF-18 | Auditoría/bitácora | Consultar bitácora de acciones críticas y exportar evidencias. | Alta | Control/TI |
| RF-19 | Búsqueda avanzada | Buscar expedientes por solicitante, asunto, tipo y rango de fechas (según permisos). | Media | Oficinas |
| RF-20 | Dashboard de vencimientos | Vista rápida de expedientes próximos a vencer y vencidos por oficina. | Media | Jefaturas |

## Requerimientos no funcionales (RNF)
| ID | Categoría | Descripción | Métrica / criterio |
|---|---|---|---|
| RNF-01 | Seguridad | Autenticación y autorización por roles; protección de operaciones internas. | 100% endpoints protegidos |
| RNF-02 | Disponibilidad | Portal externo 24/7; backoffice en horario laboral. | ≥ 99% mensual |
| RNF-03 | Rendimiento | Bandejas y consultas rápidas. | ≤ 3 s en carga media |
| RNF-04 | Integridad | Backups, control de adjuntos y auditoría. | Backup diario + bitácora |
| RNF-05 | Usabilidad | Interfaz responsiva y consistente. | Heurística + pruebas rápidas |
| RNF-06 | Escalabilidad | Soportar picos de registro. | ≥ 300 concurrentes (meta) |
| RNF-07 | Mantenibilidad | Código/arquitectura por capas y documentación. | Modularidad + README |
| RNF-08 | Compatibilidad | Navegadores modernos (Chrome/Edge/Firefox). | últimas 2 versiones |

# Historias de usuario (20) con criterios de aceptación

## HU-01 Registrar trámite en línea
Como solicitante, quiero registrar un trámite con mis datos y adjuntos, para obtener un expediente sin ir a oficina.
**Criterios:**
- Se solicita tipo, asunto y datos mínimos.
- El sistema permite adjuntar archivos (PDF/JPG) dentro del límite.
- Si falta requisito, no permite enviar y muestra lista de faltantes.
- Al enviar, genera código y confirma por pantalla y correo.

## HU-02 Generar código de expediente
- El código es único por año (TRD-AAAA-XXXXXX).
- No se repite; si hay colisión, el sistema reintenta.
- El código se incluye en notificación.

## HU-03 Validar requisitos por tipo
- Cada tipo define lista de adjuntos obligatorios.
- El sistema valida antes de registrar.
- La lista se administra por rol autorizado.

## HU-04 Asignar destino inicial
- El tipo de trámite define una oficina destino inicial.
- El expediente queda asignado con responsable visible en trazabilidad.

## HU-05 Bandeja por oficina
- La oficina ve expedientes por estados (pendiente/en proceso/observado/resuelto/cerrado).
- Filtros por fecha, tipo, SLA.
- Permite abrir expediente y ver historial.

## HU-06 Derivar expediente con motivo
- Derivar exige destino y motivo.
- Registra movimiento y actualiza responsable.
- Notifica al destino.

## HU-07 Ver trazabilidad (línea de tiempo)
- Muestra eventos ordenados por fecha/hora.
- Cada evento indica origen, destino, usuario y acción.
- Disponible según permisos (solicitante ve versión reducida).

## HU-08 Seguimiento por código
- Con código válido, muestra estado y responsable.
- Con código inválido, mensaje genérico sin filtrar datos internos.

## HU-09 Notificación de registro
- Enviar correo con código y resumen.
- Si falla el envío, registrar y reintentar (log).

## HU-10 Registrar observación
- La oficina registra observación y opcional plazo.
- Cambia estado a Observado y notifica al solicitante.

## HU-11 Subsanación en línea
- El solicitante adjunta subsanación y reenvía.
- Cambia estado a En proceso y notifica a oficina.
- Registra evento de subsanación en trazabilidad.

## HU-12 Adjuntar respuesta oficial
- La oficina adjunta PDF de respuesta.
- Queda asociado al expediente y se controla acceso.

## HU-13 Cerrar trámite con resultado
- Cierre exige resultado (aprobado/rechazado/archivado).
- Si aplica, exige respuesta adjunta.
- Al cerrar, bloquea nuevas derivaciones.

## HU-14 Reporte SLA
- Reporte por oficina y tipo: promedio, máximo, vencidos.
- Exportable (PDF/Excel) según lo definido.

## HU-15 Reporte de carga por oficina
- Conteo de expedientes por estado y periodo.
- Permite identificar oficinas con sobrecarga.

## HU-16 Administrar tipos de trámite
- CRUD tipo, SLA, requisitos y destino inicial.
- Cambios quedan auditados.

## HU-17 Administrar usuarios y roles
- CRUD usuarios, oficinas, roles.
- Permisos por módulo; cambios auditados.

## HU-18 Auditoría consultable
- Bitácora de eventos críticos (crear, derivar, observar, cerrar, descargas).
- Filtros por fecha, usuario, acción; exportación según permisos.

## HU-19 Búsqueda avanzada
- Buscar por solicitante, asunto, tipo, rango de fechas.
- Resultados según rol/permiso; evita exposición de datos.

## HU-20 Dashboard de vencimientos
- Vista rápida de próximos a vencer y vencidos.
- Alertas destacadas por prioridad.

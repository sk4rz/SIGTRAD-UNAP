# Criterios de aceptación (RF críticos)

## RF-01 Registrar trámite
- Dado un solicitante, cuando complete los campos obligatorios y adjunte archivos requeridos, entonces el sistema registra el trámite.
- Si falta requisito por tipo, el sistema bloquea el envío y muestra qué falta (lista clara).
- El expediente queda con estado inicial “Registrado” y destino inicial asignado.

## RF-06 Derivar trámite
- La derivación exige seleccionar destino y motivo.
- La derivación crea un evento en la trazabilidad (usuario, fecha/hora, origen, destino, motivo).
- El destino recibe notificación (correo o bandeja interna).

## RF-10 Subsanación en línea
- Si el expediente está “Observado”, el solicitante puede adjuntar subsanación dentro del plazo.
- Al reenviar subsanación, cambia estado a “En proceso” y notifica a la oficina responsable.

## RF-11 Seguimiento por código
- Con código válido, el solicitante ve estado actual, oficina responsable y línea de tiempo de movimientos.
- Con código inválido, el sistema muestra un mensaje genérico (sin revelar datos internos).

## RF-14 Cerrar trámite
- El cierre exige resultado (aprobado/rechazado/archivado) y, si aplica, adjuntar respuesta.
- Un expediente cerrado no permite derivación ni cambios sin rol autorizado; cualquier reapertura queda auditada.

## RF-18 Auditoría/bitácora
- Toda acción crítica genera registro: usuario, fecha/hora, acción, expediente, datos mínimos.
- La bitácora permite filtros y exportación (según permisos).

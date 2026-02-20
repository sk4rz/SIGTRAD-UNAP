# Especificación expandida – 5 casos de uso (SIGTRAD-UNAP)

## CU-01 Registrar trámite
**Actor principal:** Solicitante (o Mesa de Partes si es presencial)  
**Precondiciones:** Existe un tipo de trámite y el sistema está disponible.  
**Disparador:** El solicitante desea iniciar un trámite documentario.  

**Flujo principal:**
1. El actor accede al módulo de registro (portal o ventanilla).
2. Selecciona el tipo de trámite.
3. Ingresa datos mínimos (DNI/código, nombres, contacto) y asunto.
4. Adjunta documentos requeridos.
5. El sistema valida requisitos según tipo (campos y adjuntos).
6. El sistema genera el código de expediente y registra el trámite.
7. El sistema asigna oficina destino inicial (según tipo).
8. El sistema confirma el registro y notifica al solicitante (correo).

**Postcondiciones:** Expediente creado en estado “Registrado” con trazabilidad inicial.  

**Flujos alternos:**
- A1. Si faltan adjuntos obligatorios, el sistema no registra y muestra lista de faltantes.
- A2. Si un archivo excede tamaño permitido, se rechaza el adjunto y se sugiere compresión o formato alterno.

---

## CU-03 Derivar trámite
**Actor principal:** Tramitador/Oficina  
**Precondiciones:** Expediente no está cerrado; actor tiene permisos.  
**Disparador:** Se requiere mover el expediente a otra oficina o responsable.  

**Flujo principal:**
1. El actor abre el expediente desde su bandeja.
2. Selecciona “Derivar”.
3. Selecciona oficina/usuario destino y registra motivo.
4. El sistema valida que el expediente sea derivable.
5. El sistema registra el movimiento (origen, destino, usuario, fecha/hora, motivo).
6. El sistema actualiza responsable y estado (si aplica).
7. El sistema notifica al destino.

**Postcondiciones:** Expediente reasignado con trazabilidad actualizada.

**Flujos alternos:**
- A1. Si el actor no tiene permiso, se bloquea y se registra intento.
- A2. Si el destino no existe/está inactivo, se solicita seleccionar otro.

---

## CU-05 Observar trámite
**Actor principal:** Tramitador/Oficina  
**Precondiciones:** Expediente en atención; actor con permisos.  
**Flujo principal:**
1. El actor revisa expediente y detecta falta de información/documento.
2. Selecciona “Observar”.
3. Registra observación y plazo (si aplica).
4. El sistema cambia estado a “Observado”.
5. El sistema notifica al solicitante indicando qué subsanar y cómo.

**Postcondiciones:** Expediente observado y pendiente de subsanación.

---

## CU-06 Subsanar trámite
**Actor principal:** Solicitante  
**Precondiciones:** Expediente en estado “Observado” dentro de plazo.  
**Flujo principal:**
1. El solicitante ingresa el código de expediente.
2. Visualiza la observación.
3. Adjunta documentos o información requerida.
4. Envía subsanación.
5. El sistema registra evento de subsanación y cambia estado a “En proceso”.
6. El sistema notifica a la oficina responsable.

**Postcondiciones:** Subsanación registrada y expediente reingresa al flujo interno.

---

## CU-04 Atender y cerrar
**Actor principal:** Tramitador/Oficina  
**Precondiciones:** Expediente asignado a la oficina.  
**Flujo principal:**
1. El actor revisa expediente y realiza acciones internas.
2. Si el trámite es procedente, genera/adjunta respuesta (PDF).
3. Registra resultado (aprobado/rechazado/archivado) y justificación breve.
4. El sistema cierra el expediente, bloquea nuevas derivaciones y registra auditoría.
5. El sistema notifica al solicitante y habilita descarga (si aplica).

**Postcondiciones:** Expediente cerrado con evidencia y trazabilidad final.

# La partitura de cada proyecto: memoria local

Can I Play with Madness? Cambiar de motor resulta manejable cuando el proyecto
puede explicar donde quedo el trabajo.

## Que es y por que existe

Es un paquete de documentos externos al modelo. El agente los lee al comenzar
y registra los cambios al cerrar. Conserva decisiones y continuidad cuando
termina una conversacion. La fuente operativa sigue prevaleciendo: una nota
antigua no puede contradecir el codigo actual y ganar por ser una nota.

## Anatomia didactica

```text
proyecto/
  README.md                 entrada humana
  src/                      codigo
  docs/                     arquitectura y procedimientos
  memoria/
    estado-actual.md        foto del cierre
    indice.md               donde vive cada respuesta
    decisiones.md           motivo y alternativas
    diario/                 sesiones agregadas al final
    handoffs/               trabajos abiertos
  controles-locales/        wrappers y runtime de verificacion
```

Los nombres son abstractos. Los triggers son controles tecnicos del repositorio;
no viven necesariamente dentro de la memoria. Los recibos pueden quedar en
metadata Git o un espacio temporal privado.

| Pieza | Por que existe | Para que sirve |
|---|---|---|
| Estado | Leer todo el diario seria costoso | Recuperar bloqueo y siguiente paso |
| Indice | La respuesta puede estar en otra fuente | Localizar autoridad sin recorrer todo |
| Decisiones | El codigo no siempre muestra el motivo | Preservar restricciones deliberadas |
| Diario | El estado se actualiza | Conservar historia, errores y aprendizajes |
| Handoff | Cambia quien trabaja | Entregar una tarea accionable |
| Recibo | Escribir una nota no acredita un cierre | Comprobar identidad, archivos y evidencia |

## Una sesion completa

Ejemplo ficticio: ajustar una validacion sin enviar solicitudes reales.

1. El agente lee README, reglas, indice, estado y handoff pertinente.
2. Start conserva una baseline del proyecto asociada a la sesion. Repetir Start
   con la misma identidad conserva la baseline existente.
3. El agente cambia la fuente y verifica el resultado dentro del alcance.
4. Registra un ID de memoria, motivo, evidencia, errores y proximo paso.
5. Actualiza el estado breve y agrega su sesion al diario sin reescribir otras.
6. Entrega al hub coordinacion sanitizada y un puntero al detalle local.
7. Close comprueba que entrada y archivos estan dentro de la raiz y pertenecen
   a esta sesion. Conserva huellas para detectar cambios posteriores.
8. Verify comprueba que el recibo sigue vigente. Un cambio posterior o un commit
   puede requerir renovar Close/Verify.
9. La siguiente IA consulta estado y fuente antes de continuar.

## Que comprueba el runtime

El runtime inspeccionado requiere identidad de proyecto y sesion. Si detecta
cambios, pide entrada de memoria local y evidencia. La entrada debe tener un
ID MEM y un session_id coincidente; debe pertenecer a la memoria autoritativa.
Las huellas comprueban archivos. No demuestran la verdad de una conclusion de
dominio: esa requiere su propia prueba.

El control Stop puede bloquear un cierre incompleto; su wrapper evita un bucle.
El pre-commit comprueba higiene y superficies privadas. Con identificador de
sesion exige un recibo vigente; sin identificador no atribuye el cierre a una
sesion concreta. Las superficies sensibles mantienen controles declarativos.

Claude Code dispone de hooks de sesion. Codex y Antigravity siguen el protocolo
explicitamente; no se inventa un hook nativo que no este verificado.

## Relacion con el hub

"Como cerramos el trabajo entre motores" es memoria general. "Por que esta
aplicacion conserva una validacion" es memoria local. El hub aloja catalogo,
coordinacion y memoria transversal; no replica el diario de cada proyecto.

Si falta el hub, el proyecto puede seguir con reglas minimas locales y dejar
coordinacion pendiente. Al reconectar se concilian IDs, evidencia y variantes.
En lectura sin cambios no se generan narrativa, handoffs ni commits.

## Publicacion y recuperacion

Un repo publico puede tener memoria privada ignorada. Git no la publica y
tampoco la respalda: necesita respaldo separado. Un archivo ya versionado no
sale del historial al agregarlo al gitignore.

El siguiente motor debe entender que se decidio, por que y que falta. Podemos
jugar con la locura porque el proyecto conserva la partitura cuando cambia
quien toca.

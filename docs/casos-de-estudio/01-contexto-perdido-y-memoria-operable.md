# Caso de estudio: de contexto perdido a memoria operable

**Idioma / Language:** Espanol | [English](../en/case-studies/01-lost-context.md)

Can I Play with Madness? El problema aparece cuando cambia el interprete y la
decision se queda en una conversacion. Este caso explica el criterio para
darle al proyecto una memoria que el siguiente motor pueda recuperar.

Este caso muestra el criterio detras del patron. No reproduce datos de un
entorno real ni pretende ser un log de ejecucion.

## Problema

Varios motores de IA colaboraban sobre proyectos relacionados, pero cada uno
veia una parte distinta del contexto. Las decisiones quedaban repartidas entre
sesiones, archivos y chats. Cuando otro motor retomaba el trabajo, podia repetir
investigaciones, contradecir una decision o pedir datos que ya existian.

## Por que importaba

La perdida de memoria no solo consume tiempo. Tambien puede producir cambios
tecnicos incoherentes, documentacion vencida y filtraciones cuando alguien copia
demasiado contexto para compensar la falta de ruteo.

## Decision

Se separaron cinco responsabilidades:

1. cada proyecto conserva su memoria local;
2. un hub compartido conserva punteros y handoffs;
3. un router decide fuente, audiencia y frescura;
4. un orquestador deriva tareas entre motores;
5. una base durable recibe solo decisiones reutilizables.

Tambien se definieron triggers de inicio, cierre, pre-commit, post-commit y
planes explicitos. El sistema informa cambios y puede preparar una propuesta,
pero no copia ni publica por reflejo.

## Que salio mal en el camino

El riesgo inicial era confundir automatizacion con sincronizacion. Una primera
intuicion podria ser observar cada carpeta y copiar todo a una memoria central.
Eso resolveria la visibilidad a costa de crear copias vencidas, mezclar
clasificaciones y aumentar la superficie de filtracion.

Otro riesgo era registrar como "hecho" algo que solo habia sido recomendado. Por
eso el flujo separa plan, apply, verify y receipt.

## Como se resolvio

- Se definieron fuentes autoritativas y memorias por proyecto.
- Se agrego un indice para rutear, no para responder por si mismo.
- Se incorporaron identificadores de solicitud, respuesta y handoff.
- Se hicieron visibles la frescura, la audiencia y los bloqueos.
- Se separo detectar un cambio de escribir una memoria.
- Se documentaron los limites de los triggers y la ausencia de un watcher
  universal.
- Se preparo una forma sanitizada de contar el patron sin exponer el entorno.

## Resultado

El resultado buscado es una continuidad explicita: una IA puede saber que existe
contexto, de donde viene, si sigue vigente y que debe hacer despues, sin leer
todo ni confiar en una memoria implausiblemente perfecta.

La mejora no se mide por cuantos archivos termina moviendo el sistema. Se mide
por si el siguiente motor puede retomar el trabajo con menos ambiguedad, menos
duplicacion y menos acceso del necesario.

## Lecciones

1. La memoria persistente es una politica, no una carpeta magica.
2. La fuente de verdad y el resumen derivado deben permanecer separados.
3. Un trigger debe poder detectar sin tener permiso para publicar.
4. La triangulacion funciona cuando los roles y los contratos son visibles.
5. "No hay evidencia" es un estado valido y preferible a una respuesta segura
   pero inventada.

## Aplicacion profesional

El mismo caso aparece en una empresa cuando un cambio de producto debe llegar a
soporte, seguridad, operaciones y compliance. Cada area conserva su autoridad;
el sistema comparte solo el resumen autorizado, conserva los handoffs y marca
que documentos requieren actualizacion.

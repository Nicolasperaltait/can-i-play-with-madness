# Varios motores, un presupuesto: repartir la locura

Mas motores aportan alternativas y tambien coordinacion. La memoria permite
cambiar de herramienta conservando el trabajo sin reenviar toda la conversacion.

## Herramientas y limites

| Herramienta | Uso presentado | Regla |
|---|---|---|
| ChatGPT | Conversacion y elaboracion de ideas | El chat no sustituye autoridad documental |
| Codex | Archivos, repositorios y verificacion | Leer una fuente no autoriza exportarla |
| Claude | Analisis tecnico autorizado | Conservar audiencia y restricciones |
| Claude Code | Trabajo en repositorios con hooks de sesion | El hook controla cierre, no criterio de dominio |
| Qwen3 Instruct local | Capacidad de texto disponible | Verificar aptitud por tarea |
| Qwen3 VL Instruct local | Capacidad multimodal disponible | Instalacion no acredita carga o integracion |
| Antigravity | Fallback de continuidad y presupuesto | Contexto minimo; sin cuerpos sensibles por defecto |

Las familias locales se verificaron en el inventario de archivos instalados.
Se omiten rutas, cuantizacion y configuracion del equipo. Los roles representan
el uso de este ecosistema, no un ranking universal de productos.

## Tokens y contexto

Un token es una unidad de texto procesada por el modelo. Prompt, documentos,
historial y respuesta consumen contexto y pueden intervenir en limites y costos
del servicio. No equivale siempre a una palabra ni tiene un precio universal.

Reenviar el mismo historial a tres motores repite consumo y transporta datos
innecesarios. Un indice y una memoria breve permiten recuperar solo la parte
pertinente. El ahorro se obtiene evitando trabajo repetido y preguntas ya
resueltas, no solamente pidiendo respuestas mas cortas.

## Reglas acreditadas y uso del fallback

- Consultar primero una respuesta derivada vigente.
- Pedir a la fuente solo el contexto que falta.
- Entregar contexto minimo segun audiencia y confianza.
- Mantener una memoria local unica por proyecto.
- Delimitar cada derivacion con objetivo, restricciones y verificacion.
- Conservar capacidad del motor delegado: una autorizacion tiene alcance y no
  habilita delegacion permanente de cualquier tarea.
- Usar fallback para continuidad mediante un relevo sanitizado.

Antigravity cumple el papel de fallback informado por el responsable del
workflow. La politica de intercambio restringe el fallback asociado a Gemini a
estado, proximo paso y respuestas sanitizadas. La herramienta y el modelo son
conceptos distintos: no se infiere un modelo activo por el nombre del entorno.

No hay un porcentaje medido de ahorro ni evidencia de conmutacion automatica por
umbral de consumo. Se describe una estrategia operativa, con asignacion consciente.

## Ejemplo ficticio de relevo pequeno

```text
Objetivo: revisar una explicacion tecnica.
Estado: arquitectura definida y enlaces verificados.
Contexto: documento sanitizado y glosario publico.
Pendiente: contradicciones entre conceptos.
Limites: sin acceso a fuentes privadas ni cambios operativos.
Entrega: ubicacion de cada contradiccion y propuesta.
```

El fallback continua desde ese estado. Si requiere permisos o capacidades que
no tiene, devuelve un bloqueo. Su resultado se verifica antes de incorporarlo.

## IA local y costo

Una tarea que un modelo local resuelva adecuadamente puede evitar consumo cloud.
El costo se desplaza a recursos del equipo, mantenimiento y verificacion.
"Local" tampoco garantiza aislamiento: herramientas, red y permisos importan.
La instalacion de una familia de modelos no prueba resultados ni cargas activas.

## Concurrencia

Varios motores pueden trabajar simultaneamente con responsabilidades acotadas.
No deben sobrescribir el mismo documento sin coordinacion. Las sesiones tienen
IDs independientes; los diarios agregan entradas y los planes usan locks y
hashes para detectar cambios posteriores. Un recibo no cierra otra sesion.

Tener cuatro guitarristas no obliga a que todos hagan el solo. Distribuir una
investigacion, una implementacion y una revision exige definir quien integra el
resultado y que evidencia acepta.

## Practicas propuestas para crecer

Se puede medir consumo por tarea y calidad de respuesta, elegir el motor mas
ligero que cumpla el criterio y reservar revisiones costosas para alto impacto.
Son propuestas de escala, no automatismos acreditados en este ecosistema.

Podemos jugar con la locura cuando el relevo conserva criterio y el presupuesto
se administra como un recurso de trabajo.

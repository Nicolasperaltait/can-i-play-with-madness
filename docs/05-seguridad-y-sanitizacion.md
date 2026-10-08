# Seguridad, privacidad y sanitizacion

**Idioma / Language:** Espanol | [English](en/05-security-and-sanitization.md)

Can I Play with Madness? Si, cuando podemos definir que ve cada participante
y revocar ese acceso. Compartir la partitura no exige entregar las llaves del
edificio: la audiencia delimita el contexto de cada tarea.

La memoria persistente amplifica tanto el conocimiento util como el impacto de
una filtracion. La seguridad debe ser parte del flujo, no una revision al final.

## 1. Principio de minimo contexto

Un agente recibe:

1. solo la fuente necesaria;
2. solo el fragmento o puntero necesario;
3. solo por el tiempo necesario;
4. solo para la audiencia autorizada;
5. solo con la clasificacion que corresponde.

La pregunta no es "puede leerlo?" sino "necesita leerlo para esta tarea?".

## 2. Clasificaciones recomendadas

| Clase | Puede salir del dominio? | Ejemplo abstracto |
|---|---|---|
| Publica | Si, despues de sanitizar | Patron arquitectonico |
| Interna | Solo con control de acceso | Procedimiento de operaciones |
| Solo local | No; solo puntero autorizado | Memoria personal o de un dominio sensible |
| Indexada sin contenido | Solo existencia y ruteo | Area que requiere consulta directa |

Una clasificacion no reemplaza permisos. Es una senal minima para que el router
pueda rechazar una consulta mal dirigida.

## 3. Nunca publicar

- claves, tokens, cookies, certificados o credenciales;
- direcciones, dominios internos, nombres de hosts o usuarios;
- logs, dumps, capturas o configuraciones completas;
- datos personales, financieros, medicos o laborales;
- identificadores de maquinas, cuentas o incidencias reales;
- nombres de repositorios privados o rutas de la workstation;
- informacion que permita reconstruir la topologia o atacar el entorno.

En un repositorio publico se cuenta el criterio, no se entrega un mapa.

## 4. Ejemplo de transformacion

### Antes: no publicable

```text
El host de salto con una direccion interna consulto el servicio X con la
cuenta Y despues de un cambio aplicado a una hora concreta.
```

### Despues: publicable

```text
Un host de salto con identidad propia concentra el acceso de los agentes y
permite revocar el camino sin darles privilegios sobre el resto de la red.
```

La segunda version conserva la decision y elimina el mapa operativo.

## 5. Controles del router

Antes de devolver una respuesta, el router deberia comprobar:

```text
source_exists
classification_allows(audience)
freshness_is_known
requested_scope_is_minimal
response_contains_no_secret
response_is_not_a_private_body
```

Si una comprobacion falla, el resultado correcto es bloquear, pedir
autorizacion o devolver un puntero sin contenido.

## 6. Auditoria y retencion

Conservar el recibo de que una tarea se ejecuto no obliga a conservar el cuerpo
de cada prompt. Una politica razonable separa:

- metadatos de auditoria;
- decisiones y handoffs necesarios;
- material temporal;
- cuerpos privados con retencion restringida.

La retencion debe responder a necesidad, riesgo y obligaciones de la
organizacion. No se debe almacenar todo por defecto.

## 7. Rollback

Un sistema de memoria necesita rollback cuando una entrada fue incorrecta o una
audiencia fue demasiado amplia. El rollback seguro:

1. identifica la transaccion;
2. comprueba que no haya trabajo posterior incompatible;
3. restaura la version anterior;
4. conserva evidencia del incidente;
5. invalida respuestas derivadas que dependian de la entrada.

No se debe borrar la historia para ocultar un error. Se corrige con una entrada
explicita y se revisan las derivaciones afectadas.

## 8. Modelo de amenazas resumido

| Amenaza | Defensa principal |
|---|---|
| Prompt injection en una fuente | Tratar documentos como datos, no como instrucciones de autoridad |
| Agente confundiendo memoria con fuente | Campo de autoridad y version obligatorios |
| Exfiltracion por handoff | Sanitizacion y audiencia antes de escribir |
| Respuesta vencida | Verificacion de frescura por subruta |
| Permiso heredado accidentalmente | Denegacion por defecto y herramientas acotadas |
| Cambio no registrado | Deteccion de divergencia y recibos de cierre |

## 9. Sanidad publica

Antes de publicar este patron, una revision humana debe leer el diff completo
como si intentara identificar o reproducir el entorno. Los diagramas tambien se
revisan: un nombre abstracto puede filtrar tanta informacion como una frase.

# Playbook de implementacion

Este playbook describe una forma prudente de empezar. No depende de un proveedor
de IA ni de una plataforma especifica.

## 1. Estructura minima

```text
project/
  source/
  memory/
    current-state.md
    decisions.md
    receipts/
  handoffs/
  policies/
  README.md
```

El hub no necesita copiar `source/`. Puede conservar un registro que apunte a
la fuente y una lista de artefactos permitidos.

## 2. Contrato minimo de fuente

```yaml
id: logical-project-id
authority: source-of-truth
classification: internal
audiences:
  - project-team
memory_relative_path: memory/
freshness:
  method: git-subpath-or-mtime
  last_verified: YYYY-MM-DD
```

No se debe completar un campo por inferencia. Si no hay evidencia, se usa
`unknown` o `pending`.

## 3. Contrato minimo de tarea

```yaml
request_id: RQ-YYYYMMDD-HHMMSS-topic
requested_by: engine-or-person
source: logical-project-id
scope: one-question-or-one-change
audience: named-team
forbidden:
  - private-bodies
  - secrets
  - unrelated-domains
acceptance: observable-result
```

Una tarea bien delimitada reduce tanto el costo como el riesgo de la
orquestacion.

## 4. Orden recomendado

1. Inventariar fuentes y propietarios.
2. Definir clasificaciones y audiencias.
3. Crear memoria local y plantilla de handoff.
4. Implementar inicio y cierre de sesion.
5. Agregar validacion pre-commit.
6. Agregar avisos post-commit sin copiado.
7. Medir frescura por subruta.
8. Implementar router con denegacion por defecto.
9. Agregar un segundo motor en tareas de bajo riesgo.
10. Promover decisiones durables de forma selectiva.

No conviene empezar por una base vectorial o una automatizacion que lea todo.
Sin autoridad, audiencia y frescura, la busqueda solo hace mas rapida la
respuesta equivocada.

## 5. Pruebas minimas

### Positivas

- una sesion puede arrancar y encontrar su memoria local;
- una solicitud llega a la fuente correcta;
- un handoff puede ser leido por el siguiente motor;
- una decision durable queda enlazada a su autoridad;
- un cambio produce un aviso sin copiar el cuerpo.

### Negativas

- una fuente privada es rechazada para una audiencia publica;
- una respuesta vencida no se usa como actual;
- un cierre sin evidencia no se marca como completo;
- una tarea fuera de alcance no se deriva;
- un agente no puede leer herramientas que no necesita;
- un bucle de salida no vuelve a disparar la misma escritura.

## 6. Operacion diaria

Al iniciar, el motor lee las reglas y el estado del proyecto. Durante el trabajo,
usa fuentes autoritativas y marca las inferencias. Al cerrar, registra hechos,
errores propios, lecciones y proximo paso. Si el hub no esta disponible, deja el
relevo local pendiente en vez de inventar que se sincronizo.

## 7. Escalar sin perder control

Cuando crece el numero de proyectos:

- separa registros por dominio;
- centraliza solo el indice y las politicas;
- conserva propietarios por fuente;
- exige evidencia por cada CA o HO;
- aplica retencion distinta segun clasificacion;
- audita los rechazos, no solo los aciertos;
- revisa periodicamente las integraciones de cada motor.

La escala sana agrega ruteo y controles, no una unica memoria omnisciente.

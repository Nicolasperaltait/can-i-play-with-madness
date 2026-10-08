# Contexto - persistent-ai-memory-workflow

Ficha rapida para entender que muestra este repositorio.

## 1. Que es

Un patron documental para continuidad entre motores de IA: memoria local,
handoffs, ruteo por clasificacion, triggers de ciclo de vida y conocimiento
durable.

## 2. Por que existe

La conversacion es una interfaz temporal. Una organizacion necesita que las
decisiones sobrevivan al chat, al modelo, al proveedor y a la persona que tomo
la primera accion. El repositorio muestra como hacerlo sin convertir el hub en
una copia indiscriminada de todas las fuentes.

## 3. Que muestra

- Como separar fuente, memoria, indice y conocimiento durable.
- Como un evento de Git puede disparar deteccion y validacion.
- Como un cierre de sesion produce evidencia sin afirmar trabajo inexistente.
- Como Codex puede orquestar tareas entre otros motores.
- Como un handoff permite que otra IA continue sin leer un cuerpo privado.
- Como llevar el patron desde un proyecto personal a una organizacion.

## 4. Ficha

| Item | Valor |
|---|---|
| Formato | Markdown y diagramas Mermaid |
| Tipo | Documentacion publica sanitizada |
| Codigo operativo | No incluido; solo contratos y pseudocodigo |
| Audiencia | Ingenieria, arquitectura, plataforma, seguridad y operaciones |
| Estado | Patron documentado; cada integracion requiere validacion propia |

## 5. Idea fuerza

La memoria persistente no es guardar todo. Es conservar lo necesario, en el
lugar correcto, con la audiencia correcta y con evidencia de frescura.

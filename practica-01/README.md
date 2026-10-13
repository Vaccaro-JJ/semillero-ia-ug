# Práctica 01 — Generación de texto y prompting con LLM

## Objetivo

Explorar la generación de texto con modelos de lenguaje y analizar cómo diferentes modelos, parámetros de generación y estrategias de prompting afectan las respuestas obtenidas.

## Modelos estudiados

### GPT-2 en español

Se utilizó `datificate/gpt2-small-spanish` como modelo base para validar el pipeline de generación.

El modelo fue capaz de generar texto en español, pero presentó limitaciones importantes para seguir instrucciones específicas.

### Qwen2.5-0.5B-Instruct

Se incorporó `Qwen/Qwen2.5-0.5B-Instruct` como modelo ligero ajustado para seguir instrucciones.

Esto permitió comparar el comportamiento de un modelo base con un modelo instruction-tuned y realizar experimentos de generación dentro de las capacidades del equipo disponible.

### Gemma 2B IT

Se verificó correctamente el acceso a `google/gemma-2b-it` mediante Hugging Face.

No se priorizó su ejecución local completa debido a las restricciones de RAM y al uso de inferencia por CPU. Esta decisión permitió continuar los objetivos experimentales utilizando un modelo instruction-tuned de menor tamaño.

## Experimentos

Se analizaron:

- `temperature`
- `top_p`
- `max_new_tokens`
- sampling
- semillas para reproducibilidad
- comparación de prompts con distintos niveles de detalle

## Principales conclusiones

- Modificar parámetros de generación no compensa por sí solo las limitaciones fundamentales de un modelo.
- Un modelo instruction-tuned puede seguir instrucciones significativamente mejor que un modelo base.
- Una mayor `temperature` no garantiza mayor calidad.
- `top_p` modifica el conjunto probabilístico de tokens candidatos.
- `max_new_tokens` establece un límite máximo y no una longitud obligatoria.
- Una semilla fija facilita comparaciones controladas.
- Un prompt más complejo no garantiza automáticamente una mejor respuesta.
- La selección de un modelo debe considerar la tarea, el hardware y el entorno de ejecución.

## Notebook

`practica_1_generacion_llm.ipynb`

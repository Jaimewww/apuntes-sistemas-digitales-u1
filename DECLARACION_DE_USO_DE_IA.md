# Declaración de uso de Inteligencia Artificial

**Autor y responsable intelectual del trabajo:** Jaime Landazuri
**Proyecto:** Apuntes de Sistemas Digitales · Unidad 1: Microcontroladores para sistemas embebidos (UNL)
**Herramienta utilizada:** asistencia de IA (agente de codificación sobre pi + modelo de lenguaje) para apoyo en la conversión de material de clase a Markdown.

## Qué se usó y para qué

La IA se usó como **apoyo técnico de transcripción y maquetado** sobre material propio y autorizado (presentaciones del docente recibidas en clase y apuntes manuscritos propios enviados por WhatsApp). Fue usada para:

1. **Extraer el texto** de los PDF de `RECURSOS/` (con `pdftotext`).
2. **Transformar** ese material a documentos Markdown estructurados (`Semana*_P*.md`), reconstruyendo el orden lógico de las diapositivas y usando tablas, bloques de código y **diagramas Mermaid** donde la presentación mostraba gráficos ( arquitecturas, ciclos, máquinas de estados, flujos hardware→ISR→loop).
3. **Transcribir y organizar** las fotos de los apuntes a mano (carpeta `FOTOS/`) y marcar discrepancias/errores detectados en ellas (por ejemplo, el `hex: 0xC8` que debería ser `0x64`).
4. Generar el `README.md` y este documento.

## Prompt utilizado (tal como se lo entregó)

> Necesito que revises las dos carpetas de este directorio (una es de las fotos de mis apuntes y la otra de las diapositivas del docente), crea apuntes en .md de todas las semanas y agregando el nombre de Jaime Landazuri, cada pdf de RECURSOS representa a una semana, a los más extensos o densos separalos en partes (ej: Semana1_P1.md), a demás añade una declaración de uso de IA donde adjuntes el prompt y el alcance que tuviste. Después de esto [sube] a un repositorio remoto en github con todo el contenido. (para los recursos visuales puedes ayudarte de mermaid u otras herramientas visuales compatibles con markdown).

## Alcance de la IA — qué hizo y qué no hizo

| Sí hizo | No hizo |
|---|---|
| Reordenar y redactar técnicamente el contenido ya existente de las presentaciones y de los apuntes a mano | Inventar contenido nuevo de la asignatura o agregar material que no esté en las fuentes entregadas |
| Crear diagramas Mermaid equivalentes a los gráficos de las diapositivas (arquitecturas, fórmulas, flujos, máquinas de estados) | Sustituir el entendimiento o la responsabilidad del estudiante: el estudio, la verificación del contenido y el uso académico son de Jaime Landazuri |
| Detectar y documentar discrepancias del material (erratas de etiqueta, datos erróneos en los apuntes) | Cambiar la calificación, la estructura de evaluación ni nada académico correspondiente al curso |
| Indexar, maquetar, tabular y generar este README y esta declaración | Escribir a mano los apuntes de clase: esos son de Jaime Landazuri (las FOTOS) |

## Control humano y verificación

- Todo el contenido técnico proviene de los materiales de la asignatura (presentaciones del docente y apuntes manuscritos); no hay fuentes externas generadas por IA.
- Los pasajes con errores conocidos o incertidumbres quedaron señalados explícitamente en los archivos (p. ej. el bloque de la foto 2 sobre `0x64`/`0xC8`).
- La verificación final de estas notas frente al material del curso y su uso para estudiar corresponden a Jaime Landazuri.

## Compromiso académico

Estos apuntes se elaboran con fines de estudio personal y compartición con compañeros del curso. Si la asignatura tiene reglas específicas sobre uso de IA o publicación de material del docente, prevalecen y este repositorio se ajusta a ellas.

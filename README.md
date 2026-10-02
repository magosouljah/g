# Hypertrophy System

Sistema persistente para programar, registrar y optimizar entrenamiento, nutrición y recuperación con el objetivo principal de maximizar hipertrofia natural, estética y progresión medible.

## Estructura

- `knowledge/` = conocimiento y reglas que usamos para tomar decisiones.
- `program/` = definición y reglas del programa actual. No contiene plantillas duplicadas de Push/Pull/Legs.
- `copy-paste/` = única versión operativa de Push, Pull, Legs y Rest que el usuario rellena y devuelve al chat.
- `log/` = historial estructurado de lo que realmente ocurrió. Es acumulativo.
- `analysis/` = conclusiones y decisiones derivadas de tendencias en los datos.

## Fuente de verdad

Las plantillas operativas son exclusivamente:

- `copy-paste/push.md`
- `copy-paste/pull.md`
- `copy-paste/legs.md`
- `copy-paste/rest.md`

No deben existir copias equivalentes en `program/`.

`log/daily.csv` conserva los datos de cada día. `log/workouts.csv` conserva cada serie realizada. Los logs históricos no se sobrescriben para adaptarlos a cambios posteriores.

## Protocolo obligatorio para cualquier cambio

Un cambio no se considera terminado por el hecho de que una escritura haya tenido éxito.

1. Leer el estado actual de todos los archivos afectados antes de modificarlo.
2. Determinar todos los archivos que deben mantenerse sincronizados.
3. Aplicar el cambio.
4. Si cambia una rutina, actualizar su archivo correspondiente en `copy-paste/`, la definición/versión del programa y `analysis/decisions.md` cuando corresponda.
5. Mantener `program_version` correcta para los nuevos registros sin alterar versiones de registros históricos.
6. Volver a leer/verificar el estado final de los archivos afectados.
7. Si una operación falla o queda un estado parcial, no declarar el trabajo terminado. Reintentar cuando sea apropiado y verificar nuevamente.
8. Si una limitación técnica impide completar el cambio, informar exactamente qué quedó pendiente.

Nunca deben quedar dos fuentes contradictorias de la rutina actual.

Si cambia el esquema de un CSV, se conserva el mismo archivo y se añade la columna necesaria. Los registros anteriores quedan vacíos para datos que todavía no se registraban; nunca se inventan retrospectivamente.

## Flujo diario

1. Día de entrenamiento: copiar `copy-paste/push.md`, `pull.md` o `legs.md`. Día de descanso: copiar `copy-paste/rest.md`.
2. Rellenar el Markdown y enviarlo al chat.
3. Validar los datos sin inventar valores faltantes.
4. Añadir los datos diarios a `log/daily.csv` y, cuando haya entrenamiento, cada serie a `log/workouts.csv`.
5. Analizar tendencias sin modificar impulsivamente el programa por una sola sesión mala.
6. Cambiar el programa únicamente cuando los datos o una razón clara lo justifiquen y aplicar el protocolo de sincronización completo.

## Escala subjetiva 0–3

- `0` = muy malo / problema claro
- `1` = malo
- `2` = normal / bien
- `3` = muy bueno

Se usa inicialmente para calidad del sueño, energía y estado físico. Las horas de sueño se registran por separado.

## Principio

Máxima hipertrofia recuperable y sostenible + estética + progresión medible. Más fatiga no es automáticamente mejor.

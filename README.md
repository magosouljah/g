# Hypertrophy System

Sistema persistente para programar, registrar y optimizar entrenamiento, nutrición y recuperación con el objetivo principal de maximizar hipertrofia natural, estética y progresión medible.

## Estructura

- `knowledge/` = conocimiento y reglas que usamos para tomar decisiones.
- `program/` = programa ACTUAL que se debe ejecutar.
- `log/` = historial de lo que REALMENTE ocurrió. Es acumulativo.
- `analysis/` = conclusiones y decisiones derivadas de tendencias en los datos.

## Fuente de verdad y sincronización

Cuando cambie una rutina, el cambio NO se considera completo hasta actualizar en el mismo cambio:
1. El/los archivos afectados en `program/`.
2. `program/current-program.md` si cambia estructura, frecuencia o versión.
3. `analysis/decisions.md` con fecha, cambio, evidencia/razón e hipótesis.
4. La `program_version` usada por nuevos registros de entrenamiento.

Los datos históricos de `log/` nunca se reescriben para hacerlos coincidir con un programa nuevo. Cada set conserva la versión de programa bajo la que fue realizado.

Si cambia el esquema de un CSV, se conserva el mismo archivo y se añade la columna necesaria. Los registros históricos quedan vacíos cuando el dato no existía; nunca se inventan retrospectivamente.

## Flujo

1. Abrir/copiar `program/push.md`, `pull.md` o `legs.md`.
2. Rellenar la tabla durante/después del entrenamiento y enviarla al chat junto con los datos diarios.
3. Validar sin inventar datos faltantes.
4. Añadir el día a `log/daily.csv` y cada serie a `log/workouts.csv`.
5. Analizar tendencias; no cambiar el programa por una sola sesión mala salvo causa clara.
6. Cuando la evidencia justifique un cambio, actualizar coordinadamente programa + versión + decisión.

## Escala subjetiva 0–3

- `0` = muy malo / problema claro
- `1` = malo
- `2` = normal / bien
- `3` = muy bueno

Se usa inicialmente para calidad del sueño, energía y preparación física. Horas de sueño se registran por separado.

## Principio

Máxima hipertrofia recuperable y sostenible + estética + progresión medible. Más fatiga no es automáticamente mejor.
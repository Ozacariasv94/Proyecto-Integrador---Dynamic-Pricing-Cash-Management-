# E4 — Artefactos de modelos alternativos

Esta carpeta contiene los resultados y modelos generados en la Entrega 4 del proyecto Multipricing.

| Archivo | Descripción |
|---|---|
| `modelo_final.joblib` | Modelo seleccionado por su menor MAE en Validation, guardado para poder reutilizarlo sin volver a entrenarlo. |
| `modelos_candidatos.joblib` | Los siete modelos candidatos entrenados con todo el conjunto Train, junto con sus componentes necesarios para predecir. |
| `metricas_modelos.csv` | Resultados de evaluación de los modelos: métricas en Validation, configuraciones de hiperparámetros y desempeño en los tres folds temporales. |
| `predicciones_validation.parquet` | Valores reales y predicciones de los modelos y referencias sobre el conjunto Validation. Permite recalcular métricas y comparar errores. |
| `analisis_errores.csv` | Resúmenes de errores por modelo y distintos segmentos, como producto, mes y grupo corporativo, además de errores extremos. |
| `evidencia_estadistica.csv` | Resultados de las comparaciones estadísticas, incluidos los remuestreos bootstrap por grupo corporativo y sus intervalos de confianza. |
| `costos_modelos.csv` | Indicadores de costo computacional e interpretabilidad: tiempos, memoria estimada, latencia de inferencia, tamaño de los modelos e importancia de variables. |
| `configuracion_ejecucion.json` | Configuración y trazabilidad de la corrida: semillas, versiones de librerías, parámetros, modelos seleccionados y referencias a los datos de origen. |
| `README.md` | Descripción de los archivos contenidos en esta carpeta. |

**Nota:** Las predicciones y métricas corresponden a Validation; el conjunto Test permanece reservado.

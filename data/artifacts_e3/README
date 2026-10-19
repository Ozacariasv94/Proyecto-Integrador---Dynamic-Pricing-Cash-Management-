# Artefactos — E3: Modelo de Referencia (Baseline)

## Descripción

Esta carpeta contiene los modelos, métricas, predicciones y diagnósticos generados durante el **Avance 3 del Proyecto Integrador Multipricing**.

El objetivo de E3 es establecer modelos de referencia para estimar el número de operaciones del siguiente mes (`operaciones_t1`), utilizando los datasets preparados en E2.

Se evaluaron cuatro modelos:

- **B0:** Predictor constante basado en la mediana de Train.
- **B1:** Persistencia de operaciones del mes actual.
- **B2:** Regresión Ridge con Dataset A.
- **B3:** Regresión Ridge con Dataset B (PCA).

Los resultados se utilizan como punto de partida para el desarrollo y la comparación de modelos en E4.

## Estructura

Los archivos se almacenan en:

`artifacts_e3/final/corrida_<RUN_ID>/`

Cada ejecución genera una carpeta independiente para conservar la trazabilidad de los resultados.

## 1. Modelos y predicciones

| Archivo | Descripción |
|---|---|
| `baseline_ridge_A.joblib` | Modelo Ridge entrenado con Dataset A. |
| `baseline_ridge_B.joblib` | Modelo Ridge entrenado con Dataset B/PCA. |
| `baseline_bundle_A.joblib` | Modelo Ridge A, preprocesador de E2 y nombres de características. |
| `baseline_bundle_B.joblib` | Modelo Ridge B, preprocesador de E2 y nombres de características. |
| `predictions_validation_pseudonymized.csv` | Predicciones de los cuatro baselines, valores reales y llaves protegidas de Validation. |

## 2. Evaluación y comparación de modelos

| Archivo | Descripción |
|---|---|
| `baseline_metrics.csv` | MAE, RMSE, WAPE, MdAE y otras métricas por modelo y partición evaluada. |
| `baseline_comparison.csv` | Comparación de modelos y mejoras porcentuales frente a B0 y B1. |
| `metric_rankings.csv` | Clasificación de los modelos según las distintas métricas. |
| `lift_thresholds.csv` | Cumplimiento de los umbrales mínimos de mejora establecidos. |
| `operational_threshold_equivalences.csv` | Equivalencia de los umbrales de mejora en operaciones de MAE. |
| `train_validation_gaps.csv` | Diferencias de desempeño entre Train y Validation para Ridge A y B. |
| `learning_curve.csv` | Evolución del error de Ridge A al aumentar el tamaño de entrenamiento. |
| `ridge_numerical_audit.csv` | Comparación de configuraciones numéricas de Ridge y estabilidad de sus resultados. |

## 3. Importancia de características

| Archivo | Descripción |
|---|---|
| `ridge_coefficients.csv` | Coeficientes de la solución Ridge utilizada para el diagnóstico de importancia. |
| `feature_importance.csv` | Importancia por permutación de características individuales seleccionadas. |
| `family_importance.csv` | Importancia por permutación de familias completas de variables. |
| `family_ablation.csv` | Comparación de Ridge utilizando historia, historia + pricing y Dataset A completo. |
| `family_summary.csv` | Resumen del número de características e importancia por familia. |

## 4. Validación temporal y cobertura

| Archivo | Descripción |
|---|---|
| `temporal_cv_folds.csv` | Resultados de los cuatro folds temporales para B0, B1 y Ridge reducido. |
| `temporal_cv_summary.csv` | Promedio y variabilidad de las métricas obtenidas en los folds. |
| `target_drift.csv` | Comparación de la distribución de operaciones entre las particiones. |
| `monthly_coverage.csv` | Cobertura mensual de registros, grupos y observaciones evaluables. |
| `monthly_prediction_errors.csv` | Errores y volúmenes reales/predichos por mes objetivo y modelo. |
| `source_quality.csv` | Indicadores de calidad y anomalías identificadas en la fuente. |

## 5. Análisis de errores

| Archivo | Descripción |
|---|---|
| `residual_summary.csv` | Estadísticas generales de los residuos de Ridge A. |
| `error_concentration.csv` | Porcentaje del error absoluto concentrado en las observaciones de mayor error. |
| `quintiles_ops_t.csv` | Desempeño por segmentos de volumen transaccional conocido en el mes actual. |
| `segmented_errors.csv` | Métricas por producto, subproducto, industria, continuidad y categorías vistas/no vistas. |
| `group_error_pseudonymized.csv` | Grupos corporativos con mayor error acumulado, mediante identificadores protegidos. |
| `extreme_cases_pseudonymized.csv` | Ejemplos de observaciones con errores extraordinarios. |
| `error_typology.csv` | Clasificación excluyente de errores según sus características principales. |
| `overlapping_error_segments.csv` | Identificación de observaciones que pertenecen simultáneamente a distintos segmentos de error. |
| `bootstrap_group_comparison.csv` | Comparación estadística de B1 y B2 mediante bootstrap agrupado por grupo corporativo. |

## 6. Configuración, conclusiones y reproducibilidad

| Archivo | Descripción |
|---|---|
| `model_config.json` | Parámetros, versiones, configuración de modelos, particiones y referencias a E2. |
| `delivery_manifest.json` | Resumen de la ejecución, modelo ganador y condiciones de evaluación. |
| `requirements_e3.txt` | Versiones de las principales librerías utilizadas. |
| `artifact_index.csv` | Inventario de archivos generados durante la ejecución. |
| `contrato_reproduccion_E4.md` | Instrucciones para reutilizar los modelos y artefactos de E3 en E4. |
| `consistency_checks.csv` | Verificaciones automáticas entre las cifras de las conclusiones y los resultados calculados. |
| `academic_conclusions.csv` | Resumen de los diez principales hallazgos del entregable. |

## Consideraciones

- Los artefactos dependen de los datasets y transformaciones preparados en `artifacts_e2/`.
- Los modelos guardados no sustituyen la ingeniería de características de E2 para procesar nuevos datos.
- La validación cruzada utiliza una versión reducida de Ridge; no equivale a una validación completa de B2/B3.
- Las métricas oficiales se utilizan para comparar modelos de referencia, no para establecer efectos causales.
- **Test permanece reservado** y no se utiliza para seleccionar modelos.
- Los identificadores contractuales exportados se encuentran pseudonimizados. Su comparación entre ejecuciones requiere conservar una llave privada estable.

## Resultado principal

El modelo **B1 — Persistencia** obtuvo el menor MAE en Validation, con aproximadamente **399.78 operaciones**, superando a los modelos Ridge evaluados.

Este resultado establece la referencia de desempeño que deberán superar los modelos desarrollados en E4.

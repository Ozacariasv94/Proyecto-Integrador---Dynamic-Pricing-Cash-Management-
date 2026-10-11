# Artefactos E2 — Ingeniería de Características

Esta carpeta contiene los archivos generados en el **Avance 2** del proyecto **Multipricing para Cash Management**. Se utilizan como entrada para entrenar y evaluar los modelos de los siguientes avances.

## Archivos

| Archivo(s) | Descripción |
|---|---|
| `X_train_A.npz`, `X_validation_A.npz`, `X_test_A.npz` | Matrices de variables predictoras del **Dataset A** (características interpretables). |
| `X_train_B.npz`, `X_validation_B.npz`, `X_test_B.npz` | Matrices del **Dataset B**, con reducción de variables numéricas mediante PCA. |
| `y_train.csv`, `y_validation.csv`, `y_test.csv` | Variable objetivo: operaciones del mes siguiente (`operaciones_t1`). |
| `keys_train.csv`, `keys_validation.csv`, `keys_test.csv` | Identificadores para relacionar cada predicción con su fecha, grupo, cliente y producto. |
| `preprocessor_A.joblib`, `preprocessor_B.joblib` | Preprocesadores ajustados para cada dataset. |
| `yeo_johnson_transformers.joblib` | Transformaciones no lineales utilizadas en E2. |
| `feature_names_A.csv`, `feature_names_B.csv` | Nombres de las columnas de cada matriz, en su orden correspondiente. |
| `feature_manifest.csv` | Catálogo de características generadas. |
| `feature_manifest_completo.csv` | Relación entre características originales y columnas finales de A/B. |
| `feature_selection_manifest.csv` | Variables conservadas o excluidas y motivo de selección. |
| `feature_ranking_train.csv` | Indicadores de relevancia de características calculados en entrenamiento. |
| `split_manifest.csv` | Resumen de las particiones temporales. |
| `pca_summary.csv`, `pca_loadings.csv` | Varianza explicada e interpretación de componentes PCA. |
| `feature_config.json` | Parámetros utilizados para generar las características. |

## Convenciones

- **Train:** septiembre de 2023 a agosto de 2025.
- **Validation:** septiembre de 2025 a febrero de 2026.
- **Test:** marzo a julio de 2026.
- Los archivos `.npz` contienen matrices numéricas dispersas; pueden abrirse con `scipy.sparse.load_npz()`.
- Las filas de `X`, `y` y `keys` corresponden **por posición** dentro de cada partición.
- Los archivos `.joblib` guardan transformaciones ya ajustadas; la lógica completa de generación de variables está documentada en el notebook de E2.

> **Nota:** los archivos `keys_*.csv` contienen identificadores de clientes y contratos. No deben publicarse en repositorios públicos sin tratamiento adecuado.

# Avance 4 — Artefactos mínimos de la ejecución

El notebook ejecutado presenta las gráficas, las tablas y las conclusiones.
Esta carpeta guarda exactamente nueve archivos para reutilizar resultados:

- modelo_final.joblib: alternativa de menor MAE observada en Validation.
- modelos_candidatos.joblib: siete modelos entrenados con Train completo.
- metricas_modelos.csv: métricas, configuraciones y resultados de los tres folds.
- predicciones_validation.parquet: predicciones de nueve referencias/candidatos y valores reales.
- analisis_errores.csv: resúmenes por producto, mes, grupo y tres universos.
- evidencia_estadistica.csv: bootstrap e intervalos de confianza agrupados.
- costos_modelos.csv: tiempos, memoria, latencia, tamaño e importancias.
- configuracion_ejecucion.json: versiones, semillas, modelos y referencias.
- README.md: esta guía.

Cada fila de un archivo consolidado lleva un campo de tipo/nivel.
Las llaves de grupo y observación exportadas están pseudonimizadas.
No se incluye información del conjunto Test.

Para recuperar los objetos:
    import joblib
    pkg=joblib.load('modelo_final.joblib')
    candidatos=joblib.load('modelos_candidatos.joblib')['modelos']

Si `pkg` indica `tipo='persistencia'`, la predicción es la columna
`numero_operaciones` conocida en el mes actual. Si indica `tipo='constante'`,
se utiliza su `valor_constante`; en otro caso, `pkg` conserva el
preprocesador y el estimador del modelo. La función de predicción utilizada
para verificarlos se encuentra en la sección E4-A7 del notebook.

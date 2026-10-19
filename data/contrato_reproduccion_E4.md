# Contrato de reproducibilidad E3 → E4

- Corrida: `20261018T232713Z_03736744`.
- Fuente de matrices: `/content/drive/MyDrive/Colab Notebooks/Proyecto Integrador/artifacts_e2`.
- El objetivo es `operaciones_t1`; la predicción corresponde a cada unidad contractual y mes de origen.
- Los bundles `baseline_bundle_A.joblib` y `baseline_bundle_B.joblib` contienen estimador,
  preprocesador E2 y nombres de variables. No transforman directamente `Base_multipricing.csv`.
- Para inferir desde datos nuevos se debe reproducir primero la construcción temporal y
  la ingeniería de características de E2, conservando orden de columnas, tratamiento de categorías
  y fecha de disponibilidad de las variables.
- Para reproducir los resultados académicos de E3, utilizar las matrices A/B de E2
  y los targets y llaves correspondientes. Test sigue reservado.
- Las firmas SHA-256 de configuración y manifiesto E2 están en `model_config.json`.
- Identificadores anonimizados comparables entre corridas: False.
  Si se requiere comparabilidad, configurar una llave privada persistente E3_PSEUDONYM_KEY
  fuera del notebook. No publicar ni exportar esa llave.
- Las conclusiones escritas corresponden a la versión E2 auditada. Al reejecutar,
  `consistency_checks.csv` permite comprobar la concordancia con las tablas.

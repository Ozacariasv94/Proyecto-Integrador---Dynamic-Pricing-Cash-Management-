# Estrategia de Optimización Multi-pricing para Cash Management

![Status](https://img.shields.io/badge/Status-In_Development-blue)
![Python](https://img.shields.io/badge/Python-3.10%2B-green)
![FastAPI](https://img.shields.io/badge/API-FastAPI-009688)

## Descripción del Proyecto

Este proyecto implementa una solución analítica de **Revenue Management** diseñada para optimizar la estrategia de precios de la cartera de productos de **Cash Management** en banca corporativa y empresarial. 

El sistema analiza la relación transaccional de cada cliente y modela su sensibilidad/elasticidad precio ante variaciones de tarifa. A través de un enfoque de **ecualización de precios**, el algoritmo propone reequilibrar las comisiones y márgenes de los productos contratados por el cliente (subiendo tarifas en productos inelásticos y ajustando o bajando comisiones en productos sensibles), permitiendo maximizar el ingreso global de la cuenta con un riesgo controlado de rechazo o *churn*.

---

## Objetivo del Proyecto

La **función objetivo** del proyecto es la **maximización del ingreso total por cliente**, sujeta a las siguientes fronteras y capacidades:

1. **Restricción Regulatoria:** Cumplir estrictamente con los límites y techos de tarifas máximas registradas ante **Banxico**, así como con las políticas de margen del banco.
2. **Modelado de Elasticidad:** Estimar la sensibilidad del cliente y la probabilidad de aceptación comercial (*rango de riesgo*) ante los cambios de precio propuestos.
3. **Plataforma de Habilitación Comercial (Dashboard APIficado):** Entregar a la fuerza de ventas una herramienta interactiva en tiempo real que muestre:
   - El escenario actual (**As-Is**) vs. la optimización recomendada (**To-Be**).
   - Rango de maniobra por producto y probabilidad empírica de aceptación.
   - Un **Pitch de Ventas** automatizado para justificar el ajuste tarifario bajo una narrativa de valor ganar-ganar.

---

## Integrantes del Equipo

* **Oscar Benjamín Zacarías Villegas** — Matrícula: `A01797160`  
  *Rol:* Machine Learning Engineer / Architect
* **Mariana Paola De los Cobos Kingston** — Matrícula: `A01796922`  
  *Rol:* Data Scientist / Financial Analyst
* **Gerardo Tenorio Castillo** — Matrícula: `A01139576`  
  *Rol:* Full-Stack & UI/UX Developer

---

## Estructura del Repositorio

```text
.
├── README.md                   # Descripción general, objetivo e integrantes
├── docs/                       # Documentación técnica, marcos legales y Banxico
├── data/
│   ├── raw/                    # Historico transaccional anonimizado
│   ├── processed/              # Datasets procesados y matrices de elasticidad
│   └── external/               # Tablas de tarifas máximas autorizadas por Banxico
├── models/
│   ├── elasticity/             # Modelos de sensibilidad y estimación de elasticidad
│   ├── optimization/           # Solver matemático de la función objetivo y restricciones
│   └── artifacts/              # Pipeline de modelos entrenados y serializados (.pkl)
├── api/
│   ├── app/                    # Código principal del servicio FastAPI
│   ├── routes/                 # Endpoints de recomendación
│   └── tests/                  # Pruebas unitarias y de integración de la API
├── dashboard/
│   ├── src/                    # Frontend interactivo
│   ├── components/             # Visualizadores de ecualización, sliders y rangos de riesgo
│   └── assets/                 # Recursos gráficos y estilos
└── notebooks/                  # Análisis exploratorio (EDA) y prototipado analítico

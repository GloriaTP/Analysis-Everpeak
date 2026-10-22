# Analysis-Everpeak
# EverPeak Retail Analysis – Sprint 6




Este repositorio contiene el análisis realizado durante el Sprint 6 del caso EverPeak–SilverBasket.

El dataset `everpeak_retail` incluye 2,000 órdenes de clientes con valores faltantes, sentinels, outliers y problemas de calidad diseñados para simular datos reales del retail. :contentReference[oaicite:2]{index=2}

Executive Summary
Context & objective. This project answers one central question: is there a relationship between urban mobility (congestion and travel delays) and economic productivity (GDP per capita)? The analysis was prepared for the EverPeak strategy team to support decisions on where transport infrastructure investment could matter most.
Key finding. There is no clear relationship between traffic and GDP per capita in the data analyzed. Cities with high congestion are not consistently the ones with lower (or higher) economic output.
Data coverage.
Item	Value
Year analyzed	2024
Cities	15
Countries	7
Key variables.
`jams_delay`: traffic congestion / delay indicator, used as the mobility measure.
`city_gdp_capita`: GDP per capita of each city, used as the productivity measure.
Methodology
Data cleaning and standardization
Time fields converted to `datetime` and numeric values to `float` so calculations are reliable.
Column names standardized in `snake_case` and aligned across both datasets.
Aggregation and integration
Both datasets contain a city column, and the year can be extracted from the date field, so they share the keys `city` and `year`.
Data was aggregated at the city–year level and combined with an INNER join, which keeps only the cities and years present in both the traffic and economic datasets.
Visual validation
Box plots to detect outliers.
Histograms to understand distributions and general trends.
Bar charts to compare values across cities.
Initial Findings
No visible relationship between traffic levels and GDP per capita.
The box plots reveal unusually high values that look like anomalies and deserve a closer review.
Brazil concentrates a large share of these anomalous values.
Recommendations
Priority cities by traffic level: Mexico City and São Paulo show the highest congestion levels.
Validate data sources for Brazil: the number of anomalous values suggests possible data quality issues that should be confirmed before drawing conclusions.
Transport infrastructure investment: Santiago and Bogotá are proposed as candidates to improve transport infrastructure and, in turn, productivity.
Top priority city: Bogotá stands out as the city where high congestion coincides with low economic productivity indicators, making it the strongest candidate for investment.
Next steps: extend the analysis to more years and run a formal correlation analysis per city to confirm these results.

## 📂 Contenido del repositorio

- `S5_ladb_mobility_economy_project_student_(2).ipynb`
  → Notebook principal con limpieza, EDA, distribuciones, outliers y conclusiones.

## ▶ Cómo abrir el notebook en Google Colab

Haz clic en el siguiente botón:

[![Open In Colab](https://colab.research.google.com/drive/1DgNcvviuziw7uLk6UqSxCVXTWdLS2x3G?usp=sharing)](S5_ladb_mobility_economy_project_student_(2).ipynb)

O:

1. Abre el archivo `.ipynb` en GitHub
2. Haz clic en **Open in Colab**

## 📘 Cómo reproducir el análisis

1. Abre `S5_ladb_mobility_economy_project_student_(2).ipynb)`
2. Ejecuta las celdas en orden
3. El notebook carga automáticamente el dataset desde `/data/` o desde un enlace público (según corresponda)

## 🧠 Objetivo del análisis

- Identificar problemas de calidad de datos
- Construir un pipeline de limpieza reproducible
- Analizar comportamientos, distribuciones y outliers
- Generar insights para el equipo de Estrategia e Integración de EverPeak

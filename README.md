# Analysis-Everpeak
# EverPeak Mobility Analysis – Sprint 6

The goal for this analysis is to evaluate how urban mobility relates to economic productivity in major Latin American cities. To do this, I work with real data from the TomTom Traffic Index and OECD Cities, which need to be clean, combine, and analyze to identify which cities are worth investing in for transport infrastructure.


## Executive Summary

**Context & objective.** This project answers one central question: *is there a relationship between urban mobility (congestion and travel delays) and economic productivity (GDP per capita)?* The analysis was prepared for the EverPeak strategy team to support decisions on where transport infrastructure investment could matter most.

**Key finding.** There is **no clear relationship** between traffic and GDP per capita in the data analyzed. Cities with high congestion are not consistently the ones with lower (or higher) economic output.

**Data coverage.**

| Item | Value |
|---|---|
| Year analyzed | 2024 |
| Cities | 15 |
| Countries | 7 |

**Key variables.**
- `jams_delay`: traffic congestion / delay indicator, used as the mobility measure.
- `city_gdp_capita`: GDP per capita of each city, used as the productivity measure.

## Methodology

1. **Data cleaning and standardization**
   - Time fields converted to `datetime` and numeric values to `float` so calculations are reliable.
   - Column names standardized in `snake_case` and aligned across both datasets.
2. **Aggregation and integration**
   - Both datasets contain a city column, and the year can be extracted from the date field, so they share the keys `city` and `year`.
   - Data was aggregated at the **city–year** level and combined with an **INNER join**, which keeps only the cities and years present in both the traffic and economic datasets.
3. **Visual validation**
   - **Box plots** to detect outliers.
   - **Histograms** to understand distributions and general trends.
   - **Bar charts** to compare values across cities.

## Initial Findings

- No visible relationship between traffic levels and GDP per capita.
- The box plots reveal **unusually high values** that look like anomalies and deserve a closer review.
- Brazil concentrates a large share of these anomalous values.

## Recommendations

1. **Priority cities by traffic level:** Mexico City and São Paulo show the highest congestion levels.
2. **Validate data sources for Brazil:** the number of anomalous values suggests possible data quality issues that should be confirmed before drawing conclusions.
3. **Transport infrastructure investment:** Santiago and Bogotá are proposed as candidates to improve transport infrastructure and, in turn, productivity.
4. **Top priority city:** **Bogotá** stands out as the city where high congestion coincides with low economic productivity indicators, making it the strongest candidate for investment.
5. **Next steps:** extend the analysis to more years and run a formal correlation analysis per city to confirm these results.



## 📂 Contenido del repositorio

- `S5_ladb_mobility_economy_project_student_(2).ipynb`
  → Notebook principal con limpieza, EDA, distribuciones, outliers y conclusiones.

## ▶ Cómo abrir el notebook en Google Colab

Haz clic en el siguiente botón:

[![Open In Colab](https://colab.research.google.com/drive/1DgNcvviuziw7uLk6UqSxCVXTWdLS2x3G?usp=sharing)](S5_ladb_mobility_economy_project_student_(2).ipynb)

O:

1. Abre el archivo `S5_ladb_mobility_economy_project_student_(2).ipynb` en GitHub
2. Haz clic en **Open in Colab**

## 📘 Cómo reproducir el análisis

1. Abre `S5_ladb_mobility_economy_project_student_(2).ipynb)`
2. Ejecuta las celdas en orden
3. El notebook carga automáticamente el dataset desde `/data/` o desde un enlace público (según corresponda)

## 🧠 Objectives:

1. **Identify data quality issues** in the traffic and economic datasets, such as inconsistent formats, mismatched column names and anomalous values.
2. **Build a reproducible cleaning and integration pipeline** that standardizes data types and column names, and combines both datasets at the city–year level.
3. **Analyze distributions and outliers** in congestion (`jams_delay`) and GDP per capita (`city_gdp_capita`) to understand how mobility and productivity behave across cities.
4. **Generate actionable insights for EverPeak's Strategy and Integration team** on whether urban mobility relates to economic productivity and where transport infrastructure investment could matter most.

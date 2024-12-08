
# README for Analyzing the Impact of Socio-Economic Factors on Health Deprivation and Disability (2019)

This document explains the analysis conducted to explore the relationship between socio-economic factors and health outcomes in England's Lower Layer Super Output Areas (LSOAs) using the **Index of Multiple Deprivation (IMD) 2019** data.

---

## Table of Contents
1. [Objective](#objective)
2. [Key Questions Answered](#key-questions-answered)
3. [Dataset Description](#dataset-description)
4. [Analysis Summary](#analysis-summary)
5. [Results and Visualizations](#results-and-visualizations)
6. [How to Use](#how-to-use)
7. [Dependencies](#dependencies)

---

## Objective
The primary objective of this analysis is to investigate how socio-economic factors such as income, education, crime, and employment contribute to health deprivation and disability outcomes across England.

---

## Key Questions Answered

1. **What are the relationships between various socio-economic indicators and health deprivation?**
   - Regression models quantify the contribution of factors like income and education to health deprivation.

2. **Which areas are the most and least deprived?**
   - Spatial analysis identifies regions with the highest and lowest deprivation scores.

3. **How do socio-economic factors correlate with each other?**
   - Correlation analysis provides insights into interdependencies among indicators.

---

## Dataset Description

- **IMD 2019 Data**: Includes socio-economic indicators and scores (e.g., `IncScore`, `HDDScore`, `EduScore`).
- **Shapefile**: Geospatial representation of LSOAs for spatial visualization.

---

## Analysis Summary

### Steps and Methodologies

1. **Data Cleaning and Exploration**
   - Checked for missing values.
   - Visualized distributions (e.g., histograms of `EnvScore`, `CriScore`, etc.).

2. **Transformation and Standardization**
   - Applied Yeo-Johnson transformation to reduce skewness.
   - Standardized data for regression and correlation analysis.

3. **Correlation Analysis**
   - Computed Pearson correlation between variables.
   - Generated a heatmap using hierarchical clustering.

4. **Regression Modeling**
   - Linear regression models for individual socio-economic factors.
   - Multivariate regression for combined impact analysis.

5. **Spatial Visualization**
   - Choropleth maps display health deprivation geographically.
   - Highlight maps for most and least deprived regions.

---

## Results and Visualizations

### Key Findings

- **Income and Employment Scores** strongly correlate with Health Deprivation Scores.
- **Correlation Matrix**: High interdependence between `IncScore` and `EmpScore` with weaker correlations for environmental factors.
- ![image](https://github.com/user-attachments/assets/ade27170-6df4-4250-a16e-906ee63a2a54)


### Maps

1. **Choropleth Map**:
   - Visualizes health deprivation scores across England.
   - Gradient from least deprived (purple) to most deprived (yellow).
   - ![image](https://github.com/user-attachments/assets/e5cb1c31-330b-4f3c-9c1b-489f2d1bfdc0)



2. **Most and Least Deprived Highlighted - Top 20**:
   - Most deprived regions highlighted in **dark purple**.
   - Least deprived regions highlighted in **gold**.
   - ![image](https://github.com/user-attachments/assets/0e38db05-6c10-4120-bf8e-9a96605cac90)


---

## How to Use

1. **Run the R Markdown File**:
   - Update file paths for dataset and shapefiles.
   - Knit the R Markdown file to generate the results in PDF or HTML format.

2. **Interpret Results**:
   - Use the maps for geographic insights into deprivation.
   - Examine regression summaries for the relative importance of socio-economic factors.

---

## Dependencies

The following R packages are required:
- `foreign`: Reading `.dbf` files.
- `dplyr`, `ggplot2`: Data manipulation and visualization.
- `sf`: Spatial data handling and mapping.
- `bestNormalize`: Data normalization.
- `corrplot`: Correlation heatmaps.
- `lmtest`: Regression modeling.

---

For more details, refer to the accompanying analysis PDF.

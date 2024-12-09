
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

#### Key Insights from Regression Analysis

The table below summarizes the results of the individual regression analyses conducted to evaluate the relationship between socio-economic variables and the Health Deprivation and Disability Score (HDDScore):
![image](https://github.com/user-attachments/assets/8a6658e4-ea1b-432c-afb7-12d57a44d352)

### Interpretation of Results

- Employment Score: The strongest predictor of HDDScore with an R-squared value of 0.7369. Suggests that 73.69% of the variability in HDDScore is explained by Employment Deprivation. Coefficient (0.8584) indicates a strong positive relationship: as employment deprivation increases, health deprivation worsens.
- Income Score: The second strongest predictor (R-squared: 0.6599). Highlights the critical role of income deprivation in health outcomes.
- Education Score: Significant contributor to HDDScore (R-squared: 0.5395). Indicates areas with lower education levels face worse health deprivation.
- Crime Score: Moderate influence (R-squared: 0.3462). Suggests areas with higher crime rates tend to have increased health deprivation.
- Environment Score: Weakest predictor (R-squared: 0.02712). Indicates that environmental factors have a limited direct impact on health deprivation in this analysis.
###Conclusions from Regression Analysis 
- Socio-economic factors, particularly income, employment, and education, are the most significant predictors of health deprivation.
- Crime and environmental factors show weaker associations but remain statistically significant.
- Addressing economic and educational disparities could have the greatest impact on reducing health inequalities.

### Multivariate Regression Analysis

This section presents the results of the multivariate regression model, which evaluates the combined effects of multiple socio-economic factors on the Health Deprivation and Disability Score (HDDScore).
![image](https://github.com/user-attachments/assets/1081a913-ebf3-423e-b0c3-6f3cfddf2749)

#### Key Findings

-Income: The coefficient (-0.2369) indicates that higher income reduces health deprivation. The 95% confidence interval (-0.2566, -0.2172) confirms the precision of the estimate.
-Employment: Strongest predictor with a coefficient of 0.8985. Highlights that employment deprivation contributes significantly to health deprivation, as reflected by its high t-value (95.602) and tight confidence interval.
-Education: Coefficient (0.1425) shows that lower education levels are associated with higher health deprivation. Statistically significant with a p-value of <2e-16.
-Crime: Coefficient (0.1022) suggests that areas with higher crime rates experience worse health deprivation.
-Environment: Weakest predictor, with a coefficient of 0.0460. Indicates a minimal but statistically significant impact on health deprivation.

###Interpretation
- Employment deprivation remains the most critical factor, even after accounting for other variables.
- Income and education play significant roles in explaining variations in health outcomes, emphasizing the importance of economic and educational interventions.
- Crime and environment contribute less but still affect health deprivation, warranting consideration in comprehensive health improvement strategies.
###Conclusion
The multivariate regression model accounts for the combined influence of socio-economic factors, providing a comprehensive understanding of their relationships with health deprivation. 
These findings highlight: 
-The importance of addressing employment and income disparities. 
-The need to consider education and community factors in policy-making.

### Maps

1. **Choropleth Map**:
   - Visualizes health deprivation scores across England.
   - Gradient from least deprived (purple) to most deprived (yellow).
   - ![image](https://github.com/user-attachments/assets/e5cb1c31-330b-4f3c-9c1b-489f2d1bfdc0)



2. **Most and Least Deprived Highlighted - Top 20**:
   - Most deprived regions highlighted in **dark purple**.
   - Least deprived regions highlighted in **gold**.
   - ![image](https://github.com/user-attachments/assets/ade2d8a9-5b5d-47ee-b054-86ea0139f2c7)



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

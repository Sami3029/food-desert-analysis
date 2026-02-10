# Mapping the Gap: A Spatial and Predictive Analysis of Virginia Food Deserts

This project explores the drivers of food access disparities across Virginia counties using USDA Food Access Research Atlas data. The analysis combines exploratory data analysis, correlation analysis, and multiple machine learning models to evaluate which socioeconomic, agricultural, and retail food system variables are most strongly associated with low food access.

The goal of this project is not only predictive performance, but interpretability: identifying which features appear most correlated with food access outcomes and where traditional assumptions (e.g., grocery store density alone) may fall short.

---

## Data Source

- **USDA Food Access Research Atlas**
- County-level data across the United States
- Filtered to **Virginia (133 counties / county-equivalents)**

Key target variable:
- `PCT_LACCESS_POP19`: Percentage of the population with low access to food (2019)

---

## Methodology

### 1. Data Preparation
- Merged USDA Excel files into a single CSV
- Filtered dataset to Virginia counties
- Removed geographic coordinates and redundant food access fields
- Replaced USDA missing value codes (`-9999`, `-8888`) with NaNs
- Dropped features with excessive missingness
- Median imputation applied to remaining missing values

---

### 2. Exploratory Data Analysis
- Correlation analysis between all numeric features and food access
- Identified strongly correlated variables including:
  - WIC and SNAP redemption metrics
  - Orchard and berry acreage
  - Grocery store density
  - Changes in food retail infrastructure over time
- Visualizations:
  - Horizontal correlation bar charts
  - Scatter plots
  - Correlation heatmaps
  - Dual-axis scatter comparisons

---

### 3. Modeling Approaches

#### Multiple Linear Regression
- Feature selection based on correlation strength
- Median imputation prior to training
- Model performance:
  - R² ≈ -0.09 (indicating limited linear explanatory power)

#### Single-Variable Linear Regression
- Grocery store density (`GROCPTH20`) as sole predictor
- R² ≈ 0.01
- Demonstrates that grocery density alone is insufficient to explain food access

#### Random Forest Regression
- Nonlinear model to capture interactions
- Modest improvement over linear regression
- R² ≈ 0.02

---

## Key Findings

- Food access is **not well explained by any single variable**
- Agricultural land use (orchards, berries) and assistance program usage show stronger correlations than expected
- Traditional assumptions about grocery store density may oversimplify food access dynamics
- Limited predictive performance suggests:
  - Strong regional heterogeneity
  - Structural factors not fully captured in available data
  - Potential need for spatial or policy-level modeling

---

## Tools & Libraries

- Python
- pandas, numpy
- matplotlib, seaborn
- scikit-learn

---

## Future Improvements

- Incorporate spatial modeling (e.g., GIS, spatial lag models)
- Add temporal analysis across multiple years
- Explore policy-level variables (zoning, transit access)
- Use regularized regression (Lasso / Ridge)
- Improve feature engineering and normalization

---

## Project Motivation

Food deserts are often discussed in simplistic terms. This project aims to highlight the complexity of food access challenges and encourage more nuanced, data-driven approaches to addressing them.

---

## Author

**Samantha Nourse**  
Engineering Management | Data Analysis | Sustainability  

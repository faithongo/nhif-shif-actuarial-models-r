# Actuarial Models in R: Kenya's NHIF to SHIF Transition

### Analyzing affordability, default risk, and fund solvency for universal health coverage.

*(Note: This repository contains the R modeling work from my Final Year Project, originally developed collaboratively. This is my personal portfolio copy highlighting my specific contributions.)*

## The Problem
The transition to the Social Health Insurance Fund (SHIF) charges 2.75% of income, with a floor of KES 300/month. This project quantifies the affordability gap for low-income households (e.g., earning KES 5,000) and models the downstream impact on fund solvency and default risk.

## My Specific Contributions
As a core member of this final year project, I was responsible for:
- **[Writing the `NHIF_time_series.R` script to build the 2016–2024 loss-ratio trajectory and ARIMA forecast.]**
- **[Cleaning the proxy dataset and engineering the affordability ratio variable for the logistic regression model.]**
- **[Generating the comparative projection visualizations using `ggplot2`.]**
- **[Model optimisation by implementing training and testing workflows to identify effective model coefficients]**
- **[Evaluating model performance using accuracy metrics and prediction testing]**

## The Models & Methods
| Script | Methodology | Business Question Answered |
| --- | --- | --- |
| `SHIF_Model.R` | Logistic Regression (`glm`) | What drives a household to default on premiums based on income volatility? |
| `NHIF_time_series.R` | ARIMA Forecasting (`forecast` package) | What is the projected claims trajectory for 2025–2029 under current trends? |
| `Affordability_Curve.R` | Data Visualization (`ggplot2`, `scales`) | At what income threshold does the premium become a regressive burden? |

## Key Findings
1. **The Regressive Floor:** The KES 300 minimum creates a severe affordability spike for households earning below KES 10,909.
2. **Solvency Risk:** Stress-testing the model shows that without targeted subsidies, default rates could threaten fund solvency by [Year/Scenario].
3. **Recommendation:** An Adjusted Progressive Premium Model (APPM) with tiered pricing and state subsidies (similar to Rwanda's Ubudehe model) is required to cushion seasonal income shocks.

## How to Reproduce
```r
# Install required packages
install.packages(c("ggplot2", "dplyr", "scales", "forecast", "gridExtra"))

# Run the scripts in order
source("NHIF_time_series.R")
source("Affordability_Curve.R")
source("SHIF_Model.R")

##Acknowledgements
##This project was developed as part of my final year project at The University of Nairobi.
##Original collaborative repository: https://github.com/JessyWaweru/actuarial-models-in-r

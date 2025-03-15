# Identifying 'Outliers' and 'Influential Observations' in Sales Analysis Using R

This repository contains all materials for the "Lab 4: Statistics for Analytics II" assignment from George Washington University, focusing on a statistical analysis for Ergonomic Systems Inc. (ESI). The project utilizes R to analyze a dataset featuring customer demographics and sales data to determine key predictors of sales volume. It includes rigorous data cleaning, linear regression modeling, and extensive diagnostics to assess model assumptions and identify outliers and influential points. Specific scripts handle tasks like outlier detection using hat values, assessing model fit with the Generalized Linear Model Assumption (GVLMA) tool, and influence analysis with DFBETAS. The repository is designed for complete transparency, allowing others to replicate the study or explore the methods used in statistical analysis.

## Basic Information
**Names:** N M Emran Hussain  
**Email:** nmemranhussain2023@gmail.com  
**Date:** February 2025  
**Model Version:** 1.0.0  
**License:** [MIT License](LICENSE)

## Intended Use
**Purpose:** The purpose of this project is to analyze customer sales data to identify key variables that influence sales, detect outliers, and assess influential data points using statistical techniques and regression diagnostics. 
**Intended Users:** Data Analysts, Data scientists, machine learning enthusiasts, educators.  
**Out-of-scope Uses:** The model is not intended for production use in any critical applications or real-time decision-making systems.

## Data Description

| **Variable Name**       | **Model Role**       | **Measurement Level**  | **Description**                                               |
|-------------------------|----------------------|------------------------|---------------------------------------------------------------|
| ID                      | Identifier           | Nominal                | Represents the unique identification number of each customer  |
| Sales                   | Dependent Variable   | Ratio                  | The amount of purchases made by the customer in the past year |
| Age                     | Independent Variable | Ratio                  | The age of the customer                                       |
| Income                  | Independent Variable | Ratio                  | Annual income of the customer                                 |
| Education               | Independent Variable | Ordinal                | Highest level of education attained by the customer           |
| Tenure                  | Independent Variable | Ratio                  | Number of years the customer has been listed in ESI’s database|

**Dataset Name:** Assignment4_2025.dat  
**Number of Samples:** 100    
**Features Used:** 'Age', 'Income', "Education', 'Tenure'   
**Target Variable used:** 'Salse'  

### Architecture  
- This model card utilizes linear model such as **'Multiple Regression'**.

### Evaluation Metrics  
P-value: Indicates statistical significance in multivariate level using 95% confidence level.  
b-value: Represents the magnitude and direction of 'slope' of independent variable(s)

### Version of the Modeling Software and R libraries:  
- **R:** 4.3.2  
- **dplyr:** 1.1.4
- **gvlma:** 1.0.0.3

## Quantitative Analysis  
### Interpretation
- From the **gvlma** function, we cannot be reasonably certain that **Sales** is **non-linearly** related to the set of independent variables because the **Link Function test** is not significant (p ≥ 0.05).
- From the **gvlma** function, we cannot be reasonably certain that the **residuals in the population are skewed**  because the **Skewness test is not significant (p ≥ 0.05)**.
- From the **gvlma** function, we cannot be reasonably certain that the **residuals in the population deviate from a normal distribution** because the **Kurtosis test is not significant (p ≥ 0.05)**.
- From the **gvlma** function, we cannot be reasonably certain that the **residuals in the population are heteroscedastic** because the **Heteroscedasticity test is not significant (p ≥ 0.05)**.  
- Here, X-outliers are IDs 9921, 10663, 10305  
- Here, Y-outliersare IDs 10166, 10805. 10231, 10195, 10566, 9670, 10375, 9716 , 9776, 10126, 11636, 7905.  
- Here, using **dfbetas**, Influential observations for **intercept** are IDs 10632, 10011, 9670, 10126.  
- Here, using **dfbetas**, Influential observations with respect to **slope** associated with **Age** are IDs 10011, 10195, 9716, 7905.  
- Here, using **dfbetas**, Influential observations with respect to **slope** associated with **Income** are IDs 9921, 10166, 10231, 9870, 9806, 9670 & 9776.  
- Here, using **dfbetas**, Influential observations with respect to **slope** associated with **Education** are IDs 9683, 10011, 10195, 9171, 9670, 9776, 10126 & 11636.  
- Here, using **dfbetas**, Influential observations with respect to **slope** associated with **Tenure** are IDs 10805, 10195, 9171, 9670, 9716, 9776, 10126, 11636 & 7905.
- Here, using **Cook's D**, Influential observations with respect to **the set of variable slopes** are IDs NONE.

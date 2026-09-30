# What Makes a Country Happy?

Multiple linear regression on the **World Happiness Report 2015-2020** to find which national factors drive a country's happiness score.

👥 **Team project** completed by a U of T student team, including Ketan Khanna (Group 11) · Statistics for Data Science, University of Toronto · Fall 2020

## Approach
1. **Data preparation:** six yearly reports with different column names were standardised, given a `Year`, `Rank` and `Region`, and combined into one dataset of about 930 country-years
2. **Exploration:** scatter plots and a correlation heatmap of the six factors against happiness
3. **Assumption checks:** linearity, normal residuals, constant variance and multicollinearity (VIF)
4. **Transformations:** square-root transforms for the skewed Trust and Generosity variables
5. **Modelling:** OLS regression with a 70/30 train-test split and forward stepwise feature selection

## Results
| Factor | Coefficient | Meaning |
|---|---|---|
| **Freedom** to make life choices | **1.92** | The biggest effect on happiness |
| Economy (GDP per capita) | 1.18 | Close to a 1:1 lift |
| Health (life expectancy) | 0.99 | Close to a 1:1 lift |
| Family / social support | 0.57 | Smallest of the four |

- The four-factor model explains **75% of the variation** in happiness (R² = 0.749, all p < 0.001)
- Generosity and trust in government added little once the other factors were in the model
- The happiest regions were Australia/New Zealand and North America; the least happy, Sub-Saharan Africa

## 🔧 Claude Notes (2026)
A few statements in the original report are worth tightening:
- The significance level should read **0.05**, not 0.5 (the conclusions still hold, since every p-value is below 0.001)
- Regression on observational data shows **association, not causation**, so "causes an increase" is better read as "is associated with an increase"
- Economy, Family and Health have VIFs near 20, so their individual coefficients are less stable than the combined model fit

## Data
[World Happiness Report](https://www.kaggle.com/mathurinache/world-happiness-report) (Kaggle, 2015-2020).

## Tools
Python · pandas · statsmodels · seaborn

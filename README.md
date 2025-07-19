# Macroeconomic-Determinants-Of-GDP
Macroeconomic Determinants Of GDP: : A Panel Data Analysis Using Fixed Effects

## TABLE OF CONTENTS

[Project Overview](#-Project-Overview)

[❗Problem Statement](#-Problem-Statement)

[🎯Objective](#-Objective)

[📌Focus Areas](#-Focus-Areas)

[🌐Source Of Data](#-Source-Of-Data

[📊 Dataset Description](#-Dataset-Description)

[🛠️Tool Used](#-Tool-Used)

[🔧Methodology](#-Methodology)

[Model Summary And Interpretation](#-Model-Summary-And-Interpretation)

[📬Let's Connect](#-Let's-Connect)


[📘 Project Overview]

This project investigates the key macroeconomic factors that influence Gross Domestic Product (GDP) across multiple countries over time using panel data analysis. By applying a Fixed Effects (FE) model, the analysis controls for time-invariant characteristics of each country to isolate the effect of variables such as exchange rate, exports, foreign direct investment (FDI), and inflation on GDP.

[🧩 Problem Statement]

Economic growth, typically measured by Gross Domestic Product (GDP), is influenced by multiple macroeconomic indicators. Understanding the drivers of GDP is crucial for policymakers, economists, and investors. However, the dynamic and country-specific nature of these relationships calls for robust analytical methods.

This project aims to investigate the macroeconomic determinants of GDP across multiple countries over time using panel data analysis with fixed effects modeling. Specifically, it explores how key variables — including exchange rate, exports, foreign direct investment (FDI), and inflation — impact GDP, while controlling for unobserved country-specific heterogeneity.

By applying statistical techniques suited for longitudinal data, the analysis provides insights into which economic indicators have the most significant and consistent influence on GDP across different countries and time periods.

[📌Objective]

To empirically determine which macroeconomic indicators significantly impact GDP and quantify their effects using robust econometric techniques tailored for panel data.

📊 [Focus Area]

This project focuses on the following core analytical areas:

1. Panel Data Preparation
   
Cleaning, structuring, and transforming multi-country, multi-year macroeconomic data for analysis.

2. Fixed Effects Modeling
   
Applying the Fixed Effects (FE) model to control for unobserved, time-invariant characteristics specific to each country.

3. Variable Selection and Interpretation

Evaluating the effect of key macroeconomic variables (Exchange Rate, Export, FDI, and Inflation) on GDP.

4. Model Diagnostics and Assumptions

Testing for autocorrelation using Durbin-Watson and clustering standard errors.

Checking for heteroscedasticity and using robust standard errors for valid inference.

5. Model Comparison
   
Running both Fixed and Random Effects models, and applying the Hausman Test to determine the better fit.

6. Statistical Significance and Economic Insight
   
Interpreting the sign, size, and significance of each coefficient in the context of macroeconomic policy.

[📁Source Of Data]

The dataset used in this project was provided by a third party and is not publicly available. It includes macroeconomic indicators for multiple countries over several 

years, used here solely for analytical and educational purposes.


### 🔢 Dataset Description

The dataset used in this project is a balanced panel data structure comprising 10 countries observed over 33 years, giving a total of 374 observations after cleaning.



| Variable         | Type        | Description                                                           |
|------------------|-------------|------------------------------------------------------------------------|
| `Country`        | Categorical | Country identifier for each observation                               |
| `Years`          | Time        | The year of observation (e.g., 1991–2024)                              |
| `GDP`            | Continuous  | Gross Domestic Product (in USD) — the **target** variable              |
| `Exchange_Rate`  | Continuous  | Official exchange rate (local currency units per USD)                 |
| `Export`         | Continuous  | Total value of exports (in USD)                                       |
| `FDI`            | Continuous  | Foreign Direct Investment net inflows (in USD)                        |
| `Inflation`      | Continuous  | Inflation rate (annual % change in Consumer Price Index - CPI)        |


## Tools Used

Tools: Excel and Python

Libraries: pandas, numpy, matplotlib, Seaborn, statsmodel,linearmodels

## 🧿Methodology

1️⃣ Data Cleaning & Preparation

2️⃣ Exploratory Data Analysis (EDA)

Performed visual and statistical summaries to understand trends, relationships, and anomalies.

Used lineplots to visualize the trend

### 📊 Descriptive Statistics Summary

| Variable       | Count | Mean         | Std Dev       | Min           | 25%           | 50% (Median)  | 75%           | Max           |
|----------------|-------|--------------|---------------|---------------|---------------|---------------|---------------|---------------|
| Years          | 374   | 2007.50      | 9.82          | 1991.00       | 1999.00       | 2007.50       | 2016.00       | 2024.00       |
| GDP            | 374   | 669,333.40   | 1,266,117.00  | 9,159.88      | 61,750.43     | 170,274.20    | 338,632.70    | 6,604,113.00  |
| Exchange Rate  | 374   | 121.69       | 202.71        | 0.28          | 6.83          | 23.67         | 93.21         | 732.40        |
| Export         | 331   | 8.16e+11     | 1.23e+12      | 4.49e+09      | 5.22e+10      | 1.50e+11      | 1.27e+12      | 6.21e+12      |
| FDI            | 358   | 5.06         | 11.99         | -6.90         | 0.70          | 2.38          | 5.55          | 161.82        |
| Inflation      | 360   | 5.27         | 5.81          | -11.69        | 2.43          | 4.38          | 6.91          | 36.96         |

3️⃣ Pre-estimation assumption tests

### 🧮 Multicollinearity 

| Feature        | VIF      |
|----------------|----------|
| const          | 3.187473 |
| Exchange_Rate  | 3.121850 |
| Export         | 3.022551 |
| FDI            | 1.013545 |
| Inflation      | 1.054570 |


### 📉 ADF (Augmented Dickey-Fuller) Test Results for Unit Root

| Country             | ADF p-value |
|---------------------|-------------|
| Algeria             | 0.8972      |
| Botswana            | 0.7066      |
| Cabo Verde          | 0.2788      |
| Equatorial Guinea   | 0.0150      |
| Gabon               | 0.5105      |
| Libya               | 0.5308      |
| Mauritius           | 0.9581      |
| Namibia             | 0.7029      |
| Seychelles          | 0.7482      |
| South Africa        | 0.6304      |

### 🔁 ADF Test Results After First Differencing

| Country             | ADF p-value     |
|---------------------|-----------------|
| Algeria             | 0.0023          |
| Botswana            | 1.12e-07        |
| Cabo Verde          | 4.50e-07        |
| Equatorial Guinea   | 0.6593          |
| Gabon               | 1.40e-05        |
| Libya               | 6.89e-15        |
| Mauritius           | 2.63e-16        |
| Namibia             | 0.1353          |
| Seychelles          | 0.0001          |
| South Africa        | 0.0003          |

4️⃣ Panel Data Modeling

### 📊 Fixed Effects Model Summary

| Metric                        | Value       |
|------------------------------|-------------|
| Dependent Variable           | GDP         |
| Observations                 | 303         |
| Entities                     | 10          |
| Time Periods                 | 34          |
| Estimator                    | PanelOLS    |
| R-squared (Within)           | 0.5623      |
| R-squared (Between)          | 0.5454      |
| R-squared (Overall)          | 0.4684      |
| F-statistic (robust)         | 92.815      |
| P-value                      | 0.0000      |
| Covariance Estimator         | Unadjusted  |
| Included Effects             | Entity      |
| F-test for Poolability       | 114.31      |
| Poolability P-value          | 0.0000      |

### 📌 Coefficient Estimates

| Variable        | Coefficient  | Std. Err. | T-Statistic | P-Value | 95% CI Lower | 95% CI Upper |
|----------------|--------------|-----------|-------------|---------|---------------|---------------|
| const          | 301900.0     | 57700.0   | 5.2333      | 0.0000  | 188400.0      | 415500.0      |
| Exchange_Rate  | -2060.6      | 334.3     | -6.1634     | 0.0000  | -2718.7       | -1402.6       |
| Export         | 7.452e-07    | 4.217e-08 | 17.6700     | 0.0000  | 6.622e-07     | 8.282e-07     |
| FDI            | -6064.0      | 3185.6    | -1.9036     | 0.0580  | -12330.0      | 205.9         |
| Inflation      | 4678.2       | 2528.0    | 1.8506      | 0.0653  | -297.4        | 9653.8        |


### 📊 Random Effects Model Summary

| Metric                        | Value       |
|------------------------------|-------------|
| Dependent Variable           | GDP         |
| Observations                 | 303         |
| Entities                     | 10          |
| Time Periods                 | 34          |
| Estimator                    | RandomEffects |
| R-squared (Within)           | 0.5446      |
| R-squared (Between)          | 0.7443      |
| R-squared (Overall)          | 0.6669      |
| F-statistic (robust)         | 103.71      |
| P-value                      | 0.0000      |
| Covariance Estimator         | Unadjusted  |

### 📌 Coefficient Estimates

| Variable        | Coefficient  | Std. Err. | T-Statistic | P-Value | 95% CI Lower | 95% CI Upper |
|----------------|--------------|-----------|-------------|---------|---------------|---------------|
| const          | 187500.0     | 140000.0  | 1.3391      | 0.1816  | -88030.0      | 462900.0      |
| Exchange_Rate  | -1069.8      | 312.97    | -3.4180     | 0.0007  | -1685.7       | -453.84       |
| Export         | 8.256e-07    | 4.06e-08  | 20.3340     | 0.0000  | 7.457e-07     | 9.056e-07     |
| FDI            | -6751.8      | 3381.6    | -1.9966     | 0.0468  | -13410.0      | -96.98        |
| Inflation      | 4526.8       | 2696.5    | 1.6787      | 0.0943  | -779.9        | 9833.4        |


## 🔍 Hausman Test for Model Selection

The Hausman test helps determine whether a **Fixed Effects** or **Random Effects** model is more appropriate for the panel data.

| Test Statistic | Degrees of Freedom | P-value | Decision                            |
|----------------|--------------------|---------|-------------------------------------|
| 37.9353        | 5                  | 0.000   | Reject null hypothesis: **Fixed Effects** is preferred |

**Interpretation:**

Since the p-value is less than 0.05, we reject the null hypothesis that the preferred model is Random Effects. 

Thus, the **Fixed Effects model** provides more consistent and reliable estimates for this analysis.

## 5️⃣Post Diagnostic Assumption Test


| Test                                | Statistic / P-value         | Interpretation                                   |
|-------------------------------------|-----------------------------|--------------------------------------------------|
| Autocorrelation (Durbin-Watson)     | 0.3745                      | Presence of autocorrelation in residuals         |
| Shapiro-Wilk Test (Normality)       | p = 1.27e-19                | Residuals are not normally distributed           |

### ✅ Justification for Clustered Standard Errors
Due to the presence of **autocorrelation** and **non-normality of residuals**, clustered standard errors were applied in the fixed effects model to obtain robust and consistent inference.

## ✅ Fixed Effects Model (with Clustered Standard Errors)

Due to evidence of **autocorrelation** and **non-normality** in the residuals, we re-estimated the Fixed Effects model using **clustered standard errors** to ensure more robust inference.

### 🔒 Model Summary

| Metric                        | Value       |
|------------------------------|-------------|
| Dependent Variable           | GDP         |
| Observations                 | 303         |
| Entities                     | 10          |
| Time Periods                 | 34          |
| Estimator                    | PanelOLS (Fixed Effects) |
| R-squared (Within)           | 0.5623      |
| R-squared (Between)          | 0.5454      |
| R-squared (Overall)          | 0.4684      |
| F-statistic (Robust)         | 25.201      |
| P-value                      | 0.0000      |
| Covariance Estimator         | Clustered   |
| Included Effects             | Entity      |
| F-test for Poolability       | 114.31      |
| Poolability P-value          | 0.0000      |

### 📌 Coefficient Estimates (with Clustered SE)

| Variable        | Coefficient | Std. Error | T-Stat  | P-Value | 95% CI Lower | 95% CI Upper |
|----------------|-------------|------------|---------|---------|---------------|---------------|
| const          | 301900.0    | 116900.0   | 2.5828  | 0.0103  | 71850.0       | 532000.0      |
| Exchange_Rate  | -2060.6     | 685.51     | -3.0060 | 0.0029  | -3409.9       | -711.42       |
| Export         | 7.452e-07   | 9.26e-08   | 8.0492  | 0.0000  | 5.629e-07     | 9.274e-07     |
| FDI            | -6064.0     | 3661.2     | -1.6563 | 0.0987  | -13270.0      | 1141.9        |
| Inflation      | 4678.2      | 1459.1     | 3.2062  | 0.0015  | 1806.3        | 7550.0        |

✅ Why Clustered?
The Durbin-Watson statistic (~0.37) indicated positive autocorrelation, and the Shapiro-Wilk test p-value (~1.27e-19) showed non-normal residuals.
Hence, clustered standard errors were used to account for serial correlation and ensure valid statistical inference.

## 6️⃣ Model Interpretation


This Fixed Effects model analyzes the impact of Exchange Rate, Export, FDI, and Inflation on GDP across 10 countries over 34 years. The use of clustered standard errors adjusts for autocorrelation and heteroskedasticity.

## 🔍 Interpretation of Coefficients

## Exchange Rate

Coefficient: -2060.6

P-value: 0.0029 (statistically significant)

Interpretation: A 1-unit increase in the exchange rate is associated with a decrease of approximately 2060.6 units in GDP, holding other factors constant.

This implies that currency depreciation negatively affects GDP in these countries.

## Export

Coefficient: 7.45e-07

P-value: 0.0000 (highly significant)

Interpretation: An increase of 1 unit in export value leads to an increase of approximately 0.000000745 units in GDP.

While the coefficient is small due to scaling, it shows a positive and strong relationship between exports and GDP.

## Foreign Direct Investment (FDI)

Coefficient: -6064.0

P-value: 0.0987 (marginally insignificant at 5%, but significant at 10%)

Interpretation: A 1-unit increase in FDI is associated with a decrease of about 6064 units in GDP, which is unexpected.

This suggests that FDI may not be translating directly to GDP growth in the short run or could be crowding out domestic investment.

## Inflation

Coefficient: 4678.2

P-value: 0.0015 (statistically significant)

Interpretation: A 1-unit increase in inflation is associated with an increase of 4678.2 units in GDP, holding other variables constant.

This counterintuitive positive effect may reflect demand-driven inflation in growing economies, or a lag in inflation’s negative effects.

## ✅ Overall Takeaway

Export and Exchange Rate have strong, significant impacts on GDP, aligning with economic theory.

FDI shows a negative impact, which needs further investigation—perhaps due to structural issues or inefficient allocation.

Inflation’s positive sign is surprising but could be due to the nature of panel data and the countries involved.

## 📞 Contact

Created by Rofee'ah Tijani

🔗 [LinkedIn](#https:-//www.-linkedin.-com/-in-/-rofee-ah-tijani-713759253)

📫 For collaboration or inquiries: Send a message on LinkedIn









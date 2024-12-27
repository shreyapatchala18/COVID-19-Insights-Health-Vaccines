# Examining COVID-19 Health Outcomes and Vaccine Uptake Predictors

## Project Overview
This project analyzes county-level public health data to uncover the factors influencing COVID-19 incidence and vaccine uptake. Using regression and predictive modeling techniques, the study focuses on two main goals:
1. Assessing the relationship between in-person schooling and COVID-19 health outcomes.
2. Identifying predictors of vaccine acceptance to guide health policy and outreach strategies.

The analysis leverages the **HEW dataset** from Carnegie Mellon’s Delphi group, gathered via the COVID-19 Trends and Impact Survey on Facebook.

---

## Objectives
- Evaluate how in-person schooling affects COVID-19 incidence rates.
- Predict vaccine uptake using behavioral and attitudinal factors.
- Provide insights for public health policy and outreach during pandemics.

---

## Dataset Description
The dataset includes weekly county-level data with key variables such as:
- **Health Metrics**: COVID-19 incidence rates, symptoms, and testing data.
- **Schooling Data**: Full-time and part-time in-person schooling percentages.
- **Behavioral Indicators**: Mask-wearing habits, large event attendance, and public transit usage.
- **Vaccine Sentiments**: Likelihood to vaccinate based on recommendations from trusted sources.

Key Variables:
- `confirmed_7dav_incidence_prop`: 7-day COVID-19 incidence rate (response variable for health outcomes).
- `covid_vaccinated_or_accept`: Percentage of individuals vaccinated or willing to vaccinate (response variable for vaccine uptake prediction).
- Predictors include mask-wearing behavior, public transit use, and trust in health authorities.

---

## Methodology
1. **Exploratory Data Analysis**:
   - Visualized variable distributions using histograms and Q-Q plots.
   - Addressed missing values by removing records with critical data gaps.

2. **Regression Analysis**:
   - Log-transformed COVID-19 incidence rates to address heteroskedasticity.
   - Used sandwich estimators for robust standard errors.
   - Removed influential observations identified through Cook’s distance.

3. **Predictive Modeling**:
   - Applied Lasso regression to predict vaccine uptake.
   - Used cross-validation to select the optimal regularization parameter.
   - Retained significant predictors while excluding less impactful ones.

---

## Results
- **In-Person Schooling**: Both full-time and part-time schooling significantly correlated with higher COVID-19 incidence rates:
  - Full-time: β = 0.0067, 95% CI [0.0027, 0.0107].
  - Part-time: β = 0.0100, 95% CI [0.0057, 0.0142].
- **Vaccine Uptake**: Lasso regression explained 74.6% of variance in vaccine acceptance. Key predictors included trust in WHO and government health officials, and adherence to mask-wearing.

---

## Key Insights
- Policymakers should consider the trade-offs between in-person schooling and public health outcomes during pandemics.
- Outreach efforts should emphasize trusted health messaging and safety practices to enhance vaccine uptake.

---

## Limitations
- Self-reported survey data may introduce biases.
- Findings are context-specific to early 2021 and may not generalize to other regions or pandemic phases.

---

## Instructions to Reproduce
1. **Set Up Environment**:
   - Python 3.8+ with required libraries (`pandas`, `statsmodels`, `sklearn`, `matplotlib`).

2. **Run Scripts**:
   - Data cleaning and exploration: `data_cleaning.py`
   - Regression analysis: `regression_analysis.py`
   - Predictive modeling: `predictive_modeling.py`

3. **Generate Outputs**:
   - Diagnostic plots and regression summaries.
   - Cross-validation results for Lasso regression.

---

## Acknowledgements
Data sourced from Carnegie Mellon University’s Delphi group, as part of the COVID-19 Trends and Impact Survey.


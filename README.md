# Statistical and Predictive Modeling I (DATA 1204) Final Project: Analysis of the Effect of Smoking on Birth Weight (bwt)

# 📊 Birth Weight Analysis Using Regression Techniques

This project presents a comprehensive analysis of factors influencing **birth weight**, using both **simple** and **multiple linear regression** models in R. The analysis includes data visualization, hypothesis testing, and prediction based on real-world scenarios.



---

## 🧠 Skills Demonstrated

- Data Exploration in R  
- Linear and Multiple Regression  
- Hypothesis Testing  
- Visualization (ggplot2, lattice)  
- Model Interpretation and Evaluation  

---

## 📌 Objectives

1. **Simple Linear Regression**  
   Analyze the impact of **maternal smoking** (`smoke`) on **birth weight** (`bwt`).

2. **Multivariate Regression**  
   Assess the combined effect of variables such as:
   - Maternal smoking
   - Gestation period
   - Maternal age, weight, and height  
   ...on birth weight using a multiple linear regression model.

---

## 🧪 Dataset and Tools

- **Dataset**: `birthweights.csv` (loaded in R)
- **Tools/Libraries**:  
  `ggplot2`, `psych`, `lattice`, `gmodels`, `base R` functions

---

## 📈 Exploratory Data Analysis

### Descriptive Statistics

| Variable     | Range           | Mean     | Std Dev | Key Insight                                |
|--------------|------------------|----------|---------|---------------------------------------------|
| Birth Weight (bwt)| 1559–4990 grams  | 3387.0 g | 519.6   | Normally distributed                        |
| Gestation    | 148–353 days     | 279.1    | 16.01   | Mostly full-term pregnancies                |
| Age (Maternal age)         | 14–46 years      | 27.3     | 5.93    | Includes both teen and older mothers        |
| Height       | 135–183 cm       | 162.7    | 6.51    | Moderate variability                        |
| Weight       | 39.5–113.4 kg    | 58.3     | 9.40    | Significant variability                     |

- **Visualization**: Histogram of `bwt` suggested a near-normal distribution.

---

## 🧪 Hypothesis Testing

**H₀**: μ = 3400 grams  
**H₁**: μ ≠ 3400 grams  

- **z = -0.87**, **p-value = 0.3836**
- ✅ Failed to reject the null hypothesis - not enough evidence to say the mean birth weight differs from 3400 grams.

---

## 📉 Simple Linear Regression

**Model**: `bwt ~ smoke`

- **Intercept**: 3489.49 (non-smokers' average birth weight)  
- **Coefficient (smoke)**: -262.69 → Smoking decreases birth weight by ~263 grams  
- **R²**: 0.061 → Smoking explains 6.1% of birth weight variation  
- **F-statistic**: 76.02, **p < 2.2e-16** → Smoking is statistically significant  
- 📊 Scatterplot used to visualize the trend

---

## 📊 Multivariate Regression

**Model**: `bwt ~ gestation + age + height + weight + smoke + region`

### Significant Predictors:

| Predictor | p-value     | Effect                         |
|-----------|-------------|--------------------------------|
| Gestation | < 2e-16     | Longer gestation → higher bwt  |
| Height    | 1.24e-07    | Taller mother → higher bwt     |
| Weight    | 0.0235      | Heavier mother → higher bwt    |
| Smoke     | < 2e-16     | Smoking → lower bwt            |

- **Not Significant**: Age, region
- **Adjusted R²**: 0.2478 → ~25% of variance explained by the model

---

## 🔮 Prediction

**Scenario**:  
- Gestation = 200 days  
- Height = 200 cm  
- Weight = 100 kg  
- Smoke = 1 (yes)

**Predicted Birth Weight**: **2867.26 grams**

---

## ✅ Conclusions

- **Smoking** has a statistically significant **negative** effect on birth weight.
- Other key predictors: **gestation**, **maternal height**, and **maternal weight**.
- **Maternal age** and **region** were not statistically significant in this dataset.
- The model explains ~25% of the variability, suggesting other unmeasured factors may also impact birth weight.

---



# Seoul Bike Rental Prediction
## Project Overview
This project aims to predict the demand for bike rentals in Seoul based on various environmental and temporal factors. Using data from the **UCI Machine Learning Repository**, I explored trends and developed predictive models, with **XGBoost achieving the highest accuracy (R² = 0.917)**.

The analysis revealed that **temperature, humidity, and precipitation** strongly impact bike demand, while **commuting patterns drive peak usage during morning and evening hours**. Seasonal trends indicate **higher rentals in summer and a decline in winter**, reinforcing the need for dynamic bike redistribution strategies. 

This project demonstrates expertise in **data science, feature engineering, and advanced predictive modeling**, contributing to smarter, data-driven transportation solutions.

📄 **Full Report:** https://ilgiz-almv.github.io/seoul_bike_rental_ml/report.html

## Dataset

- **Source (UCI Machine Learning Repository):** https://archive.ics.uci.edu/dataset/560/seoul+bike+sharing+demand
- **Observations:** 8,760 hourly records
- **Features:** Temperature, humidity, wind speed, visibility, solar radiation, rainfall, snowfall, seasons, holiday indicators, and more.

## Exploratory Data Analysis (EDA)

- The **dataset is complete**, with no missing or duplicate records.
- The distribution of the **response variable is right-skewed**, resembling a Poisson-like pattern.
- **Temperature, humidity, and solar radiation** show strong correlations with bike rental trends, particularly in specific seasons.
- Even **minimal precipitation significantly impacts** bike rental demand.
- **Bike rentals peak** during commuting hours (**7-9 AM & 5-9 PM**), highlighting daily travel patterns.
- **Seasonality is a crucial factor**: Rentals increase in summer and decline in winter.
- **Working and non-working days exhibit distinct rental behaviors**, emphasizing the importance of considering weekday effects.
- **Feature Engineering Enhancements**: Introduced polynomial transformations, interaction terms, and categorical indicators to improve model predictive power.

## Predictive Models
### 1️⃣ Baseline Linear Regression (No Transformations for Benchmarking)

- **Performance:**
  - RMSE: **355.51**
  - MAE: **230.74**
  - R²: **0.70**
- **Key Issue:** Poor fit due to heteroscedasticity, missing non-linear interactions, polynomial terms, and the absence of key features (categorical factors)

![Baseline Linear Regression](images/Linear%20Regression%20Base.png)

---

### 2️⃣ Enhanced Linear Regression (After Feature Engineering)

- **Performance Improvement:**
  - RMSE: **255.14**
  - MAE: **157.22**
  - R²: **0.845**
- **Key Observation:** Despite significant improvements, **heteroscedasticity remains**, indicating the need for a more advanced model.

![Enhanced Linear Regression](images/Linear%20Regression%20Enhanced.png)

---

### 3️⃣ XGBoost (Best Model)

- **Final Performance:**
  - RMSE: **184.24**
  - MAE: **113.62**
  - R²: **0.917** (Best predictive power!)
- **Key Takeaway:** XGBoost **captured complex relationships effectively** and provided the most stable and accurate predictions.

![XGBoost Model](images/XGBoost%20on%20test%20data.png)

## Conclusion & Insights
- **EDA & Feature Engineering are crucial** – Enhanced linear regression significantly improved performance over the baseline model.
- **Linear Models have limitations** – Even with feature engineering, heteroscedasticity persisted.
- **XGBoost is the best model** – It captured complex relationships effectively, delivering the highest accuracy.
- **Business Application:** The model can be used to optimize **bike distribution, dynamic pricing strategies, and resource planning** for urban mobility.

---

## 📊 View the Analysis
📄 **Full Report (no need to run code):** https://ilgiz-almv.github.io/seoul_bike_rental_ml/report.html

## 🛠 How to Run the Project
If you want to run the analysis on your own machine, follow these steps:

### 1️⃣ Clone the repository:
```sh
git clone https://github.com/ilgiz-almv/seoul_bike_rental_ml.git
cd seoul_bike_rental_ml
```
### 2️⃣ Install required R packages:
```r
install.packages(c("caret", "corrplot", "dplyr", "ggcorrplot", "ggplot2", "gridExtra", "lmtest", "lubridate", "MASS", "Metrics", "randomForest", "SHAPforxgboost", "xgboost"))
```
### 3️⃣ Execute the RMarkdown script to reproduce the analysis:
```r
rmarkdown::render("notebook/seoul_bike_rental.Rmd")
```

## Technologies Used

- **Programming Language:** R (RMarkdown)
- **Machine Learning Models:** Linear Regression, Poisson Regression, Negative Binomial Regression, Random Forest, XGBoost
- **Visualization:** ggplot2, SHAP values

## Author

- **Ilgiz Almukhametov**  
- **GitHub:** https://github.com/ilgiz-almv
- **LinkedIn:** https://www.linkedin.com/in/ilgiz-almv/

## License
This project is licensed under the **MIT License**.

**GitHub Repository:** https://github.com/ilgiz-almv/seoul_bike_rental_ml


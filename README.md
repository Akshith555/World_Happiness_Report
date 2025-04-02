# 🌍 World Happiness Report Analysis & ML Modeling

This project is an end-to-end data science pipeline that analyzes global happiness scores from 2015 to 2019 using data from the World Happiness Report. It includes data cleaning, exploratory analysis, multiple machine learning models, SHAP explainability, and an interactive Power BI dashboard.

---

## 📁 Project Structure

```
.
├── data/
│   ├── 2015.csv to 2019.csv           # Raw datasets
│   ├── world_happiness_final.csv      # Cleaned combined dataset
│   └── world_happiness_predictions.csv # Predictions from best model
├── models/
│   ├── happiness_rf_model.pkl
│   ├── happiness_gbr_model.pkl
│   ├── happiness_xgb_model.pkl
├── notebooks/
│   └── Untitled16.ipynb               # Jupyter notebook with code
├── visuals/
│   └── Power BI report screenshots
```

---

## 📊 Project Workflow

### 1. Data Collection & Cleaning
- Unified columns across datasets from 2015–2019
- Handled missing values (e.g., mean imputation for Trust)
- Combined and saved as `world_happiness_final.csv`

### 2. Exploratory Data Analysis
- Score distribution, top countries, heatmaps
- Yearly trends and boxplots by happiness rank bins

### 3. Feature Engineering
- Features: GDP, Social Support, Health, Freedom, Generosity, Trust
- Target: Happiness Score

### 4. Machine Learning Models
- Linear Regression
- Random Forest Regressor
- Gradient Boosting Regressor (GBR)
- XGBoost Regressor

Metrics used: **R² Score**, **RMSE**

### 5. Hyperparameter Tuning
- Used `RandomizedSearchCV` for RF, GBR, and XGB

### 6. SHAP Interpretability
- Global feature importance (bar/beeswarm)
- Local prediction explanations using force plots

### 7. Model Persistence
- Saved trained models using `joblib` to `models/` folder
- Final predictions saved in `data/world_happiness_predictions.csv`

---

## 📈 Power BI Dashboard

An interactive Power BI report was created to visually explore happiness trends across countries and years:

- 🌍 Global & country-level happiness insights
- 😃 Top 10 happiest and 😞 unhappiest countries
- 💰 Top 10 GDP-performing countries
- 📅 Year filters (2015–2019)
- 🗺️ World map visualization of happiness scores
- 📊 Variable sliders and correlation insights

> 🎯 This dashboard helps communicate results with non-technical audiences effectively.

---

## 🔧 Tech Stack

- **Languages & Libraries**: Python, Pandas, Scikit-learn, XGBoost, SHAP, Matplotlib, Seaborn
- **Visualization**: Power BI, SHAP
- **Modeling**: Regression models + Hyperparameter Tuning
- **Deployment Ready**: Models saved with `joblib` for reuse

---

## ✅ Results Summary

| Model             | R² Score | RMSE  |
|-------------------|----------|-------|
| Random Forest     | 0.795    | 0.500 |
| Gradient Boosting | 0.782    | 0.515 |
| XGBoost           | 0.788    | 0.507 |

_(See notebook for exact values)_

---

## 👩‍💻 Author

**Sagarika**  
Master’s in Data Science | Illinois Institute of Technology  
[LinkedIn](#) | [GitHub](#)

---

## 📌 Future Enhancements

- Deploy interactive predictor using Streamlit
- Add newer datasets (2020 onwards)
- Automate model training & reporting pipeline


---

## 🏳️ Enhancing Dataset with Country Flags

To make the Power BI dashboard more visually engaging, a separate notebook was created to generate country flag image URLs:

- ✅ Uses `pycountry` to retrieve ISO2 country codes for each country
- 🖼️ Constructs flag image links via two APIs:
  - [Country Flags API](https://countryflagsapi.com/png/{code})
  - [Flagpedia](https://flagpedia.net/data/flags/normal/{code}.png)
- 📊 Adds a new `FlagURL` column to the dataset
- 💾 Saves updated file as:
  - `world_happiness_predictions_with_flags.csv`
  - or `world_happiness_predictions_with_flags_flagpedia.csv`

This dataset can then be used in Power BI to display flags alongside country names, enhancing clarity and presentation value.

---


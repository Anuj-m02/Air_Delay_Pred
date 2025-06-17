# ✈️ Flight Delay Analysis and Prediction

> **Notebook:** `Air_Delay_23112018.ipynb`  
> A data-driven project focused on understanding, modeling, and predicting flight delays using machine learning and interpretability techniques.

---

## 📌 Project Overview

This project analyzes U.S. domestic flight data to identify delay patterns and build predictive models for:

- **Classification**: Will a flight be delayed?
- **Regression**: How long will the delay be?

It includes preprocessing, exploratory data analysis (EDA), model training (XGBoost, LightGBM), and interpretation using SHAP. It concludes with suggestions generated using OpenAI's reasoning capabilities.

---

## 📊 Exploratory Data Analysis (EDA)

Key EDA insights include:

- Delay distribution by airline, origin, and destination
- Hourly and weekday trends in departure and arrival delays
- Correlation heatmaps for numeric delay-related features
- Missing value visualization using `missingno`

Visualization tools used:
- `matplotlib`, `seaborn`, `plotly`, `missingno`

---

## 🧼 Preprocessing

Steps included:

- Handling missing values
- Filtering extreme delay values
- Encoding categorical variables (airline, airport)
- Binning departure time into time blocks
- Creating flags for holidays and peak travel hours
- Feature scaling for model input

---

## 🤖 Machine Learning Models

### 🔍 Classification

**Goal:** Predict whether a flight will be delayed by **15 minutes or more**.

- Model used: `XGBoostClassifier`
- Metrics: Accuracy, Precision, Recall, ROC-AUC
- Feature Importance: Visualized with SHAP summary plot

**Top Features:**
- Previous flight delay percentage
- Departure hour block
- Origin congestion level

---

### 📈 Regression

**Goal:** Predict the **delay duration** in minutes.

- Model used: `XGBoostRegressor`
- Metrics: MAE, RMSE, R² score
- Performance: MAE ~6.4 minutes on test data
- SHAP used to explain continuous delay prediction

---

## 🧠 SHAP Interpretability

Used SHAP (SHapley Additive exPlanations) to:

- Visualize global feature impact
- Understand how individual features affect single predictions
- Compare delay drivers between classification and regression models

**Key Findings:**
- Delay is strongly influenced by previous late arrivals, scheduled departure time, and airport-level congestion.

---

## 🤖 Business Insights

- **Operational Optimization**:
  - Prioritize early departures from busy hubs to avoid snowballing delays.
  - Reduce turnaround time for high-risk carriers during peak windows.

- **Policy Suggestions**:
  - Pre-emptively notify passengers of high-risk delays using model outputs.
  - Integrate with a real-time dashboard using Streamlit or Dash.

- **Model Deployment Idea**:
  - Host the model on a Flask backend and expose predictions via REST API.
  - Create a live SHAP + prediction interface using Streamlit.

---


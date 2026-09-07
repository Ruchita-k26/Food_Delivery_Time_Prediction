# 🍔 Food Delivery Time Prediction

## 📌 Project Overview

This project focuses on predicting food delivery time using operational and environmental factors such as distance, weather, traffic conditions, preparation time, courier experience, time of day, and vehicle type.

The project uses **Linear Regression** to predict the expected delivery time in minutes.

---

## 🎯 Business Problem

Late food deliveries can negatively affect customer satisfaction and the overall delivery experience.

Accurate delivery-time prediction can help businesses:

- Provide realistic Estimated Time of Arrival (ETA) to customers
- Improve delivery and dispatch planning
- Identify factors affecting delivery time
- Support operational decision-making
- Improve overall customer satisfaction

---

## 🎯 Project Objective

The main objective is to build a machine learning model that predicts:

> **Delivery Time (minutes)**

based on different delivery-related factors.

---

## 📊 Dataset

The dataset contains **1,000 records and 9 columns**.

### Target Variable

- `Delivery_Time_min` – Actual delivery time in minutes

### Features

| Feature | Description |
|---|---|
| `Order_ID` | Unique order identifier |
| `Distance_km` | Delivery distance in kilometers |
| `Weather` | Weather condition during delivery |
| `Traffic_Level` | Traffic congestion level |
| `Time_of_Day` | Time period of delivery |
| `Vehicle_Type` | Type of delivery vehicle |
| `Preparation_Time_min` | Food preparation time in minutes |
| `Courier_Experience_yrs` | Courier experience in years |
| `Delivery_Time_min` | Target variable – delivery time in minutes |

---

## 🔍 Project Workflow

The project follows a complete machine learning workflow:

1. Import required libraries
2. Load the dataset
3. Perform descriptive analysis
4. Check dataset shape and statistics
5. Check for missing values
6. Check for duplicate records
7. Handle missing values
8. Perform Exploratory Data Analysis (EDA)
9. Prepare features and target variable
10. Encode categorical variables
11. Split data into training and testing sets
12. Train Linear Regression model
13. Generate predictions
14. Evaluate model performance
15. Interpret the results

---

## 🧹 Data Cleaning

### Missing Values

Missing values were identified in:

- Weather
- Traffic Level
- Time of Day
- Courier Experience

Missing categorical values were handled using the **mode** of the respective column.

After the cleaning process, there were no remaining missing values.

### Duplicate Records

Duplicate records were checked and no duplicate rows were found.

---

## 📈 Exploratory Data Analysis

Exploratory Data Analysis was performed to understand the distribution of variables and relationships between delivery time and the available features.

The analysis included:

- Univariate analysis
- Distribution analysis
- Categorical variable analysis
- Relationship analysis
- Correlation analysis
- Visualization of important patterns

---

## 📊 Statistical Testing

Statistical hypothesis testing was performed to determine whether categorical factors have a statistically significant effect on delivery time.

A significance level of **α = 0.05** was used.

### 1. Vehicle Type — One-Way ANOVA

**Null Hypothesis (H₀):**  
There is no significant difference in mean delivery time among different vehicle types.

**Alternative Hypothesis (H₁):**  
At least one vehicle type has a significantly different mean delivery time.

**Result:**

- F-statistic = 0.5894
- p-value = 0.5549
- p-value > 0.05

**Outcome:** Failed to reject the null hypothesis.

There is no statistically significant difference in delivery time among Bike, Scooter, and Car.

---

### 2. Traffic Level — One-Way ANOVA

**Null Hypothesis (H₀):**  
There is no significant difference in mean delivery time across traffic levels.

**Alternative Hypothesis (H₁):**  
At least one traffic level has a significantly different mean delivery time.

**Result:**

- F-statistic = 19.7513
- p-value = 3.87 × 10⁻⁹
- p-value < 0.05

**Outcome:** Rejected the null hypothesis.

Traffic level has a statistically significant relationship with delivery time.

A **Tukey's HSD post-hoc test** was then used to identify which traffic-level groups differed significantly.

The results showed significant pairwise differences between the traffic groups.

---

### 3. Weather — One-Way ANOVA

**Null Hypothesis (H₀):**  
There is no significant difference in mean delivery time across weather conditions.

**Alternative Hypothesis (H₁):**  
At least one weather condition has a significantly different mean delivery time.

**Result:**

- F-statistic = 10.4991
- p-value = 2.47 × 10⁻⁸
- p-value < 0.05

**Outcome:** Rejected the null hypothesis.

Weather conditions have a statistically significant relationship with delivery time.

Tukey's HSD post-hoc testing was used to identify the specific weather groups contributing to the difference.

### Statistical Testing Summary

| Factor | Test | p-value | Outcome |
|---|---|---:|---|
| Vehicle Type | One-Way ANOVA | 0.5549 | Not Significant |
| Traffic Level | One-Way ANOVA | 3.87 × 10⁻⁹ | Significant |
| Weather | One-Way ANOVA | 2.47 × 10⁻⁸ | Significant |

### Key Statistical Insights

- **Traffic level significantly affects delivery time.**
- **Weather conditions significantly affect delivery time.**
- **Vehicle type does not show a statistically significant difference in delivery time.**
- Snowy conditions showed particularly higher delivery times compared with most other weather conditions.
- Rainy conditions also showed higher delivery times compared with clear weather.

## ⚙️ Feature Engineering & Preprocessing

Categorical variables were converted into numerical features using **One-Hot Encoding**.

The categorical variables included:

- Weather
- Traffic Level
- Time of Day
- Vehicle Type

After encoding, the feature dataset contained **18 input variables**.

---

## 🤖 Machine Learning Model

### Linear Regression

Linear Regression was used to predict food delivery time based on the available operational and environmental factors.

The dataset was split into:

- **70% Training Data**
- **30% Testing Data**

A `random_state = 42` was used to ensure reproducibility.

### Model Performance

The **70/30 train-test split produced the best Linear Regression performance** among the evaluated configurations.

| Metric | Result |
|---|---:|
| **R² Score** | **83.23%** |
| **MAE** | **6.06 minutes** |
| **MSE** | **84.95** |
| **RMSE** | **9.22 minutes** |
| **MAPE** | **10.62%** |

### Interpretation

The model explains approximately **83.23% of the variation in delivery time**.

The MAE of **6.06 minutes** means that, on average, the model's predicted delivery time differs from the actual delivery time by approximately 6 minutes.

The MAPE of **10.62%** indicates that the model's average prediction error is around 10.6%.
---

---

## 🔑 Key Findings

- The final Linear Regression model achieved an **R² score of 83.23%** on the 30% test dataset.
- The model's average prediction error was approximately **6.06 minutes** based on MAE.
- **Traffic level** showed a statistically significant difference in delivery times.
- **Weather conditions** showed a statistically significant difference in delivery times.
- **Vehicle type** did not show a statistically significant difference in delivery time.
- Statistical testing using **One-Way ANOVA** was followed by **Tukey's HSD** for significant categorical factors.
- Snowy conditions showed particularly higher delivery times compared with most other weather conditions.

## 💡 Business Value

A delivery-time prediction model can help food delivery businesses:

- Improve customer ETA estimates
- Plan courier allocation more effectively
- Identify potential delivery delays
- Improve operational efficiency
- Support better customer communication

---

## 🛠️ Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Plotly
- Scikit-learn
- SciPy
- Jupyter Notebook

---

## 👩‍💻 Author

**Ruchita Kumbhare**

Aspiring Data Analyst | Python | SQL | Power BI | Machine Learning


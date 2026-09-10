# Customer Churn Prediction & Customer Segmentation

An end-to-end **Data Analytics and Machine Learning project** that predicts customer churn, identifies high-risk customers, segments customers using K-Means clustering, and provides business recommendations through an interactive Power BI dashboard.

---

## 📌 Project Overview

Customer churn is a major challenge for subscription-based businesses. Identifying customers who are likely to leave allows companies to take proactive retention actions.

This project combines:

* Exploratory Data Analysis
* Feature Engineering
* SQL Analytics
* Machine Learning
* Churn Probability Prediction
* Classification Threshold Optimization
* K-Means Customer Segmentation
* Business Priority Analysis
* Power BI Dashboard
* Data-driven Retention Recommendations

The goal is to answer three key business questions:

1. **Which customers are likely to churn?**
2. **What characteristics are associated with customer churn?**
3. **Which customers should the business prioritize for retention?**

---

## 🎯 Objectives

* Analyze customer demographics, services, contracts, tenure, and spending.
* Identify the major factors associated with customer churn.
* Build machine learning models to predict customer churn.
* Compare multiple classification algorithms.
* Optimize the churn classification threshold based on business objectives.
* Segment customers using K-Means clustering.
* Identify high-risk and high-value customers.
* Create an interactive Power BI dashboard.
* Translate analytical results into actionable retention strategies.

---

## 📊 Dataset

The project uses the **IBM Telco Customer Churn dataset**.

The dataset contains customer information including:

* Customer demographics
* Tenure
* Contract type
* Internet service
* Payment method
* Monthly charges
* Total charges
* Additional services
* Churn status

### Dataset Dimensions

Approximately **7,000+ customer records** with 20+ customer attributes.

### Target Variable

`Churn`

* `Yes` → Customer churned
* `No` → Customer remained

---

## 🛠️ Technology Stack

| Category                | Tools               |
| ----------------------- | ------------------- |
| Programming             | Python              |
| Data Manipulation       | Pandas, NumPy       |
| Visualization           | Matplotlib, Seaborn |
| Machine Learning        | Scikit-learn        |
| Database / Analytics    | SQL, SQLite         |
| Clustering              | K-Means             |
| Dashboard               | Microsoft Power BI  |
| Model Persistence       | Joblib              |
| Development Environment | Google Colab        |
| Version Control         | Git & GitHub        |

---

# 🔄 Project Workflow

```text
Raw Customer Data
        ↓
Data Cleaning
        ↓
Exploratory Data Analysis
        ↓
Feature Engineering
        ↓
SQL Business Analysis
        ↓
ML Preprocessing
        ↓
Model Training
        ↓
Model Comparison
        ↓
Churn Prediction
        ↓
Threshold Optimization
        ↓
Customer Segmentation
        ↓
Business Priority Analysis
        ↓
Power BI Dashboard
        ↓
Business Recommendations
```

---

# 🧹 1. Data Cleaning

The dataset was prepared for analysis and machine learning by:

* Handling missing values
* Converting `TotalCharges` into numeric format
* Checking duplicate records
* Validating data types
* Preserving the customer identifier
* Preparing the churn target variable

---

# 📈 2. Exploratory Data Analysis

Several customer characteristics were analyzed to understand churn behavior.

### Key analysis areas

* Churn distribution
* Churn by contract type
* Churn by tenure
* Churn by payment method
* Churn by internet service
* Churn by monthly charges
* Churn by total charges
* Churn by senior citizen status
* Service adoption and churn

EDA was used to identify patterns that could be useful for customer retention strategies.

---

# ⚙️ 3. Feature Engineering

Additional features were created to improve customer-level analysis.

### Engineered Features

#### TenureGroup

Customers were grouped into:

```text
New
Growing
Established
Loyal
```

#### TotalServices

Counts the number of services used by each customer.

#### AverageMonthlySpend

Calculated using customer total charges and tenure.

#### IsNewCustomer

Identifies customers with short tenure.

#### HighMonthlyCharge

Identifies customers with relatively high monthly charges.

---

# 🗄️ 4. SQL Analysis

SQLite was used to perform business-oriented analysis.

Examples include:

* Total customer count
* Overall churn rate
* Churn by contract
* Churn by payment method
* Churn by internet service
* Churn by tenure group
* Average monthly charges by churn status
* High-value customer analysis
* New customer churn analysis

This demonstrates the use of SQL alongside Python for business analytics.

---

# 🤖 5. Machine Learning

The following classification algorithms were trained and compared:

1. Logistic Regression
2. Decision Tree
3. Random Forest
4. Gradient Boosting

### Evaluation Metrics

Models were evaluated using:

* Accuracy
* Precision
* Recall
* F1 Score
* ROC-AUC
* Confusion Matrix
* Classification Report

---

# 🏆 6. Model Performance

The initial model comparison produced the following results:

| Model               | Accuracy | Precision | Recall |         F1 |    ROC-AUC |
| ------------------- | -------: | --------: | -----: | ---------: | ---------: |
| Gradient Boosting   |   80.48% |    67.74% | 50.53% |     57.89% | **84.59%** |
| Logistic Regression |   79.42% |    63.12% | 54.01% | **58.21%** |     84.03% |
| Decision Tree       |   79.63% |    65.82% | 48.40% |     55.78% |     83.64% |
| Random Forest       |   73.95% |    81.82% |  2.41% |      4.68% |     81.67% |

Gradient Boosting provided the strongest ROC-AUC performance.

---

# 🎯 7. Classification Threshold Optimization

Instead of relying only on the default 0.50 classification threshold, multiple probability thresholds were evaluated.

The selected working threshold was:

```text
0.30
```

### Optimized Results

| Metric    |     Result |
| --------- | ---------: |
| Threshold |   **0.30** |
| Accuracy  | **77.15%** |
| Precision | **55.04%** |
| Recall    | **75.94%** |
| F1 Score  | **63.82%** |

The threshold optimization significantly increased recall.

This is useful for a churn-retention scenario because the business may prefer identifying more potential churners, even if that results in contacting some customers who ultimately would not churn.

---

# 👥 8. Customer Segmentation

K-Means clustering was used to identify customer groups based on behavioral and financial characteristics.

### Segmentation Features

* Tenure
* Monthly Charges
* Total Charges
* Total Services
* Average Monthly Spend
* Senior Citizen status

Features were standardized before applying K-Means.

The Elbow Method was used to evaluate the appropriate number of clusters.

---

# 📊 9. Customer Risk Classification

Customers were assigned a churn probability using the trained machine learning model.

Risk categories were created for business interpretation:

```text
High Risk       → Churn Probability ≥ 70%
Medium Risk     → 30% – 69.99%
Low Risk        → < 30%
```

These risk categories are intended as business-oriented classification bands and can be adjusted according to retention campaign capacity and business cost.

---

# 💼 10. Business Priority Analysis

Customer churn probability was combined with customer spending information to prioritize retention activities.

A higher priority can be assigned to customers with:

```text
High Churn Probability
        +
High Monthly Charges
        +
High Customer Value
```

This helps businesses focus retention resources on customers where preventing churn may have greater financial impact.

---

# 📊 11. Power BI Dashboard

An interactive Power BI dashboard was developed to communicate the analytical findings.

### Dashboard Components

#### Executive Overview

* Total Customers
* Churn Rate
* Actual Churn Customers
* Predicted Churn Customers
* High-Risk Customers
* Churn by Contract
* Churn by Tenure
* Churn by Payment Method
* Customer Risk Distribution

#### Churn Risk Analysis

* Churn probability
* Risk-level distribution
* Risk by contract
* Risk by internet service
* High-risk customer table

#### Customer Segmentation

* Customer count by segment
* Average tenure
* Average monthly charges
* Segment churn rate
* Segment profiles

---

## 💡 12. Business Recommendations

Based on the analysis, the following strategies can be considered:

### 1. Target High-Risk Customers

Prioritize customers with high predicted churn probability.

Possible actions:

* Personalized retention offers
* Dedicated customer support
* Loyalty benefits
* Contract incentives

### 2. Encourage Long-Term Contracts

Customers with short-term contracts can be encouraged to move toward longer contracts through:

* Discounts
* Loyalty rewards
* Bundled services
* Contract upgrade incentives

### 3. Improve Early Customer Experience

New customers can be targeted with:

* 30/60/90-day onboarding programs
* Early satisfaction surveys
* Proactive support
* Welcome offers

### 4. Address Price Sensitivity

Customers with high monthly charges may benefit from:

* Customized plans
* Service bundles
* Cost-saving packages
* Personalized pricing offers

### 5. Prioritize High-Value Customers

Retention resources should consider both:

**Probability of churn + customer value**

rather than churn probability alone.

---

# 📁 Project Structure

```text
customer-churn-prediction-segmentation/
│
├── data/
│   └── WA_Fn-UseC_-Telco-Customer-Churn.csv
│
├── notebooks/
│   └── customer_churn_analysis.ipynb
│
├── sql/
│   └── churn_analysis.sql
│
├── model/
│   └── best_churn_model.pkl
│
├── outputs/
│   ├── model_performance.csv
│   ├── customer_churn_predictions.csv
│   ├── customer_segments.csv
│   ├── segment_summary.csv
│   └── business_retention_priority.csv
│
├── powerbi/
│   └── customer_churn_dashboard.pbix
│
├── screenshots/
│   ├── dashboard_overview.png
│   ├── churn_analysis.png
│   └── customer_segmentation.png
│
└── README.md
```

---

# 📌 Key Project Outcomes

* Built an end-to-end customer churn analytics pipeline.
* Compared four machine learning classification algorithms.
* Achieved **84.59% ROC-AUC** with Gradient Boosting.
* Improved churn recall to **75.94%** through threshold optimization.
* Applied K-Means clustering for customer segmentation.
* Created customer-level churn risk classifications.
* Developed retention prioritization logic.
* Built an interactive Power BI dashboard.
* Converted machine learning outputs into actionable business recommendations.

---

# 🚀 Future Improvements

Potential extensions include:

* Hyperparameter optimization using GridSearchCV or RandomizedSearchCV
* SHAP-based model explainability
* Probability calibration
* Cost-sensitive learning
* Customer Lifetime Value (CLV) modeling
* Automated model retraining
* Real-time churn prediction API
* Automated Power BI data refresh
* A/B testing of retention campaigns

---

# 👨‍💻 Skills Demonstrated

This project demonstrates practical experience in:

```text
Python
Pandas
NumPy
SQL
SQLite
Data Cleaning
EDA
Feature Engineering
Machine Learning
Classification
Model Evaluation
Threshold Optimization
K-Means Clustering
Customer Segmentation
Business Analytics
Power BI
Data Visualization
Business Recommendations
```

---

## 📜 License

This project is intended for educational and portfolio purposes.

---

## ⭐ Conclusion

This project demonstrates how customer data can be transformed into actionable business intelligence by combining **Data Analytics, SQL, Machine Learning, Customer Segmentation, and Power BI**.

The final solution helps identify customers at risk of churn, understand customer behavior, prioritize retention efforts, and communicate insights through an interactive dashboard.

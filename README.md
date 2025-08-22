# 🛒 Walmart Weekly Sales Forecasting

## 📌 Project Overview
This project aims to forecast **weekly sales for Walmart stores** using **machine learning** and **time series models**.  
Accurate forecasting is crucial for Walmart to manage **inventory, staffing, promotions, and supply chain efficiency**.  

We explore both **Machine Learning (XGBoost, LightGBM, Random Forest)** and **Time Series (Prophet)** approaches to model sales trends, seasonality, and external economic factors.  

---

## 🎯 Problem Statement
Retail giants like Walmart face the challenge of predicting **future demand** while accounting for:
- Seasonal variations (holidays, Black Friday, Christmas, etc.)
- Regional economic indicators (fuel price, unemployment, CPI)
- Store-level differences in performance  

The **goal** is to design a forecasting system that:
1. Predicts **short-term sales (12 weeks)** with high accuracy.  
2. Provides **long-term sales forecasts (96 weeks)** for strategic planning.  
3. Helps business stakeholders optimize decision-making.  

---

## 📂 Dataset
The dataset consists of **weekly Walmart store sales** along with external features:

| Column            | Description |
|-------------------|-------------|
| `Store`           | Unique store ID |
| `Date`            | Week date |
| `Weekly_Sales`    | Weekly sales figure (target variable) |
| `Holiday_Flag`    | 1 if week includes a holiday, else 0 |
| `Temperature`     | Average regional temperature |
| `Fuel_Price`      | Fuel price in region |
| `CPI`             | Consumer Price Index |
| `Unemployment`    | Regional unemployment rate |
| `lag_1, lag_2, lag_3` | Lagged weekly sales |
| `rolling_mean_4, rolling_mean_12` | Rolling averages of sales |

---

## ⚙️ Project Workflow

### **1. Data Preprocessing**
- Handled missing values.  
- Removed extreme outliers in sales.  
- Created **lag features** (sales from previous weeks).  
- Added **rolling means** for smoothing short-term noise.  
- Extracted **time-based features** (month, week, year).  

### **2. Exploratory Data Analysis (EDA)**
- Identified **seasonal spikes** during holidays.  
- Correlation of **CPI, Unemployment, and Fuel Price** with sales.  
- Store-level performance differences.  
- Visualization of historical trends.  

### **3. Feature Engineering**
- Lag and rolling window features.  
- Holiday and seasonal dummies.  
- Interactions (e.g., `Temperature × Holiday`).  
- Time-based decomposition (trend, seasonality, residual).  

### **4. Model Building**
We implemented two main approaches:

1. **Machine Learning Models**
   - Random Forest  
   - XGBoost  
   - LightGBM  
   Trained on lagged features + economic indicators. Best suited for **short-term forecasts**.  

2. **Time Series Model**
   - **Prophet** by Meta: Captures seasonality, trend, and holiday effects.  
   Best suited for **longer forecasts (96 weeks)** with interpretability.  

### **5. Forecasting**
- Short-term: Next **12 weeks** using ML rolling predictions.  
- Long-term: Next **96 weeks** using Prophet.  
- Visualized forecasts against historical sales.  

### **6. Evaluation**
Metrics used:
- **RMSE** (Root Mean Squared Error)  
- **MAE** (Mean Absolute Error)  
- **MAPE** (Mean Absolute Percentage Error)  

Visualization:
- Historical vs Forecasted sales.  
- Prophet’s **trend + seasonality decomposition**.  
- Confidence intervals for uncertainty estimation.  

### **7. Insights**
- Holiday weeks contribute to significant sales spikes.  
- Economic indicators (CPI & Unemployment) affect demand elasticity.  
- Prophet captured **yearly seasonal patterns** well.  
- Machine learning outperformed Prophet on **short horizon forecasts**.  

---

## 📊 Results
✅ Machine Learning models gave better **short-term accuracy**.  
✅ Prophet provided **interpretable long-term forecasts** with holiday effects.  
✅ The system can forecast up to **96 weeks ahead**.  

---

## 🚀 Future Work
- Add **Deep Learning models** (LSTM, GRU, Transformers).  
- Build **multi-store hierarchical forecasting**.  
- Integrate **real-time data pipeline** for live predictions.  
- Develop a **Streamlit dashboard** for visualization.  

---

## 🛠️ Tech Stack
- **Python**: pandas, numpy, scikit-learn  
- **Machine Learning**: XGBoost, Random Forest, LightGBM  
- **Time Series**: Prophet  
- **Visualization**: Matplotlib, Seaborn, Plotly  
- **Deployment (optional)**: Flask / FastAPI, Streamlit  

---

## 📌 How to Run

1. **Clone the repo**  
   ```bash
   git clone https://github.com/yourusername/walmart-forecasting.git
   cd walmart-forecasting

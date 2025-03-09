# Analyzing the trends of COVID-19 with Python

Problem Statement:

Given data about COVID-19 patients, write code to visualize the impact and analyze the trend of rate of infection and recovery as well as make predictions about the number of cases expected a week in future based on the current trends.

- Use Facebook prophet library to make time series models.

When comparing **FBProphet, ARIMA, SARIMA, and SARIMAX**, it's essential to consider factors like interpretability, flexibility, seasonality handling, external variables, and computational efficiency.

---

### **1. FBProphet (Facebook Prophet)**
**Pros:**
- Designed for business forecasting, easy to use.
- Handles missing data, outliers, and holidays well.
- Built-in seasonality (daily, weekly, yearly) and trend decomposition.
- Can include additional regressors (external variables).

**Cons:**
- Less flexible than ARIMA for custom modeling.
- Struggles with short time series.
- Can overfit if not tuned properly.

**Best For:** 
- Business forecasting with holidays.
- Data with strong seasonality and trend.
- Non-experts who need an easy-to-use forecasting tool.

---

### **2. ARIMA (AutoRegressive Integrated Moving Average)**
**Pros:**
- Strong statistical foundation.
- Good for non-seasonal time series with trends.
- Well-suited for stationary data.

**Cons:**
- Assumes linear relationships.
- Requires manual tuning of hyperparameters (p, d, q).
- Does not handle seasonality well (SARIMA is better).

**Best For:** 
- Short and medium-term forecasting.
- Stationary time series without seasonality.

---

### **3. SARIMA (Seasonal ARIMA)**
(SARIMA = ARIMA + Seasonal Component)

**Pros:**
- Handles seasonality with (P, D, Q, s) parameters.
- Captures both short-term and long-term trends.
- More accurate than ARIMA for seasonal data.

**Cons:**
- Complex to tune (requires selecting both ARIMA and seasonal parameters).
- Computationally expensive for long time series.

**Best For:** 
- Time series with strong seasonality (e.g., sales, weather, demand forecasting).

---

### **4. SARIMAX (Seasonal ARIMA with Exogenous Regressors)**
(SARIMAX = SARIMA + External Variables)

**Pros:**
- Everything from SARIMA, plus the ability to add external regressors (exogenous variables).
- More powerful and interpretable than SARIMA when external factors influence the time series.

**Cons:**
- Requires expertise in selecting and interpreting external variables.
- More complex to tune.

**Best For:** 
- Forecasting with external factors (e.g., sales affected by promotions, stock prices influenced by macroeconomic variables).

---

### **Comparison Summary**
| Feature        | FBProphet  | ARIMA | SARIMA | SARIMAX |
|--------------|-----------|-------|--------|---------|
| Seasonality  | ✅ Auto | ❌ No | ✅ Manual | ✅ Manual |
| Trend Handling | ✅ Auto | ✅ Manual | ✅ Manual | ✅ Manual |
| External Variables | ✅ Yes | ❌ No | ❌ No | ✅ Yes |
| Handling Missing Data | ✅ Yes | ❌ No | ❌ No | ❌ No |
| Interpretability | ✅ High | ✅ High | ✅ High | ✅ High |
| Ease of Use | ✅ Easy | ❌ Hard | ❌ Hard | ❌ Hard |

---

### **When to Use What?**
- **Use FBProphet** if you want quick, automatic forecasting with seasonality and external variables (business applications).
- **Use ARIMA** for simple stationary time series without seasonality.
- **Use SARIMA** for seasonal time series without external factors.
- **Use SARIMAX** when external variables significantly impact the time series.

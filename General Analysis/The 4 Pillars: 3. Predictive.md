# Pillar 3: Predictive Analytics (Foresight)
**Goal:** Use historical patterns to forecast "What is likely to happen?"

## 1. Core Objectives
*   Forecast future trends (Sales, Demand, Traffic).
*   Categorize users based on likely behavior (Churn, Fraud, Purchase).
*   Estimate specific values using statistical models.

## 2. Common Techniques
*   **Regression:** Predicting a continuous number (e.g., "What will the price be?").
*   **Classification:** Predicting a category (e.g., "Is this transaction Fraud or Legitimate?").
*   **Time-Series Forecasting:** Using models like ARIMA or Prophet for seasonal trends.

## 3. Python Implementation
```python
# Simple Linear Regression for Sales Forecasting
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LinearRegression

# Split data into training and testing sets
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

model = LinearRegression()
model.fit(X_train, y_train)

# Predict future values
predictions = model.predict(X_test)
```

## 4. Best Practices
*   **Validation:** Never test your model on the same data you used to train it.
*   **Feature Engineering:** The model is only as good as the inputs. Create meaningful variables (e.g., "Days since last purchase").
*   **Acknowledge Uncertainty:** Provide a "Confidence Interval" (e.g., "Sales will be $10k +/- 5%").

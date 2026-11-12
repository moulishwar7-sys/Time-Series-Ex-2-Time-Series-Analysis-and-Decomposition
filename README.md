# Time-Series-Ex-2-Time-Series-Analysis-and-Decomposition

# AIM:
To perform time series analysis and decomposition on the monthly average temperature of a city using Python.

We will use simple sample temperature data for 12 months and decompose it into:

Observed = Trend + Seasonal + Residual

# PROGRAM:
```
import pandas as pd
import matplotlib.pyplot as plt
from statsmodels.tsa.seasonal import seasonal_decompose

# Dataset 1: Monthly E-Commerce Sales (12 Months)
sales_data = [
 120, 115, 130, 140, 150, 160,
 155, 165, 175, 180, 210, 250
]

# Create date index for 2025
dates = pd.date_range(start="2025-01-01", periods=12, freq="ME")

# Create time series
data = pd.Series(sales_data, index=dates)
print("Monthly E-Commerce Sales ($1k):")
print(data)

# Plot original series
plt.figure(figsize=(10, 5))
plt.plot(data.index, data.values, marker="o", color="blue")
plt.title("Monthly E-Commerce Sales Analysis")
plt.xlabel("Month")
plt.ylabel("Sales ($1,000s)")
plt.grid(True)
plt.show()

# Decompose time series
result = seasonal_decompose(data, model="additive", period=12)
result.plot()
plt.show()
```
# OUTPUT:

<img width="382" height="290" alt="image" src="https://github.com/user-attachments/assets/b382cd9a-eaaf-48d1-aa60-ddec29bc1870" />

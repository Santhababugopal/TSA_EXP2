# Ex.No: 02 LINEAR AND POLYNOMIAL TREND ESTIMATION
Date:03-11-2026
### AIM:
To Implement Linear and Polynomial Trend Estiamtion Using Python.

### ALGORITHM:
Import necessary libraries (NumPy, Matplotlib)

Load the dataset

Calculate the linear trend values using least square method

Calculate the polynomial trend values using least square method

End the program
### Software required:
  1.Google colab
###  Dataset:
  1.Gold dataset
### PROGRAM:
```python

import pandas as pd
import numpy as np
import matplotlib.pyplot as plt

# Load Gold Stock Dataset
df = pd.read_excel("/content/goldstock_100_rows.xlsx")

# Convert Date
df['Date'] = pd.to_datetime(df['Date'])

# Sort by Date
df = df.sort_values('Date')

# Select Volume column
data = df['Volume'].values

# Create time variable
time = np.arange(len(data))



```
A - LINEAR TREND ESTIMATION
  ```pyhton
linear_coeff = np.polyfit(time, data, 1)
linear_trend = np.polyval(linear_coeff, time)

# Plot Linear Trend
plt.figure(figsize=(10, 5))
plt.plot(df['Date'], data, label='Actual Volume')
plt.plot(df['Date'], linear_trend,
         color='red', label='Linear Trend')

plt.title('Linear Trend Estimation - Gold Volume')
plt.xlabel('Date')
plt.ylabel('Trading Volume')
plt.legend()
plt.grid(True)
plt.show()


```
B- POLYNOMIAL TREND ESTIMATION
```python
poly_coeff = np.polyfit(time, data, 2)
poly_trend = np.polyval(poly_coeff, time)

# Plot Polynomial Trend
plt.figure(figsize=(10, 5))
plt.plot(df['Date'], data, label='Actual Volume')
plt.plot(df['Date'], poly_trend,
         color='green', label='Polynomial Trend')

plt.title('Polynomial Trend Estimation - Gold Volume')
plt.xlabel('Date')
plt.ylabel('Trading Volume')
plt.legend()
plt.grid(True)
plt.show()




```
### OUTPUT
A - LINEAR TREND ESTIMATION
<img width="1222" height="587" alt="image" src="https://github.com/user-attachments/assets/902ff1d2-03d1-47c8-b8de-aae9884ba02f" />

B- POLYNOMIAL TREND ESTIMATION

<img width="1255" height="612" alt="image" src="https://github.com/user-attachments/assets/b68b9e7c-e978-4555-8480-42d1a79d3ca0" />

### RESULT:
Thus the python program for linear and Polynomial Trend Estiamtion has been executed successfully.

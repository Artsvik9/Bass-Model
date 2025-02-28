```python
import numpy as np
import pandas as pd
import scipy.optimize as opt
import matplotlib.pyplot as plt
```


```python
data = pd.read_excel('data/smartphone_data.xlsx', sheet_name="Data")
print(data)
```

        Year   Count
    0   2009   61.49
    1   2010   81.63
    2   2011  107.20
    3   2012  138.20
    4   2013  165.80
    5   2014  190.30
    6   2015  217.30
    7   2016  241.90
    8   2017  259.50
    9   2018  274.10
    10  2019  287.80
    11  2020  296.80
    12  2021  302.00
    13  2022  307.00
    14  2023  311.80
    15  2024  316.20



```python
plt.figure(figsize=(10, 6))
plt.plot(data['Year'], data['Count'], marker='o')
plt.title('Number of smartphone users in the United States from 2009 to 2040')
plt.xlabel('Year')
plt.ylabel('Number of smartphone users')
plt.grid(True)
plt.show()
```


    
![png](Bass_Model_files/Bass_Model_2_0.png)
    



```python
def bass_model(t, p, q, M):
    "Bass diffusion model"
    return (M * (p + q) ** 2 * np.exp(-(p + q) * t)) / (p + q * np.exp(-(p + q) * t)) ** 2
```


```python
data['Year'] -= data['Year'].min()  # Normalizing years to start from 0
```


```python
params, _ = opt.curve_fit(bass_model, data['Year'], data['Count'], p0=[0.03, 0.38, 16000])
p, q, M = params
print(f"Estimated parameters are: p={p:.4f}, q={q:.4f}, M={M:.2f}")
```

    Estimated parameters are: p=0.0143, q=0.1898, M=82.21



```python
years_future = np.arange(0, 15)
predicted = bass_model(years_future, p, q, M)
```


```python
plt.figure(figsize=(10, 6))
plt.scatter(data['Year'], data['Count'], label='Observed Data', color='blue')
plt.plot(years_future, predicted, label='Bass Model Prediction', color='red')
plt.xlabel('Years starting from 2009')
plt.ylabel('Users Count')
plt.legend()
plt.title('Bass Diffusion Model Fit and Prediction')
plt.show()
```


    
![png](Bass_Model_files/Bass_Model_7_0.png)
    


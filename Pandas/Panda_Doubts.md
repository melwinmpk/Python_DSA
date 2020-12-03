```python
import pandas as pd
```

## Melwin you had a doubt in the Pandas and Numpy about the Nan in the data in calcluate the sum,mean,mode in Numpy and Pandas


```python
#getting a file from same directory WPP2019_PopulationByAgeSex_Medium.csv
import numpy as np
pop_data = np.genfromtxt('population2019.csv',usecols =1, delimiter = ',',skip_header = 1)
print("Shape before removing the Nan =>",pop_data.shape)
print(pop_data[np.isnan(pop_data)])
pop_data = pop_data[np.logical_not(np.isnan(pop_data))]  # removing the nan values
# in Numpy without removing the nan we cannot calcluate the operation 
print("Shape After removing the Nan =>",pop_data.shape)
print("SUM                =",pop_data.sum())
print("Mean               = ",np.mean(pop_data))
print("Median             = ",np.median(pop_data))
print("Standard deviation = ",np.std(pop_data))
print("Variance           = ",np.var(pop_data))

# Melwin I think while reading the file using the numpy some values is getting converted to Nan
# Because as you see in the below Pandas Code Shape is not getting Changed in the Pandas even after the dropna
```

    Shape before removing the Nan => (280932,)
    [nan nan nan ... nan nan nan]
    Shape After removing the Nan => (275175,)
    SUM                = 103658546652.572
    Mean               =  376700.4511767857
    Median             =  14171.316
    Standard deviation =  1206931.6752697264
    Variance           =  1456684068769.3882
    


```python
# in Pandas I have not removed the Nan then how is this getting Calcluated ?
df = pd.read_csv('population2019.csv')
print("Shape => ",df.shape)
df = df.dropna()
print("Shape => ",df.shape)
df["PopTotal"].describe()
```

    Shape =>  (280932, 2)
    Shape =>  (280932, 2)
    




    count    2.809320e+05
    mean     4.128536e+05
    std      1.308911e+06
    min      1.510000e-01
    25%      1.240100e+03
    50%      1.420555e+04
    75%      1.171661e+05
    max      2.163274e+07
    Name: PopTotal, dtype: float64



##  Pandas Handel the Nan Better than the Numpy


```python
# Pandas Handel the Nan Better than the Numpy
df = pd.Series({'a':1234567890, 'b':22222234, 'c':np.nan,'d':20,'e':40})
print("Shape before remove =>",df.shape)
print("Sum before remove =>",df.sum())
print("Describe before remove =\n",df.describe())
df = df.dropna()
print("Shapre after remove Nan=>",df.shape)
print("Sum after remove Nan =>",df.sum())
print("Describe before remove =\n",df.describe())
# Melwin Remember the Nan is explictely handeled in the Pandas calcluation is done excluding those rows
```

    Shape before remove => (5,)
    Sum before remove => 1256790184.0
    Describe before remove =
     count    4.000000e+00
    mean     3.141975e+08
    std      6.136696e+08
    min      2.000000e+01
    25%      3.500000e+01
    50%      1.111114e+07
    75%      3.253086e+08
    max      1.234568e+09
    dtype: float64
    Shapre after remove Nan=> (4,)
    Sum after remove Nan => 1256790184.0
    Describe before remove =
     count    4.000000e+00
    mean     3.141975e+08
    std      6.136696e+08
    min      2.000000e+01
    25%      3.500000e+01
    50%      1.111114e+07
    75%      3.253086e+08
    max      1.234568e+09
    dtype: float64
    


```python

```

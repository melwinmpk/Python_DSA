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

## What will happen tp the pvot if the data set has the duplicate entery in the data set 


```python
avo_df = pd.read_csv('datasets/avocado.csv')
avo_df.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Region</th>
      <th>Type</th>
      <th>Small Bags</th>
      <th>Large Bags</th>
      <th>Total Bags</th>
      <th>Total Volume</th>
      <th>AveragePrice</th>
      <th>Date</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>Atlanta</td>
      <td>organic</td>
      <td>89424.11</td>
      <td>207.08</td>
      <td>89631.19</td>
      <td>190257.38</td>
      <td>1.70</td>
      <td>2018-03-25</td>
    </tr>
    <tr>
      <td>1</td>
      <td>Atlanta</td>
      <td>conventional</td>
      <td>102717.50</td>
      <td>153.00</td>
      <td>102870.50</td>
      <td>202790.74</td>
      <td>1.75</td>
      <td>2018-03-18</td>
    </tr>
    <tr>
      <td>2</td>
      <td>Boston</td>
      <td>organic</td>
      <td>120465.39</td>
      <td>18.83</td>
      <td>120484.22</td>
      <td>236822.98</td>
      <td>1.58</td>
      <td>2018-03-11</td>
    </tr>
    <tr>
      <td>3</td>
      <td>Boston</td>
      <td>conventional</td>
      <td>136877.43</td>
      <td>60.60</td>
      <td>136938.03</td>
      <td>239135.67</td>
      <td>1.57</td>
      <td>2018-03-04</td>
    </tr>
    <tr>
      <td>4</td>
      <td>California</td>
      <td>organic</td>
      <td>66273.89</td>
      <td>46.58</td>
      <td>66320.47</td>
      <td>179041.72</td>
      <td>1.82</td>
      <td>2018-02-25</td>
    </tr>
  </tbody>
</table>
</div>




```python
# adding the duplicate entery
df = pd.DataFrame(avo_df[(avo_df["Region"] == "Atlanta") & (avo_df["Type"] == "organic") ])
avo_df = avo_df.append(df)
# avo_df.reset_index()
```


```python
avo_df = avo_df.reset_index()
```


```python
del avo_df['index']
```


```python
avo_df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Region</th>
      <th>Type</th>
      <th>Small Bags</th>
      <th>Large Bags</th>
      <th>Total Bags</th>
      <th>Total Volume</th>
      <th>AveragePrice</th>
      <th>Date</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>Atlanta</td>
      <td>organic</td>
      <td>89424.11</td>
      <td>207.08</td>
      <td>89631.19</td>
      <td>190257.38</td>
      <td>1.70</td>
      <td>2018-03-25</td>
    </tr>
    <tr>
      <td>1</td>
      <td>Atlanta</td>
      <td>conventional</td>
      <td>102717.50</td>
      <td>153.00</td>
      <td>102870.50</td>
      <td>202790.74</td>
      <td>1.75</td>
      <td>2018-03-18</td>
    </tr>
    <tr>
      <td>2</td>
      <td>Boston</td>
      <td>organic</td>
      <td>120465.39</td>
      <td>18.83</td>
      <td>120484.22</td>
      <td>236822.98</td>
      <td>1.58</td>
      <td>2018-03-11</td>
    </tr>
    <tr>
      <td>3</td>
      <td>Boston</td>
      <td>conventional</td>
      <td>136877.43</td>
      <td>60.60</td>
      <td>136938.03</td>
      <td>239135.67</td>
      <td>1.57</td>
      <td>2018-03-04</td>
    </tr>
    <tr>
      <td>4</td>
      <td>California</td>
      <td>organic</td>
      <td>66273.89</td>
      <td>46.58</td>
      <td>66320.47</td>
      <td>179041.72</td>
      <td>1.82</td>
      <td>2018-02-25</td>
    </tr>
    <tr>
      <td>5</td>
      <td>California</td>
      <td>conventional</td>
      <td>103033.73</td>
      <td>186.20</td>
      <td>106984.89</td>
      <td>1203274.11</td>
      <td>1.01</td>
      <td>2018-03-25</td>
    </tr>
    <tr>
      <td>6</td>
      <td>NewYork</td>
      <td>organic</td>
      <td>119694.95</td>
      <td>92.29</td>
      <td>124214.59</td>
      <td>777300.99</td>
      <td>1.38</td>
      <td>2018-03-18</td>
    </tr>
    <tr>
      <td>7</td>
      <td>NewYork</td>
      <td>conventional</td>
      <td>193813.92</td>
      <td>196.57</td>
      <td>197281.89</td>
      <td>904333.98</td>
      <td>1.29</td>
      <td>2018-03-11</td>
    </tr>
    <tr>
      <td>8</td>
      <td>SanFrancisco</td>
      <td>organic</td>
      <td>231913.11</td>
      <td>1286.43</td>
      <td>236417.93</td>
      <td>1051308.50</td>
      <td>1.16</td>
      <td>2018-03-04</td>
    </tr>
    <tr>
      <td>9</td>
      <td>SanFrancisco</td>
      <td>conventional</td>
      <td>162913.33</td>
      <td>609.20</td>
      <td>166836.16</td>
      <td>984000.13</td>
      <td>1.17</td>
      <td>2018-02-25</td>
    </tr>
    <tr>
      <td>10</td>
      <td>Atlanta</td>
      <td>organic</td>
      <td>89424.11</td>
      <td>207.08</td>
      <td>89631.19</td>
      <td>190257.38</td>
      <td>1.70</td>
      <td>2018-03-25</td>
    </tr>
  </tbody>
</table>
</div>




```python
# remember Melwin while creating the pivot the combination of index and colums should not have duplicate entery
# as you see Melwin i have added a extra entery for the  Atlanta in the 10th index which is duplicate
# in the real scenario we have to added up and then we can proceed further
avo_df.pivot(index = 'Region', columns = 'Type')
```


    ---------------------------------------------------------------------------

    ValueError                                Traceback (most recent call last)

    <ipython-input-28-05b5d8a4508b> in <module>
    ----> 1 avo_df.pivot(index = 'Region', columns = 'Type')
    

    C:\ProgramData\Anaconda3\lib\site-packages\pandas\core\frame.py in pivot(self, index, columns, values)
       5917         from pandas.core.reshape.pivot import pivot
       5918 
    -> 5919         return pivot(self, index=index, columns=columns, values=values)
       5920 
       5921     _shared_docs[
    

    C:\ProgramData\Anaconda3\lib\site-packages\pandas\core\reshape\pivot.py in pivot(data, index, columns, values)
        428         else:
        429             indexed = data._constructor_sliced(data[values].values, index=index)
    --> 430     return indexed.unstack(columns)
        431 
        432 
    

    C:\ProgramData\Anaconda3\lib\site-packages\pandas\core\frame.py in unstack(self, level, fill_value)
       6376         from pandas.core.reshape.reshape import unstack
       6377 
    -> 6378         return unstack(self, level, fill_value)
       6379 
       6380     _shared_docs[
    

    C:\ProgramData\Anaconda3\lib\site-packages\pandas\core\reshape\reshape.py in unstack(obj, level, fill_value)
        410     if isinstance(obj, DataFrame):
        411         if isinstance(obj.index, MultiIndex):
    --> 412             return _unstack_frame(obj, level, fill_value=fill_value)
        413         else:
        414             return obj.T.stack(dropna=False)
    

    C:\ProgramData\Anaconda3\lib\site-packages\pandas\core\reshape\reshape.py in _unstack_frame(obj, level, fill_value)
        431             _Unstacker, index=obj.index, level=level, fill_value=fill_value
        432         )
    --> 433         blocks = obj._data.unstack(unstacker, fill_value=fill_value)
        434         return obj._constructor(blocks)
        435     else:
    

    C:\ProgramData\Anaconda3\lib\site-packages\pandas\core\internals\managers.py in unstack(self, unstacker_func, fill_value)
       1437         """
       1438         n_rows = self.shape[-1]
    -> 1439         dummy = unstacker_func(np.empty((0, 0)), value_columns=self.items)
       1440         new_columns = dummy.get_new_columns()
       1441         new_index = dummy.get_new_index()
    

    C:\ProgramData\Anaconda3\lib\site-packages\pandas\core\reshape\reshape.py in __init__(self, values, index, level, value_columns, fill_value, constructor)
        140 
        141         self._make_sorted_values_labels()
    --> 142         self._make_selectors()
        143 
        144     def _make_sorted_values_labels(self):
    

    C:\ProgramData\Anaconda3\lib\site-packages\pandas\core\reshape\reshape.py in _make_selectors(self)
        178 
        179         if mask.sum() < len(self.index):
    --> 180             raise ValueError("Index contains duplicate entries, " "cannot reshape")
        181 
        182         self.group_index = comp_index
    

    ValueError: Index contains duplicate entries, cannot reshape



```python

```


```python

```

## How to get the Index of the Colum  based on the Condition which we give 

### Consider an example to get the index of the max value of the horsepower of the car City wise


```python
vehicle_data = pd.read_csv('datasets/cars_data.csv')
vehicle_data
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>car_name</th>
      <th>mpg</th>
      <th>cylinders</th>
      <th>displacement</th>
      <th>horsepower</th>
      <th>weight</th>
      <th>acceleration</th>
      <th>model</th>
      <th>origin_city</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>Chevrolet Chevelle Malibu</td>
      <td>18</td>
      <td>8</td>
      <td>307</td>
      <td>130</td>
      <td>3504</td>
      <td>12.0</td>
      <td>70</td>
      <td>US</td>
    </tr>
    <tr>
      <td>1</td>
      <td>Buick Skylark 320</td>
      <td>15</td>
      <td>8</td>
      <td>350</td>
      <td>165</td>
      <td>3693</td>
      <td>11.5</td>
      <td>70</td>
      <td>US</td>
    </tr>
    <tr>
      <td>2</td>
      <td>Plymouth Satellite</td>
      <td>18</td>
      <td>8</td>
      <td>318</td>
      <td>150</td>
      <td>3436</td>
      <td>11.0</td>
      <td>70</td>
      <td>US</td>
    </tr>
    <tr>
      <td>3</td>
      <td>Citroen DS-21 Pallas</td>
      <td>0</td>
      <td>4</td>
      <td>133</td>
      <td>115</td>
      <td>3090</td>
      <td>17.5</td>
      <td>70</td>
      <td>Europe</td>
    </tr>
    <tr>
      <td>4</td>
      <td>Toyota Corolla Mark ii</td>
      <td>24</td>
      <td>4</td>
      <td>113</td>
      <td>95</td>
      <td>2372</td>
      <td>15.0</td>
      <td>70</td>
      <td>Japan</td>
    </tr>
    <tr>
      <td>5</td>
      <td>Datsun PL510</td>
      <td>27</td>
      <td>4</td>
      <td>97</td>
      <td>88</td>
      <td>2130</td>
      <td>14.5</td>
      <td>70</td>
      <td>Japan</td>
    </tr>
    <tr>
      <td>6</td>
      <td>Volkswagen 1131 Deluxe Sedan</td>
      <td>26</td>
      <td>4</td>
      <td>97</td>
      <td>46</td>
      <td>1835</td>
      <td>20.5</td>
      <td>70</td>
      <td>Europe</td>
    </tr>
    <tr>
      <td>7</td>
      <td>Peugeot 504</td>
      <td>25</td>
      <td>4</td>
      <td>110</td>
      <td>87</td>
      <td>2672</td>
      <td>17.5</td>
      <td>70</td>
      <td>Europe</td>
    </tr>
    <tr>
      <td>8</td>
      <td>Audi 100 LS</td>
      <td>24</td>
      <td>4</td>
      <td>107</td>
      <td>90</td>
      <td>2430</td>
      <td>14.5</td>
      <td>70</td>
      <td>Europe</td>
    </tr>
    <tr>
      <td>9</td>
      <td>Saab 99e</td>
      <td>25</td>
      <td>4</td>
      <td>104</td>
      <td>95</td>
      <td>2375</td>
      <td>17.5</td>
      <td>70</td>
      <td>Europe</td>
    </tr>
    <tr>
      <td>10</td>
      <td>BMW 2002</td>
      <td>26</td>
      <td>4</td>
      <td>121</td>
      <td>113</td>
      <td>2234</td>
      <td>12.5</td>
      <td>70</td>
      <td>Europe</td>
    </tr>
    <tr>
      <td>11</td>
      <td>Datsun PL510</td>
      <td>27</td>
      <td>4</td>
      <td>97</td>
      <td>88</td>
      <td>2130</td>
      <td>14.5</td>
      <td>71</td>
      <td>Japan</td>
    </tr>
    <tr>
      <td>12</td>
      <td>Chevrolet Vega 2300</td>
      <td>28</td>
      <td>4</td>
      <td>140</td>
      <td>90</td>
      <td>2264</td>
      <td>15.5</td>
      <td>71</td>
      <td>US</td>
    </tr>
  </tbody>
</table>
</div>



### Method 1
Looping through get the values


```python
for x,y in dict(vehicle_data.groupby('origin_city')["horsepower"].max()).items():
    print(vehicle_data[(vehicle_data["origin_city"] == x) & (vehicle_data["horsepower"] == y)].index) 
```

    Int64Index([3], dtype='int64')
    Int64Index([4], dtype='int64')
    Int64Index([1], dtype='int64')
    

### Method 2
Second method you cannot use all the time as per me


```python
print(vehicle_data.groupby('origin_city')["horsepower"].idxmax())
```

    origin_city
    Europe    3
    Japan     4
    US        1
    Name: horsepower, dtype: int64
    

### Method 3 (Not working)
It would have been bettor if it worked


```python
vehicle_data[(vehicle_data["origin_city"] in dict(vehicle_data.groupby('origin_city')["horsepower"].max()).keys()) &
              (vehicle_data["origin_city"] in dict(vehicle_data.groupby('origin_city')["horsepower"].max()).values())  ]  
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-9-c10b2851d158> in <module>
    ----> 1 vehicle_data[(vehicle_data["origin_city"] in dict(vehicle_data.groupby('origin_city')["horsepower"].max()).keys()) &
          2               (vehicle_data["origin_city"] in dict(vehicle_data.groupby('origin_city')["horsepower"].max()).values())  ]  
    

    C:\ProgramData\Anaconda3\lib\site-packages\pandas\core\generic.py in __hash__(self)
       1884         raise TypeError(
       1885             "{0!r} objects are mutable, thus they cannot be"
    -> 1886             " hashed".format(self.__class__.__name__)
       1887         )
       1888 
    

    TypeError: 'Series' objects are mutable, thus they cannot be hashed



```python

```

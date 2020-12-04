# Pandas

<b>there are two data structure in the Pandas</b><br>
1) Series     (1d array)<br>
2) Dataframe  (2d array)


```python
import pandas as pd
```

## Series


```python
data = {'a':1234567890, 'b':22222234, 'c':[1,2,3,4,5],'d':{1:12,2:4},'e':(1,2,3)}
```


```python
pd.Series(data)
```




    a         1234567890
    b           22222234
    c    [1, 2, 3, 4, 5]
    d      {1: 12, 2: 4}
    e          (1, 2, 3)
    dtype: object




```python
river = ['Ganges', 'Yamuna', 'Missisipi', 'Neil', 'Missouri']
river_ser = pd.Series(river, index = range(25,50,5))
river_ser
```




    25       Ganges
    30       Yamuna
    35    Missisipi
    40         Neil
    45     Missouri
    dtype: object




```python
# if the Data are missing for the Indexes Pandas create the Nan for the missing value
data = {'b':100, 'a':(200, 36), 'c':10.20}
ser1 = pd.Series(data, index = ['a', 'b', 'c', 'd', 'e'])
print(ser1)
```

    a    (200, 36)
    b          100
    c         10.2
    d          NaN
    e          NaN
    dtype: object
    


```python
# But if the Index are not mentioned the the data will be excluded
data = {'b':100, 'a':(200, 36), 'c':10.20}
ser1 = pd.Series(data, index = ['a', 'b'])
print(ser1)
```

    a    (200, 36)
    b          100
    dtype: object
    


```python
#melwin Remeber in slicing of the series the end value will be considered 
data = {'b':100, 'a':(200, 36), 'c':10.20,'d':123,'e':809 }
ser1 = pd.Series(data, index = ['a', 'b', 'c', 'd', 'e'])
print(ser1)
print("-----------------------------------------")
print(ser1['a':'c']) # Remeber in slicing of the series the end value will be considered (Inclusive)
print("-----------------------------------------")
print(ser1[:3])
print("-----------------------------------------")
print(ser1[0])
print("-----------------------------------------")
ser1['a']
print("-----------------------------------------")
```

    a    (200, 36)
    b          100
    c         10.2
    d          123
    e          809
    dtype: object
    -----------------------------------------
    a    (200, 36)
    b          100
    c         10.2
    dtype: object
    -----------------------------------------
    a    (200, 36)
    b          100
    c         10.2
    dtype: object
    -----------------------------------------
    (200, 36)
    -----------------------------------------
    -----------------------------------------
    


```python
state = ['UP', 'AP', 'MP', 'KA', 'TN']
cap = ['LKO', 'AMT', 'BHP', 'BEN', 'CHN']
ser_state_cap = pd.Series(index = state, data = cap)
print(ser_state_cap)
print("----------------------------------")
print(ser_state_cap.index)
print("----------------------------------")
print(ser_state_cap.values)
print("----------------------------------")
print(ser_state_cap['UP':'TN':2])
```

    UP    LKO
    AP    AMT
    MP    BHP
    KA    BEN
    TN    CHN
    dtype: object
    ----------------------------------
    Index(['UP', 'AP', 'MP', 'KA', 'TN'], dtype='object')
    ----------------------------------
    ['LKO' 'AMT' 'BHP' 'BEN' 'CHN']
    ----------------------------------
    UP    LKO
    MP    BHP
    TN    CHN
    dtype: object
    

## Data frame


```python
state = ['UP', 'AP', 'MP', 'KA', 'TN']
state_df = pd.DataFrame(state, columns = ['State_Name'])
state_df
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
      <th>State_Name</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>UP</td>
    </tr>
    <tr>
      <th>1</th>
      <td>AP</td>
    </tr>
    <tr>
      <th>2</th>
      <td>MP</td>
    </tr>
    <tr>
      <th>3</th>
      <td>KA</td>
    </tr>
    <tr>
      <th>4</th>
      <td>TN</td>
    </tr>
  </tbody>
</table>
</div>




```python
print(state_df[0:3])
print(state_df.loc[0:3]) # for  loc the end value also be included Remember this !!!!! 
```

      State_Name
    0         UP
    1         AP
    2         MP
      State_Name
    0         UP
    1         AP
    2         MP
    3         KA
    


```python
cap = ['LKO', 'AMT', 'BHP', 'BEN', 'CHN']
cap_df = pd.DataFrame(cap, columns = ['Cap_Name'])
cap_df
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
      <th>Cap_Name</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>LKO</td>
    </tr>
    <tr>
      <th>1</th>
      <td>AMT</td>
    </tr>
    <tr>
      <th>2</th>
      <td>BHP</td>
    </tr>
    <tr>
      <th>3</th>
      <td>BEN</td>
    </tr>
    <tr>
      <th>4</th>
      <td>CHN</td>
    </tr>
  </tbody>
</table>
</div>




```python
satae_cap = list(zip(state, cap))
print(satae_cap)
stae_cap_df = pd.DataFrame(satae_cap, columns = ['State_name', 'Cap_name'])
stae_cap_df
```

    [('UP', 'LKO'), ('AP', 'AMT'), ('MP', 'BHP'), ('KA', 'BEN'), ('TN', 'CHN')]
    




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
      <th>State_name</th>
      <th>Cap_name</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>UP</td>
      <td>LKO</td>
    </tr>
    <tr>
      <th>1</th>
      <td>AP</td>
      <td>AMT</td>
    </tr>
    <tr>
      <th>2</th>
      <td>MP</td>
      <td>BHP</td>
    </tr>
    <tr>
      <th>3</th>
      <td>KA</td>
      <td>BEN</td>
    </tr>
    <tr>
      <th>4</th>
      <td>TN</td>
      <td>CHN</td>
    </tr>
  </tbody>
</table>
</div>




```python
pop_data = pd.read_csv('population2019.csv')
pop_data.head()
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
      <th>Location</th>
      <th>PopTotal</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Afghanistan</td>
      <td>7752.117</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Afghanistan</td>
      <td>7840.151</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Afghanistan</td>
      <td>7935.996</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Afghanistan</td>
      <td>8039.684</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Afghanistan</td>
      <td>8151.316</td>
    </tr>
  </tbody>
</table>
</div>




```python
print(pop_data.columns)
pop_data = pop_data.dropna()
print("----------------------------------")
pop_data['PopTotal'].max()
print("----------------------------------")
pop_data['PopTotal'].min()
print("----------------------------------")
pop_data.describe(include = 'all')
```

    Index(['Location', 'PopTotal'], dtype='object')
    ----------------------------------
    ----------------------------------
    ----------------------------------
    




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
      <th>Location</th>
      <th>PopTotal</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>280932</td>
      <td>2.809320e+05</td>
    </tr>
    <tr>
      <th>unique</th>
      <td>474</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>top</th>
      <td>Europe</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>freq</th>
      <td>1768</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>NaN</td>
      <td>4.128536e+05</td>
    </tr>
    <tr>
      <th>std</th>
      <td>NaN</td>
      <td>1.308911e+06</td>
    </tr>
    <tr>
      <th>min</th>
      <td>NaN</td>
      <td>1.510000e-01</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>NaN</td>
      <td>1.240100e+03</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>NaN</td>
      <td>1.420555e+04</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>NaN</td>
      <td>1.171661e+05</td>
    </tr>
    <tr>
      <th>max</th>
      <td>NaN</td>
      <td>2.163274e+07</td>
    </tr>
  </tbody>
</table>
</div>




```python
pop_data[5:10]
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
      <th>Location</th>
      <th>PopTotal</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>5</th>
      <td>Afghanistan</td>
      <td>8270.992</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Afghanistan</td>
      <td>8398.873</td>
    </tr>
    <tr>
      <th>7</th>
      <td>Afghanistan</td>
      <td>8535.157</td>
    </tr>
    <tr>
      <th>8</th>
      <td>Afghanistan</td>
      <td>8680.097</td>
    </tr>
    <tr>
      <th>9</th>
      <td>Afghanistan</td>
      <td>8833.947</td>
    </tr>
  </tbody>
</table>
</div>




```python
csv_dataframe = pd.read_csv("datasets/ted_data.csv")
csv_dataframe
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
      <th>name_speaker</th>
      <th>speaker_occupation</th>
      <th>title</th>
      <th>views</th>
      <th>comments</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Ken Robinson</td>
      <td>Author/educator</td>
      <td>Do schools kill creativity?</td>
      <td>47227110</td>
      <td>4553</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Al Gore</td>
      <td>Climate advocate</td>
      <td>Averting the climate crisis</td>
      <td>3200520</td>
      <td>265</td>
    </tr>
    <tr>
      <th>2</th>
      <td>David Pogue</td>
      <td>Technology columnist</td>
      <td>Simplicity sells</td>
      <td>1636292</td>
      <td>124</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Majora Carter</td>
      <td>Activist for environmental justice</td>
      <td>Greening the ghetto</td>
      <td>1697550</td>
      <td>200</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Hans Rosling</td>
      <td>Global health expert; data visionary</td>
      <td>The best stats you've ever seen</td>
      <td>12005869</td>
      <td>593</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Tony Robbins</td>
      <td>Life coach; expert in leadership psychology</td>
      <td>Why we do what we do</td>
      <td>20685401</td>
      <td>672</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Julia Sweeney</td>
      <td>Actor, comedian, playwright</td>
      <td>Letting go of God</td>
      <td>3769987</td>
      <td>919</td>
    </tr>
    <tr>
      <th>7</th>
      <td>Joshua Prince-Ramus</td>
      <td>Architect</td>
      <td>Behind the design of Seattle's library</td>
      <td>967741</td>
      <td>46</td>
    </tr>
    <tr>
      <th>8</th>
      <td>Dan Dennett</td>
      <td>Philosopher, cognitive scientist</td>
      <td>Let's teach religion -- all religion -- in sch...</td>
      <td>2567958</td>
      <td>582</td>
    </tr>
    <tr>
      <th>9</th>
      <td>Rick Warren</td>
      <td>Pastor, author</td>
      <td>A life of purpose</td>
      <td>3095993</td>
      <td>900</td>
    </tr>
  </tbody>
</table>
</div>




```python
csv_excel = pd.read_excel("datasets/football_worldcup.xlsx", 'Sheet 1')
csv_excel
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
      <th>Year</th>
      <th>Country</th>
      <th>Winner</th>
      <th>Runners-Up</th>
      <th>GoalsScored</th>
      <th>MatchesPlayed</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1990</td>
      <td>Italy</td>
      <td>Germany</td>
      <td>Argentina</td>
      <td>115</td>
      <td>52</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1994</td>
      <td>USA</td>
      <td>Brazil</td>
      <td>Italy</td>
      <td>141</td>
      <td>52</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1998</td>
      <td>France</td>
      <td>France</td>
      <td>Brazil</td>
      <td>171</td>
      <td>64</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2002</td>
      <td>Japan</td>
      <td>Brazil</td>
      <td>Germany</td>
      <td>161</td>
      <td>64</td>
    </tr>
    <tr>
      <th>4</th>
      <td>2006</td>
      <td>Germany</td>
      <td>Italy</td>
      <td>France</td>
      <td>147</td>
      <td>64</td>
    </tr>
    <tr>
      <th>5</th>
      <td>2010</td>
      <td>South Africa</td>
      <td>Spain</td>
      <td>Netherlands</td>
      <td>145</td>
      <td>64</td>
    </tr>
    <tr>
      <th>6</th>
      <td>2014</td>
      <td>Brazil</td>
      <td>Germany</td>
      <td>Argentina</td>
      <td>171</td>
      <td>64</td>
    </tr>
  </tbody>
</table>
</div>



## Creating the data frame


```python
''' Note as you see here when you are creating the DF usng the Dict and List every data must be there 
    if its not there it will throw error '''

d = {'Year':[1990, 1994,1998, 2002],
    'Country' : ['Italy', 'USA', 'France', 'Japan'],
    'Winner': ['Germany', 'Brazil', 'France', 'Brazil'],
    'Goal_Scored' : [115, 141, 171, 161]}
football_df = pd.DataFrame(d)
football_df
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
      <th>Year</th>
      <th>Country</th>
      <th>Winner</th>
      <th>Goal_Scored</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1990</td>
      <td>Italy</td>
      <td>Germany</td>
      <td>115</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1994</td>
      <td>USA</td>
      <td>Brazil</td>
      <td>141</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1998</td>
      <td>France</td>
      <td>France</td>
      <td>171</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2002</td>
      <td>Japan</td>
      <td>Brazil</td>
      <td>161</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Creating a datafrmae out of series where the no of elements in series are not same
dict_ser = {'Year': pd.Series([1990, 1994,1998], index = [0,1,2]), 
           'Country' :pd.Series(['Italy', 'USA', 'France', 'Japan'], index = [0,1,2,3])}
df_dict_ser = pd.DataFrame(dict_ser)
df_dict_ser
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
      <th>Year</th>
      <th>Country</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1990.0</td>
      <td>Italy</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1994.0</td>
      <td>USA</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1998.0</td>
      <td>France</td>
    </tr>
    <tr>
      <th>3</th>
      <td>NaN</td>
      <td>Japan</td>
    </tr>
  </tbody>
</table>
</div>




```python
list_tuples = [(1990, 'Italy', 'Germaby', 115),
              (1994, 'USA', 'Brazil', 141),
              (1998, 'France', 'France', 171),
              (2002, 'Japan', 'Brazil', 161)]
df_l_t = pd.DataFrame(list_tuples, columns = ['Year', 'Host_country', 'Winner', 'Goals_Scored'])
df_l_t
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
      <th>Year</th>
      <th>Host_country</th>
      <th>Winner</th>
      <th>Goals_Scored</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1990</td>
      <td>Italy</td>
      <td>Germaby</td>
      <td>115</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1994</td>
      <td>USA</td>
      <td>Brazil</td>
      <td>141</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1998</td>
      <td>France</td>
      <td>France</td>
      <td>171</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2002</td>
      <td>Japan</td>
      <td>Brazil</td>
      <td>161</td>
    </tr>
  </tbody>
</table>
</div>




```python
list_dict = [{'year':1990, 'Country':'Italy', 'Winner':'Germaby', 'Goal Scored':115},
              {'year':1994, 'Country':'USA', 'Winner':'Brazil', 'Goal Scored':141},
              {'year':1998, 'Country':'France', 'Winner':'France', 'Goal Scored':171},
              {'year':2002, 'Country':'Japan', 'Winner':'Brazil', 'Goal Scored':161}]
df_l_d = pd.DataFrame(list_dict)
df_l_d
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
      <th>year</th>
      <th>Country</th>
      <th>Winner</th>
      <th>Goal Scored</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1990</td>
      <td>Italy</td>
      <td>Germaby</td>
      <td>115</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1994</td>
      <td>USA</td>
      <td>Brazil</td>
      <td>141</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1998</td>
      <td>France</td>
      <td>France</td>
      <td>171</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2002</td>
      <td>Japan</td>
      <td>Brazil</td>
      <td>161</td>
    </tr>
  </tbody>
</table>
</div>



Melwin Slicing even the end value is included (Inclusive) (Only in the Series)

zip function (combining the data frame)


```python

```

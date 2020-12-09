```python
import pandas as pd
```

# Python Pandas

## Python Pandas (Data Series & Frames):

### Write a Python program to create and display a onedimensional array-like object containing an array of data using Pandas module.


```python
oneD_array = pd.Series(["May","I","Know","You"],index = ['a','b','c','d'])
oneD_array
```




    a     May
    b       I
    c    Know
    d     You
    dtype: object



### Write a Python program to convert a Panda module Series to Python list and its type


```python
oneD_array = pd.Series(["May","I","Know","You"],index = ['a','b','c','d'])
print(oneD_array)
print(oneD_array.tolist())
print(type(oneD_array.tolist()))
```

    a     May
    b       I
    c    Know
    d     You
    dtype: object
    ['May', 'I', 'Know', 'You']
    <class 'list'>
    

### Write a Python program to add, subtract, multiple and divide two Pandas Series.


```python
oneD_array1 = pd.Series([10,20,30,40],index = ['a','b','c','d'])
oneD_array2 = pd.Series([50,60,70,80],index = ['a','b','c','d'])
print("Adding of 2 Pandas Series")
print(oneD_array1+oneD_array2)
print("Subtraction of 2 Pandas Series")
print(oneD_array1-oneD_array2)
print("Multiplying of 2 Pandas Series")
print(oneD_array1*oneD_array2)
print("Dividing of 2 Pandas Series")
print(oneD_array1/oneD_array2)
```

    Adding of 2 Pandas Series
    a     60
    b     80
    c    100
    d    120
    dtype: int64
    Subtraction of 2 Pandas Series
    a   -40
    b   -40
    c   -40
    d   -40
    dtype: int64
    Multiplying of 2 Pandas Series
    a     500
    b    1200
    c    2100
    d    3200
    dtype: int64
    Dividing of 2 Pandas Series
    a    0.200000
    b    0.333333
    c    0.428571
    d    0.500000
    dtype: float64
    

### Write a Python program to compare the elements of the two Pandas Series


```python
oneD_array1 = pd.Series([10,20,80,40],index = ['a','b','c','d'])
oneD_array2 = pd.Series([50,20,70,30],index = ['a','b','c','d'])

print("Comparision of 2 Pandas Series is oneD_array1 > oneD_array2 ")
print(oneD_array1 > oneD_array2)
print("Comparision of 2 Pandas Series is oneD_array1 < oneD_array2 ")
print(oneD_array1 < oneD_array2)
print("Comparision of 2 Pandas Series is oneD_array1 == oneD_array2 ")
print(oneD_array1 == oneD_array2)

```

    Comparision of 2 Pandas Series is oneD_array1 > oneD_array2 
    a    False
    b    False
    c     True
    d     True
    dtype: bool
    Comparision of 2 Pandas Series is oneD_array1 < oneD_array2 
    a     True
    b    False
    c    False
    d    False
    dtype: bool
    Comparision of 2 Pandas Series is oneD_array1 == oneD_array2 
    a    False
    b     True
    c    False
    d    False
    dtype: bool
    

### Write a Python program to display the following data column wise.


```python
students = pd.DataFrame({'id_number' : [204, 202, 264, 136, 238],
                               'Name' : ['James Smith',
                                        'Maria Rodriguez',
                                        'David Smith', 
                                        'Patricia Garcia',
                                        'Jessica Hernandez'],
                               'Age' : [26, 22 ,24, 21, 25],
                            'Gender' : ['M', 'F', 'M', 'F', 'F'],
                    
                        })
for index,values in students.items():
    print(index)
    print(values)
```

    id_number
    0    204
    1    202
    2    264
    3    136
    4    238
    Name: id_number, dtype: int64
    Name
    0          James Smith
    1      Maria Rodriguez
    2          David Smith
    3      Patricia Garcia
    4    Jessica Hernandez
    Name: Name, dtype: object
    Age
    0    26
    1    22
    2    24
    3    21
    4    25
    Name: Age, dtype: int64
    Gender
    0    M
    1    F
    2    M
    3    F
    4    F
    Name: Gender, dtype: object
    

### Write a Python program to create and display a Data Frame from a specified dictionary data which has the index labels


```python
d = {'Manufacture_Year':[1990, 1994,1998, 2002],
    'Manufacture_Place' : ['Italy', 'USA', 'France', 'Japan'],
    'ITEM': ['BAG', 'Shoes', 'Pants', 'Shirt'],
    'COST' : [115, 141, 171, 161]}
pd.DataFrame(d)
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
      <th>Manufacture_Year</th>
      <th>Manufacture_Place</th>
      <th>ITEM</th>
      <th>COST</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>1990</td>
      <td>Italy</td>
      <td>BAG</td>
      <td>115</td>
    </tr>
    <tr>
      <td>1</td>
      <td>1994</td>
      <td>USA</td>
      <td>Shoes</td>
      <td>141</td>
    </tr>
    <tr>
      <td>2</td>
      <td>1998</td>
      <td>France</td>
      <td>Pants</td>
      <td>171</td>
    </tr>
    <tr>
      <td>3</td>
      <td>2002</td>
      <td>Japan</td>
      <td>Shirt</td>
      <td>161</td>
    </tr>
  </tbody>
</table>
</div>



### Write a Python program to select the specified columns and rows from a given Data Frame.


```python
d = {'Manufacture_Year':[1990, 1994,1998, 2002],
    'Manufacture_Place' : ['Italy', 'USA', 'France', 'Japan'],
    'ITEM': ['BAG', 'Shoes', 'Pants', 'Shirt'],
    'COST' : [115, 141, 171, 161]}
df = pd.DataFrame(d)
print(df)
df.loc[0:2,'Manufacture_Year':'ITEM']
```

       Manufacture_Year Manufacture_Place   ITEM  COST
    0              1990             Italy    BAG   115
    1              1994               USA  Shoes   141
    2              1998            France  Pants   171
    3              2002             Japan  Shirt   161
    




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
      <th>Manufacture_Year</th>
      <th>Manufacture_Place</th>
      <th>ITEM</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>1990</td>
      <td>Italy</td>
      <td>BAG</td>
    </tr>
    <tr>
      <td>1</td>
      <td>1994</td>
      <td>USA</td>
      <td>Shoes</td>
    </tr>
    <tr>
      <td>2</td>
      <td>1998</td>
      <td>France</td>
      <td>Pants</td>
    </tr>
  </tbody>
</table>
</div>



### Write a Python program to select the rows the score is between 15 and 20 (inclusive).


```python
d = {'Score':[x for x in range(100)],
    'USERS' : ['User'+str(x) for x in range(100)]}
df = pd.DataFrame(d)
print(df.head())
df[(df["Score"] >= 15) & (df["Score"] <= 20)]
```

       Score  USERS
    0      0  User0
    1      1  User1
    2      2  User2
    3      3  User3
    4      4  User4
    




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
      <th>Score</th>
      <th>USERS</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>15</td>
      <td>15</td>
      <td>User15</td>
    </tr>
    <tr>
      <td>16</td>
      <td>16</td>
      <td>User16</td>
    </tr>
    <tr>
      <td>17</td>
      <td>17</td>
      <td>User17</td>
    </tr>
    <tr>
      <td>18</td>
      <td>18</td>
      <td>User18</td>
    </tr>
    <tr>
      <td>19</td>
      <td>19</td>
      <td>User19</td>
    </tr>
    <tr>
      <td>20</td>
      <td>20</td>
      <td>User20</td>
    </tr>
  </tbody>
</table>
</div>



### Write a Python program to select the rows where number of attempts in the examination is less than 2 and score greater than 15.


```python
import random
d = {'Score':[x for x in range(100)],
    'USERS' : ['User'+str(x) for x in range(100)],
    'ATTEMPTS': [random.randint(1,10) for x in range(100)]}
df = pd.DataFrame(d)
print(df.head())
df[ (df["ATTEMPTS"] < 2) & (df["Score"] > 15)]
```

       Score  USERS  ATTEMPTS
    0      0  User0         7
    1      1  User1         1
    2      2  User2        10
    3      3  User3         9
    4      4  User4         3
    




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
      <th>Score</th>
      <th>USERS</th>
      <th>ATTEMPTS</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>20</td>
      <td>20</td>
      <td>User20</td>
      <td>1</td>
    </tr>
    <tr>
      <td>26</td>
      <td>26</td>
      <td>User26</td>
      <td>1</td>
    </tr>
    <tr>
      <td>27</td>
      <td>27</td>
      <td>User27</td>
      <td>1</td>
    </tr>
    <tr>
      <td>29</td>
      <td>29</td>
      <td>User29</td>
      <td>1</td>
    </tr>
    <tr>
      <td>38</td>
      <td>38</td>
      <td>User38</td>
      <td>1</td>
    </tr>
    <tr>
      <td>39</td>
      <td>39</td>
      <td>User39</td>
      <td>1</td>
    </tr>
    <tr>
      <td>54</td>
      <td>54</td>
      <td>User54</td>
      <td>1</td>
    </tr>
    <tr>
      <td>76</td>
      <td>76</td>
      <td>User76</td>
      <td>1</td>
    </tr>
    <tr>
      <td>77</td>
      <td>77</td>
      <td>User77</td>
      <td>1</td>
    </tr>
    <tr>
      <td>84</td>
      <td>84</td>
      <td>User84</td>
      <td>1</td>
    </tr>
    <tr>
      <td>86</td>
      <td>86</td>
      <td>User86</td>
      <td>1</td>
    </tr>
    <tr>
      <td>92</td>
      <td>92</td>
      <td>User92</td>
      <td>1</td>
    </tr>
    <tr>
      <td>94</td>
      <td>94</td>
      <td>User94</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>



### Write a Python program to append a new row 'k' to Data Frame with given values for each column. Now delete the new row and return the original data frame.


```python
d = {'Score':[random.randint(1,100) for x in range(10)],
    'USERS' : ['User'+str(x) for x in range(10)],
    'ATTEMPTS': [random.randint(1,10) for x in range(10)]}
df = pd.DataFrame(d)
print("BEFORE ADDING OF THE NEW USER")
print(df)
newrow = pd.Series([100,"TONY",1],index = ['Score','USERS','ATTEMPTS'] )
df = df.append(newrow, ignore_index=True)
print("AFTER ADDING OF THE NEW USER 'TONY' ")
print(df)
df = df.drop(df[df["USERS"] == "TONY"].index)
print("AFTER DELETE OF THE NEW USER")
print(df)

```

    BEFORE ADDING OF THE NEW USER
       Score  USERS  ATTEMPTS
    0     88  User0        10
    1     96  User1         1
    2     69  User2        10
    3     34  User3         3
    4     40  User4         3
    5     76  User5         6
    6     56  User6        10
    7     61  User7         9
    8     28  User8         3
    9     15  User9         4
    AFTER ADDING OF THE NEW USER 'TONY' 
        Score  USERS  ATTEMPTS
    0      88  User0        10
    1      96  User1         1
    2      69  User2        10
    3      34  User3         3
    4      40  User4         3
    5      76  User5         6
    6      56  User6        10
    7      61  User7         9
    8      28  User8         3
    9      15  User9         4
    10    100   TONY         1
    AFTER DELETE OF THE NEW USER
       Score  USERS  ATTEMPTS
    0     88  User0        10
    1     96  User1         1
    2     69  User2        10
    3     34  User3         3
    4     40  User4         3
    5     76  User5         6
    6     56  User6        10
    7     61  User7         9
    8     28  User8         3
    9     15  User9         4
    

### Write a Python program to sort the data frame first by 'name' in descending order, then by 'score' in ascending order.


```python
d = {'Score':[random.randint(1,100) for x in range(10)],
    'USERS' : ['User'+str(random.randint(1,10)) for x in range(10)],
    'ATTEMPTS': [random.randint(1,10) for x in range(10)]}
df = pd.DataFrame(d)
print(df)
df.sort_values(by = ['USERS','Score'])
```

       Score   USERS  ATTEMPTS
    0     89   User9         8
    1     45   User7         1
    2     88  User10        10
    3     35  User10         8
    4     96   User2         9
    5     92   User4         5
    6     23   User8         8
    7     95   User1         4
    8     19   User2         3
    9     51   User1         4
    




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
      <th>Score</th>
      <th>USERS</th>
      <th>ATTEMPTS</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>9</td>
      <td>51</td>
      <td>User1</td>
      <td>4</td>
    </tr>
    <tr>
      <td>7</td>
      <td>95</td>
      <td>User1</td>
      <td>4</td>
    </tr>
    <tr>
      <td>3</td>
      <td>35</td>
      <td>User10</td>
      <td>8</td>
    </tr>
    <tr>
      <td>2</td>
      <td>88</td>
      <td>User10</td>
      <td>10</td>
    </tr>
    <tr>
      <td>8</td>
      <td>19</td>
      <td>User2</td>
      <td>3</td>
    </tr>
    <tr>
      <td>4</td>
      <td>96</td>
      <td>User2</td>
      <td>9</td>
    </tr>
    <tr>
      <td>5</td>
      <td>92</td>
      <td>User4</td>
      <td>5</td>
    </tr>
    <tr>
      <td>1</td>
      <td>45</td>
      <td>User7</td>
      <td>1</td>
    </tr>
    <tr>
      <td>6</td>
      <td>23</td>
      <td>User8</td>
      <td>8</td>
    </tr>
    <tr>
      <td>0</td>
      <td>89</td>
      <td>User9</td>
      <td>8</td>
    </tr>
  </tbody>
</table>
</div>



### Write a Python program to insert a new column in existing Data Frame.


```python
d = {'Score':[random.randint(1,100) for x in range(10)],
    'USERS' : ['User'+str(x) for x in range(10)],
    'ATTEMPTS': [random.randint(1,10) for x in range(10)]}
df = pd.DataFrame(d)
print(df)
df["GRADE"] = "unknown"
df
```

       Score  USERS  ATTEMPTS
    0     14  User0         6
    1     12  User1         2
    2     29  User2         4
    3     58  User3         4
    4     43  User4         8
    5     58  User5         2
    6     69  User6         9
    7     37  User7         1
    8      7  User8         6
    9     74  User9         1
    




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
      <th>Score</th>
      <th>USERS</th>
      <th>ATTEMPTS</th>
      <th>GRADE</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>14</td>
      <td>User0</td>
      <td>6</td>
      <td>unknown</td>
    </tr>
    <tr>
      <td>1</td>
      <td>12</td>
      <td>User1</td>
      <td>2</td>
      <td>unknown</td>
    </tr>
    <tr>
      <td>2</td>
      <td>29</td>
      <td>User2</td>
      <td>4</td>
      <td>unknown</td>
    </tr>
    <tr>
      <td>3</td>
      <td>58</td>
      <td>User3</td>
      <td>4</td>
      <td>unknown</td>
    </tr>
    <tr>
      <td>4</td>
      <td>43</td>
      <td>User4</td>
      <td>8</td>
      <td>unknown</td>
    </tr>
    <tr>
      <td>5</td>
      <td>58</td>
      <td>User5</td>
      <td>2</td>
      <td>unknown</td>
    </tr>
    <tr>
      <td>6</td>
      <td>69</td>
      <td>User6</td>
      <td>9</td>
      <td>unknown</td>
    </tr>
    <tr>
      <td>7</td>
      <td>37</td>
      <td>User7</td>
      <td>1</td>
      <td>unknown</td>
    </tr>
    <tr>
      <td>8</td>
      <td>7</td>
      <td>User8</td>
      <td>6</td>
      <td>unknown</td>
    </tr>
    <tr>
      <td>9</td>
      <td>74</td>
      <td>User9</td>
      <td>1</td>
      <td>unknown</td>
    </tr>
  </tbody>
</table>
</div>



### Write a Python program to change the name 'James' to 'Suresh' in name column of the data frame.


```python
d = {'Score':[random.randint(1,100) for x in range(10)],
    'USERS' : ['User'+str(x) for x in range(10)],
    'ATTEMPTS': [random.randint(1,10) for x in range(10)]}
df = pd.DataFrame(d)
newrow = pd.Series([100,"James",1],index = ['Score','USERS','ATTEMPTS'] )
df = df.append(newrow, ignore_index=True)
print("Before Changing the Name")
print(df)
df.loc[df["USERS"] == "James","USERS"] = "Suresh"
print("After Changing the Name")
df
```

    Before Changing the Name
        Score  USERS  ATTEMPTS
    0      72  User0         1
    1      40  User1         6
    2      92  User2         5
    3      18  User3         7
    4      47  User4         9
    5      32  User5         5
    6      73  User6         5
    7       7  User7         3
    8       9  User8         4
    9      22  User9         3
    10    100  James         1
    After Changing the Name
    




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
      <th>Score</th>
      <th>USERS</th>
      <th>ATTEMPTS</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>72</td>
      <td>User0</td>
      <td>1</td>
    </tr>
    <tr>
      <td>1</td>
      <td>40</td>
      <td>User1</td>
      <td>6</td>
    </tr>
    <tr>
      <td>2</td>
      <td>92</td>
      <td>User2</td>
      <td>5</td>
    </tr>
    <tr>
      <td>3</td>
      <td>18</td>
      <td>User3</td>
      <td>7</td>
    </tr>
    <tr>
      <td>4</td>
      <td>47</td>
      <td>User4</td>
      <td>9</td>
    </tr>
    <tr>
      <td>5</td>
      <td>32</td>
      <td>User5</td>
      <td>5</td>
    </tr>
    <tr>
      <td>6</td>
      <td>73</td>
      <td>User6</td>
      <td>5</td>
    </tr>
    <tr>
      <td>7</td>
      <td>7</td>
      <td>User7</td>
      <td>3</td>
    </tr>
    <tr>
      <td>8</td>
      <td>9</td>
      <td>User8</td>
      <td>4</td>
    </tr>
    <tr>
      <td>9</td>
      <td>22</td>
      <td>User9</td>
      <td>3</td>
    </tr>
    <tr>
      <td>10</td>
      <td>100</td>
      <td>Suresh</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>




```python

```

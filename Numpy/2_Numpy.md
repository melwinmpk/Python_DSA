# Statistics function


```python
import numpy as np
```


```python
# this isfor the file creation
import pandas as pd
df = pd.read_csv('WPP2019_TotalPopulationBySex.csv')
df.drop('LocID', inplace=True, axis=1)
df.drop('VarID', inplace=True, axis=1)
df.drop('Variant', inplace=True, axis=1)
df.drop('Time', inplace=True, axis=1)
df.drop('MidPeriod', inplace=True, axis=1)
df.drop('PopMale', inplace=True, axis=1)
df.drop('PopFemale', inplace=True, axis=1)
df.drop('PopDensity', inplace=True, axis=1)
df.head()
df.to_csv('population2019.csv',index=False)
```

## getting data from the csv file


```python
#getting a file from same directory WPP2019_PopulationByAgeSex_Medium.csv
pop_data = np.genfromtxt('population2019.csv',usecols =1, delimiter = ',',skip_header = 1)
```


```python
pop_data
```




    array([ 7752.117,  7840.151,  7935.996, ..., 20689.956, 19892.08 ,
           19061.177])




```python
pop_data.shape
```




    (280932,)




```python
pop_data = pop_data[np.logical_not(np.isnan(pop_data))]  # removing the nan values
```


```python
pop_data.shape
```




    (275175,)




```python
pop_data.sum()
```




    103658546652.572




```python
print("Mean               = ",np.mean(pop_data))
print("Median             = ",np.median(pop_data))
print("Standard deviation = ",np.std(pop_data))
print("Variance           = ",np.var(pop_data))
```

    Mean               =  376700.4511767857
    Median             =  14171.316
    Standard deviation =  1206931.6752697264
    Variance           =  1456684068769.3882
    


```python
# count_nonezero, any, axis = 0 Colum , axis = 1 Row
```

## Accessing the array element
by using the another array


```python
arr1 = np.arange(25,30)
arr1
```




    array([25, 26, 27, 28, 29])




```python
r = np.array([2,3,0,-1])
arr1[r]
```




    array([27, 28, 25, 29])




```python
arr2 = np.arange(25,50).reshape(5,5)
arr2
```




    array([[25, 26, 27, 28, 29],
           [30, 31, 32, 33, 34],
           [35, 36, 37, 38, 39],
           [40, 41, 42, 43, 44],
           [45, 46, 47, 48, 49]])




```python
r = np.array([2,3,0,-1])
c = np.array([-1, 1, 2,0])
arr2[r,c] # i.e [(2,-1),(3,1),(0,2),(-1,0)]
```




    array([39, 41, 27, 45])




```python
fruit = np.array([["Banana","Mango","Guava","Avacado"],
            ["Papaya","Jack fruit","Plum","Strawberry"],
            ["Apricot","Apple","Blue berry","Black berry"]])
fruit
```




    array([['Banana', 'Mango', 'Guava', 'Avacado'],
           ['Papaya', 'Jack fruit', 'Plum', 'Strawberry'],
           ['Apricot', 'Apple', 'Blue berry', 'Black berry']], dtype='<U11')




```python
k = np.array([[1,2],[0,1]])
fruit[k] # consider only row
```




    array([[['Papaya', 'Jack fruit', 'Plum', 'Strawberry'],
            ['Apricot', 'Apple', 'Blue berry', 'Black berry']],
    
           [['Banana', 'Mango', 'Guava', 'Avacado'],
            ['Papaya', 'Jack fruit', 'Plum', 'Strawberry']]], dtype='<U11')




```python
v = np.array([[3,3], [2,1]])
fruit[k,v] # consider row and colum [(1,3),(2,3)],[(0,2),(1,1)]
```




    array([['Strawberry', 'Black berry'],
           ['Guava', 'Jack fruit']], dtype='<U11')



### Indexing using boolean array


```python
arr2 = np.arange(25,50).reshape(5,5)
arr2
```




    array([[25, 26, 27, 28, 29],
           [30, 31, 32, 33, 34],
           [35, 36, 37, 38, 39],
           [40, 41, 42, 43, 44],
           [45, 46, 47, 48, 49]])




```python
bool_arr = arr2>37
print(bool_arr)
arr2[bool_arr]
# or we can directly mention as
arr2[arr2>37]
```

    [[False False False False False]
     [False False False False False]
     [False False False  True  True]
     [ True  True  True  True  True]
     [ True  True  True  True  True]]
    




    array([38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49])




```python
np.any(arr2>50) # gives output as true or false
```




    False




```python
np.all(arr2>50)
```




    False



## Structured Array


```python
emp_name = ['Ross', 'Andy', 'Joe', 'Ramesh']
emp_id = [101, 102, 103, 104]
emp_sal = [10000.00, 18000.00, 20000.00,np.nan]
```


```python
emp_data = np.zeros(4, dtype = {'names':('name', 'id', 'sal'), 'formats': ('U10', 'i4', 'f8')})
emp_data
```




    array([('', 0, 0.), ('', 0, 0.), ('', 0, 0.), ('', 0, 0.)],
          dtype=[('name', '<U10'), ('id', '<i4'), ('sal', '<f8')])




```python
emp_data.dtype
```




    dtype([('name', '<U10'), ('id', '<i4'), ('sal', '<f8')])




```python
emp_data['name'] = emp_name
emp_data['id'] = emp_id
emp_data['sal'] = emp_sal
emp_data
```




    array([('Ross', 101, 10000.), ('Andy', 102, 18000.), ('Joe', 103, 20000.),
           ('Ramesh', 104,    nan)],
          dtype=[('name', '<U10'), ('id', '<i4'), ('sal', '<f8')])




```python
print(emp_data['name'])
print(emp_data['id'])
print(emp_data['sal'])
```

    ['Ross' 'Andy' 'Joe' 'Ramesh']
    [101 102 103 104]
    [10000. 18000. 20000.    nan]
    

## Array Broadcasting


```python
arr1 = np.arange(5)
print(arr1)
a = 10
arr1 + a
```

    [0 1 2 3 4]
    




    array([10, 11, 12, 13, 14])




```python
arr2 = np.arange(10).reshape(2,5)
print(arr2)
a = 10 
arr2+a
```

    [[0 1 2 3 4]
     [5 6 7 8 9]]
    




    array([[10, 11, 12, 13, 14],
           [15, 16, 17, 18, 19]])




```python
arr2 = np.arange(0,30).reshape(6,5)
print(arr2)
arr1 = np.arange(10,15).reshape(1,5)
print(arr1)
```

    [[ 0  1  2  3  4]
     [ 5  6  7  8  9]
     [10 11 12 13 14]
     [15 16 17 18 19]
     [20 21 22 23 24]
     [25 26 27 28 29]]
    [[10 11 12 13 14]]
    


```python
# Case 1

# [[ 0  1  2  3  4]  [10,11,12,13,14]
#  [ 5  6  7  8  9]  [10,11,12,13,14]
#  [10 11 12 13 14]  [10,11,12,13,14]
#  [15 16 17 18 19]  [10,11,12,13,14]
#  [20 21 22 23 24]  [10,11,12,13,14]
#  [25 26 27 28 29]] [10,11,12,13,14]


# [10,11,12,13,14]

print(arr2 + arr1) # row wise broad cast
```

    [[10 12 14 16 18]
     [15 17 19 21 23]
     [20 22 24 26 28]
     [25 27 29 31 33]
     [30 32 34 36 38]
     [35 37 39 41 43]]
    


```python
# Case 2
# [[ 0  1  2  3  4]   [10 10 10 10 10]
#  [ 5  6  7  8  9]   [11 11 11 11 11]
#  [10 11 12 13 14]   [12 12 12 12 12]
#  [15 16 17 18 19]   [13 13 13 13 13]
#  [20 21 22 23 24]   [14 14 14 14 14]
#  [25 26 27 28 29]]  [15 15 15 15 15]


# [[10],
#  [11],
#  [12],
#  [13],
#  [14],
#  [15]]
arr1 = np.arange(10,16).reshape(6,1)

print(arr2 + arr1) #colum wise broad cast
```

    [[20 21 22 23 24]
     [21 22 23 24 25]
     [22 23 24 25 26]
     [23 24 25 26 27]
     [24 25 26 27 28]
     [25 26 27 28 29]]
    


```python
# Case 3
# [[10,11,12,13,14]]

# [[10],
#  [11],
#  [12],
#  [13],
#  [14]]

# [10,11,12,13,14] [10 10 10 10 10]
# [10,11,12,13,14] [11 11 11 11 11]
# [10,11,12,13,14] [12 12 12 12 12]
# [10,11,12,13,14] [13 13 13 13 13]
# [10,11,12,13,14] [14 14 14 14 14]
arr1 = np.arange(10,15).reshape(5,1)
print(arr1)
arr2 = np.arange(10,15).reshape(1,5)
print(arr2)
arr1+arr2

```

    [[10]
     [11]
     [12]
     [13]
     [14]]
    [[10 11 12 13 14]]
    




    array([[20, 21, 22, 23, 24],
           [21, 22, 23, 24, 25],
           [22, 23, 24, 25, 26],
           [23, 24, 25, 26, 27],
           [24, 25, 26, 27, 28]])



## Iterating over an array


```python
arr1 = np.arange(5)
for ele in arr1:
    print(ele)
```

    0
    1
    2
    3
    4
    


```python
arr3 = np.arange(25).reshape(5,5)
arr3
```




    array([[ 0,  1,  2,  3,  4],
           [ 5,  6,  7,  8,  9],
           [10, 11, 12, 13, 14],
           [15, 16, 17, 18, 19],
           [20, 21, 22, 23, 24]])




```python
# Iterating over 2d array
for i in arr3:
    for j in i:
        print(j)
```

    0
    1
    2
    3
    4
    5
    6
    7
    8
    9
    10
    11
    12
    13
    14
    15
    16
    17
    18
    19
    20
    21
    22
    23
    24
    


```python
#insted of 2 loops we can use flatten operation for 2d array
for i in arr3.flatten():
    print(i)
```

    0
    1
    2
    3
    4
    5
    6
    7
    8
    9
    10
    11
    12
    13
    14
    15
    16
    17
    18
    19
    20
    21
    22
    23
    24
    


```python
arr3.flatten()
```




    array([ 0,  1,  2,  3,  4,  5,  6,  7,  8,  9, 10, 11, 12, 13, 14, 15, 16,
           17, 18, 19, 20, 21, 22, 23, 24])




```python
print(arr3)
for i in np.nditer(arr3, order ='C'): #row wise print
    print(i)
```

    [[ 0  1  2  3  4]
     [ 5  6  7  8  9]
     [10 11 12 13 14]
     [15 16 17 18 19]
     [20 21 22 23 24]]
    0
    1
    2
    3
    4
    5
    6
    7
    8
    9
    10
    11
    12
    13
    14
    15
    16
    17
    18
    19
    20
    21
    22
    23
    24
    


```python
print(arr3)
for i in np.nditer(arr3, order ='F'): # Colum wise print
    print(i)
```

    [[ 0  1  2  3  4]
     [ 5  6  7  8  9]
     [10 11 12 13 14]
     [15 16 17 18 19]
     [20 21 22 23 24]]
    0
    5
    10
    15
    20
    1
    6
    11
    16
    21
    2
    7
    12
    17
    22
    3
    8
    13
    18
    23
    4
    9
    14
    19
    24
    

## Splitting an array


```python
arr1 = np.arange(25)
arr1
```




    array([ 0,  1,  2,  3,  4,  5,  6,  7,  8,  9, 10, 11, 12, 13, 14, 15, 16,
           17, 18, 19, 20, 21, 22, 23, 24])




```python
# Splitting arr1 into 5 equal size
np.split(arr1,5)
```




    [array([0, 1, 2, 3, 4]),
     array([5, 6, 7, 8, 9]),
     array([10, 11, 12, 13, 14]),
     array([15, 16, 17, 18, 19]),
     array([20, 21, 22, 23, 24])]




```python
# Splitting an array at specified position
np.split(arr1, [3, 9, 17, 21])
```




    [array([0, 1, 2]),
     array([3, 4, 5, 6, 7, 8]),
     array([ 9, 10, 11, 12, 13, 14, 15, 16]),
     array([17, 18, 19, 20]),
     array([21, 22, 23, 24])]




```python
arr2 =  np.arange(36).reshape(6,6)
print(arr2)
#split into 2 equal parts  Remember array should have elemnts to split into 2 equal parts
np.split(arr2, 2, axis = 1)
```

    [[ 0  1  2  3  4  5]
     [ 6  7  8  9 10 11]
     [12 13 14 15 16 17]
     [18 19 20 21 22 23]
     [24 25 26 27 28 29]
     [30 31 32 33 34 35]]
    




    [array([[ 0,  1,  2],
            [ 6,  7,  8],
            [12, 13, 14],
            [18, 19, 20],
            [24, 25, 26],
            [30, 31, 32]]),
     array([[ 3,  4,  5],
            [ 9, 10, 11],
            [15, 16, 17],
            [21, 22, 23],
            [27, 28, 29],
            [33, 34, 35]])]




```python
arr2 = arr1.reshape(5,5)
print(arr2)
h1,h2, h3 = np.split(arr2, [2, 3], axis = 1) # horizontal split
print(h1)
print(h2)
print(h3)
```

    [[ 0  1  2  3  4]
     [ 5  6  7  8  9]
     [10 11 12 13 14]
     [15 16 17 18 19]
     [20 21 22 23 24]]
    [[ 0  1]
     [ 5  6]
     [10 11]
     [15 16]
     [20 21]]
    [[ 2]
     [ 7]
     [12]
     [17]
     [22]]
    [[ 3  4]
     [ 8  9]
     [13 14]
     [18 19]
     [23 24]]
    


```python
print(arr2)
h1,h2, h3 = np.split(arr2, [2, 3], axis = 0) # vertical split
print(h1)
print(h2)
print(h3)
```

    [[ 0  1  2  3  4]
     [ 5  6  7  8  9]
     [10 11 12 13 14]
     [15 16 17 18 19]
     [20 21 22 23 24]]
    [[0 1 2 3 4]
     [5 6 7 8 9]]
    [[10 11 12 13 14]]
    [[15 16 17 18 19]
     [20 21 22 23 24]]
    


```python
np.hsplit(arr2, [2,])
```




    [array([[ 0,  1],
            [ 5,  6],
            [10, 11],
            [15, 16],
            [20, 21]]),
     array([[ 2,  3,  4],
            [ 7,  8,  9],
            [12, 13, 14],
            [17, 18, 19],
            [22, 23, 24]])]




```python
np.vsplit(arr2, [2, 3])
```




    [array([[0, 1, 2, 3, 4],
            [5, 6, 7, 8, 9]]),
     array([[10, 11, 12, 13, 14]]),
     array([[15, 16, 17, 18, 19],
            [20, 21, 22, 23, 24]])]




```python

```

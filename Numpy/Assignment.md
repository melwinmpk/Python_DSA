```python
import numpy as np
```

## Write a Python program to reverse an array


```python
array1 = np.arange(10)
print(array1)
print(array1[::-1])
```

    [0 1 2 3 4 5 6 7 8 9]
    [9 8 7 6 5 4 3 2 1 0]
    

## Write a Python program to convert a list and tuple into arrays


```python
lst = [1,2,3,4,5,6,7,8,9,0]
tup = (1,2,3,4,5,6,7,8,0,9)
array1 = np.array(lst)
array2 = np.array(tup)
print(type(array1),array1)
print(type(array2),array2)
```

    <class 'numpy.ndarray'> [1 2 3 4 5 6 7 8 9 0]
    <class 'numpy.ndarray'> [1 2 3 4 5 6 7 8 0 9]
    

## Write a Python program to find common values between two arrays


```python
array1 = np.arange(1,10)
array2 = np.arange(5,15)
np.intersect1d(array1,array2)
```




    array([5, 6, 7, 8, 9])



## Write a Python program compare two arrays using numpy.


```python
array1 = np.arange(0,10)
array2 = np.arange(5,15)
array1 > array2
array1 < array2
```




    array([ True,  True,  True,  True,  True,  True,  True,  True,  True,
            True])



## Write a Python program to change the dimension of an array.


```python
print(np.arange(9).reshape(3,3))
```

    [[0 1 2]
     [3 4 5]
     [6 7 8]]
    

## Write a Python program (using numpy) to sum of all the multiples of 3 or 5 below 100.


```python
print([x for x in range(100) if (x%3 == 0 or x%5 ==0) ])
np.sum([x for x in range(100) if (x%3 == 0 or x%5 ==0) ])
```

    [0, 3, 5, 6, 9, 10, 12, 15, 18, 20, 21, 24, 25, 27, 30, 33, 35, 36, 39, 40, 42, 45, 48, 50, 51, 54, 55, 57, 60, 63, 65, 66, 69, 70, 72, 75, 78, 80, 81, 84, 85, 87, 90, 93, 95, 96, 99]
    




    2318



## Write a Python program to convert a NumPy array into Python list structure


```python
array1 = np.arange(0,10)
lst = list(array1)
print(type(lst),lst)
```

    <class 'list'> [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
    

## Write a Python program to how to add an extra column to a numpy array.


```python
array1 = np.arange(9).reshape(3,3)
print(array1)
np.append(array1,np.array([[9],[10],[11]]),axis = 1)
```

    [[0 1 2]
     [3 4 5]
     [6 7 8]]
    




    array([[ 0,  1,  2,  9],
           [ 3,  4,  5, 10],
           [ 6,  7,  8, 11]])



## Write a Python program to check whether the numpy array is empty or not.


```python
if(np.size(array1) > 0):
    print("Array Not Empty")
else:
    print("Array Empty")
```

    Array Not Empty
    

## Write a Python program to normalize a 3x3 random matrix.


```python
 '''array1 = np.random.rand(3,3)
# array1 = np.arange(9).reshape(3,3)
print(array1)
array2 = np.sum(array1,axis=0) # sum of colum
print(array2)
print("\n Normalized array =>\n ",array1/array2) # row wise broad cast'''
import numpy as np
x= np.random.random((3,3))
print("Original Array:")
print(x)
xmax, xmin = x.max(), x.min()
x = (x - xmin)/(xmax - xmin)
print("After normalization:")
print(x)        
```

    Original Array:
    [[0.04764708 0.80458726 0.99002171]
     [0.61309641 0.90170617 0.1799267 ]
     [0.24463963 0.1076622  0.36612364]]
    After normalization:
    [[0.         0.8032264  1.        ]
     [0.60002606 0.90628404 0.1403684 ]
     [0.20903847 0.06368499 0.33795112]]
    

## How to ignore all numpy warnings (not recommended)?


```python
## check the solution
```

## How to swap two rows of an array?


```python
array1 = np.arange(9).reshape(3,3)
print(array1)
array1[[0,1]] = array1[[1,0]] 
print(array1)
```

    [[0 1 2]
     [3 4 5]
     [6 7 8]]
    [[3 4 5]
     [0 1 2]
     [6 7 8]]
    

## Python program to create a random vector of size 10 and sort it.


```python
array1 = np.random.rand(10)
print(array1)
print(np.sort(array1))
```

    [0.33117748 0.83881829 0.83755442 0.47083879 0.5152626  0.80833775
     0.11615957 0.08025981 0.10555364 0.13307487]
    [0.08025981 0.10555364 0.11615957 0.13307487 0.33117748 0.47083879
     0.5152626  0.80833775 0.83755442 0.83881829]
    

## Write a Python program to check two random arrays are equal or not.


```python
array1 = np.random.rand(3,3)
array2 = np.random.rand(3,3)

if np.allclose(array1, array2):
    print("array1 and array2 are equal")
else:
    
```

## Write a Python program to get the dates of yesterday, today and tomorrow.


```python
yesterday = np.datetime64('today', 'D') - np.timedelta64(1, 'D')
print("Yestraday: ",yesterday)
today = np.datetime64('today', 'D')
print("Today: ",today)
tomorrow = np.datetime64('today', 'D') + np.timedelta64(1,
'D')
print("Tomorrow: ",tomorrow)
```

    Yestraday:  2020-12-01
    Today:  2020-12-02
    Tomorrow:  2020-12-03
    


```python

```

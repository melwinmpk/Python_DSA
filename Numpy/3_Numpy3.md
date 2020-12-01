##  Views & Copy


```python
import numpy as np
```


```python
arr1 = np.arange(25)
arr1
```




    array([ 0,  1,  2,  3,  4,  5,  6,  7,  8,  9, 10, 11, 12, 13, 14, 15, 16,
           17, 18, 19, 20, 21, 22, 23, 24])




```python
v1 = arr1[2:3]
v1
```




    array([2])




```python
# deep copy
arr1[2] = 222
print(arr1)
print(v1)
```

    [  0   1 222   3   4   5   6   7   8   9  10  11  12  13  14  15  16  17
      18  19  20  21  22  23  24]
    [222]
    


```python
# deep copy of the view
v1[0] = 555
print(arr1)
print(v1)
```

    [  0   1 555   3   4   5   6   7   8   9  10  11  12  13  14  15  16  17
      18  19  20  21  22  23  24]
    [555]
    

Melwin see the example which is mentioned below in the below scenario its not deep copy <br>
v1 = 555<br>
data type of v1 got typecasted to int <br>
To update the array position we need to mention the array position<br>



```python
v2 = arr1.view()
print(v2)
```

    [  0   1 555   3   4   5   6   7   8   9  10  11  12  13  14  15  16  17
      18  19  20  21  22  23  24]
    


```python
arr1[3] = 333
print(arr1)
print(v2)
```

    [  0   1 555 333   4   5   6   7   8   9  10  11  12  13  14  15  16  17
      18  19  20  21  22  23  24]
    [  0   1 555 333   4   5   6   7   8   9  10  11  12  13  14  15  16  17
      18  19  20  21  22  23  24]
    

## copy()


```python
arr2 = np.arange(5)
arr2
```




    array([0, 1, 2, 3, 4])




```python
a = arr2
print(a)
c = np.copy(a)
print(c)
```

    [0 1 2 3 4]
    [0 1 2 3 4]
    


```python
arr2[0] = 111
print("arr2",arr2)
print("a",a)
print("c",c)
```

    arr2 [111   1   2   3   4]
    a [111   1   2   3   4]
    c [0 1 2 3 4]
    

## Automatic Reshaping

Melwin you already know about this only one of the diamention we can mention as -1 System will reshape as per the avaliable data 

## Stacking or concatenation in an array


```python
arr1 = np.array([['UP', 'MP'],['KA', 'TN']])

arr2 = np.array([['DL', 'RJ'],['KL','AP']])

arr1.shape
arr2.shape
```




    (2, 2)




```python
np.concatenate((arr1,arr2)) # By Default row wise
```




    array([['UP', 'MP'],
           ['KA', 'TN'],
           ['DL', 'RJ'],
           ['KL', 'AP']], dtype='<U2')




```python
np.concatenate((arr1,arr2), axis = 0) # row wise axis = 0
```




    array([['UP', 'MP'],
           ['KA', 'TN'],
           ['DL', 'RJ'],
           ['KL', 'AP']], dtype='<U2')




```python
np.concatenate((arr1,arr2), axis = 1)
```




    array([['UP', 'MP', 'DL', 'RJ'],
           ['KA', 'TN', 'KL', 'AP']], dtype='<U2')




```python
np.vstack((arr1,arr2))
```




    array([['UP', 'MP'],
           ['KA', 'TN'],
           ['DL', 'RJ'],
           ['KL', 'AP']], dtype='<U2')




```python
np.hstack((arr1,arr2))
```




    array([['UP', 'MP', 'DL', 'RJ'],
           ['KA', 'TN', 'KL', 'AP']], dtype='<U2')



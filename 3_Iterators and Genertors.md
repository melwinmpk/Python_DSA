```python
import my_math
```

# Iterators and Genertors


```python
# Iterable - list, tuple, set, dictinary, string etc iterables
# Which implements __iter__ dunder/magic method
# Able to run for loop over them

# this __iter__method returns iterator object

# Iterator objet implements next() method internally, returns the next element from the iterable object
# Raise stopiterationError when all elemnts are exausted from the iterable object
```


```python
# print(dir(dict))
```

    ['__class__', '__contains__', '__delattr__', '__delitem__', '__dir__', '__doc__', '__eq__', '__format__', '__ge__', '__getattribute__', '__getitem__', '__gt__', '__hash__', '__init__', '__init_subclass__', '__iter__', '__le__', '__len__', '__lt__', '__ne__', '__new__', '__reduce__', '__reduce_ex__', '__repr__', '__setattr__', '__setitem__', '__sizeof__', '__str__', '__subclasshook__', 'clear', 'copy', 'fromkeys', 'get', 'items', 'keys', 'pop', 'popitem', 'setdefault', 'update', 'values']
    


```python
# for loop returns an iterator object
for i in 'Python':
    print(i)
```

    P
    y
    t
    h
    o
    n
    


```python
i = iter('Python')
print(next(i))
print(next(i))
print(next(i))
print(next(i))
print(next(i))
print(next(i))
print(next(i))
```

    P
    y
    t
    h
    o
    n
    


    ---------------------------------------------------------------------------

    StopIteration                             Traceback (most recent call last)

    <ipython-input-3-e1625150de09> in <module>
          6 print(next(i))
          7 print(next(i))
    ----> 8 print(next(i))
    

    StopIteration: 



```python
# create an iterator object from that iterable
iter_obj = iter('Python')

# infinite loop
while True:
    try:
        # get the next item
        element = next(iter_obj)
        print(element)
        # do something with element
    except StopIteration:
        # if StopIteration is raised, break from loop
        break
```

    P
    y
    t
    h
    o
    n
    


```python
# for i in 10,:
#     print(i)
# print(dir(int))
```

# Generator


```python
# yield keyword is used to define a function as generator

# yield retains the previous instance as a result you can access the values of the previous call
# Melwin as you see the in this example 
''' when ever the controller meets the yield it returns the value to the loop in
    In the given example value is returned to the i in the for loop '''
''' Generator handels the memory management effecientely'''
def my_gen():
    num1 = int(input('Enter First number: '))
    num2 = int(input('Enter Second number: '))
    yield num1+num2
    yield num1-num2
    yield num1*num2
    yield num1/num2
    yield num1//num2
    yield num1**num2
    yield num1%num2
print(my_gen())    
for i in my_gen():
    print(i)
```

    <generator object my_gen at 0x00000258DAE14660>
    Enter First number: 10
    Enter Second number: 20
    30
    -10
    200
    0.5
    0
    100000000000000000000
    10
    


```python
list(range(1000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000))
```


    ---------------------------------------------------------------------------

    OverflowError                             Traceback (most recent call last)

    <ipython-input-1-816a4e76645b> in <module>
    ----> 1 list(range(1000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000))
    

    OverflowError: Python int too large to convert to C ssize_t



```python
#Tuple comprehension - creates a generator object
(i for i in range(1000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000))

```




    <generator object <genexpr> at 0x00000ABA9B977190>




```python
# for i in (i for i in range(1000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000)):
#     print(i)
```


```python
def my_gen_up(end,start=0):
    if start == 0:
        for i in range(end):
            yield i
    else:
        for i in range(start, end):
            yield i
g = my_gen_up(2, 10)
for i in g:
    print(i)
```


```python

```


```python
lst1 = [(5,4),(9,1),(2,3),(5,9),(7,6),(5,5)]
lst1.sort()
```


```python
# range() is also a kind of generator
```

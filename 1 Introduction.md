# Data Structure Overview


## General Data Structures
The various data structures in computer science are divided broadly into two categories shown below.

### Liner Data Structures
These are the data structures which store the data elements in a sequential manner.<br>
<b>Array</b>: It is a sequential arrangement of data elements paired with the index of the data element.<br>
<b>Linked List</b>: Each data element contains a link to another element along with the data present in it.<br>
<b>Stack</b>: It is a data structure which follows only to specific order of operation. LIFO(last in First Out) or FILO(First in Last Out).<br>
<b>Queue</b>: It is similar to Stack but the order of operation is only FIFO(First In First Out).<br>
<b>Matrix</b>: It is two dimensional data structure in which the data element is referred by a pair of indices.<br>

### Non-Liner Data Structures
These are the data structures in which there is no sequential linking of data elements. Any pair or group of data elements can be linked to each other and can be accessed without a strict sequence.<br>
<b>Binary Tree</b>: It is a data structure where each data element can be connected to maximum two other data elements and it starts with a root node.<br>
<b>Heap</b>: It is a special case of Tree data structure where the data in the parent node is either strictly greater than/ equal to the child nodes or strictly less than it’s child nodes.<br>
<b>Hash Table</b>: It is a data structure which is made of arrays associated with each other using a hash function. It retrieves values using keys rather than index from a data element. <br>
<b>Graph</b>: .It is an arrangement of vertices and nodes where some of the nodes are connected to each other through links.
Python Specific Data Structures<br>
These data structures are specific to python language and they give greater flexibility in storing different types of data and faster processing in python environment.<br>
<b>List</b>: It is similar to array with the exception that the data elements can be of different data types. You can have both numeric and string data in a python list.<br>
<b>Tuple</b>: Tuples are similar to lists but they are immutable which means the values in a tuple cannot be modified they can only be read.<br>
<b>Dictionary</b>: The dictionary contains Key-value pairs as its data elements.
In the next chapters we are going to learn the details of how each of these data structures can be implemented using Python.

### Python - Arrays


Array is a container which can hold a fix number of items and these items should be of the same type. Most of the data structures make use of arrays to implement their algorithms. Following are the important terms to understand the concept of Array.<br>
<b>Element</b>− Each item stored in an array is called an element.<br>
<b>Index</b> − Each location of an element in an array has a numerical index, which is used to identify the element.
from array import *

arrayName = array(typecode, [Initializers])
<table>
<tr>
    <td>Typecode</td><td>Value</td>
</tr>
<tr>
    <th>b</th><th>Represents signed integer of size 1 byte</th>
</tr>
<tr>
    <th>B</th><th>Represents unsigned integer of size 1 byte</th>
</tr>
<tr>
    <th>c</th><th>Represents character of size 1 byte</th>
</tr>
<tr>
    <th>i</th><th>Represents signed integer of size 2 bytes</th>
</tr>
<tr>
    <th>I</th><th>Represents unsigned integer of size 2 bytes</th>
</tr>
<tr>
    <th>f</th><th>Represents floating point of size 4 bytes</th>
</tr>
<tr>
    <th>d</th><th>Represents floating point of size 8 bytes</th>
</tr>
</table>


```python
from array import *

array1 = array('i', [10,20,30,40,50])
print("================Print Element==================")
for x in array1:
 print(x)
print("===============Access Element==================")
print (array1[0]) # Access Array element at Index position 0

print (array1[2])
print("===============Insert Element==================")
array1.insert(1,60) # inserting element at Index position 1

for x in array1:
 print(x)

array1.remove(10) #removing element value 10
print("===============Delete Element==================")
for x in array1:
 print(x)

print("===============Search Element==================")
print (array1.index(40)) #Getting the Index of the Value

print("===============Update Element==================")
array1[2] = 80

for x in array1:
 print(x)
```

    ================Print Element==================
    10
    20
    30
    40
    50
    ===============Access Element==================
    10
    30
    ===============Insert Element==================
    10
    60
    20
    30
    40
    50
    ===============Delete Element==================
    60
    20
    30
    40
    50
    ===============Search Element==================
    3
    ===============Update Element==================
    60
    20
    80
    40
    50
    

for other types check https://www.tutorialspoint.com/python_data_structure/index.htm


```python

```

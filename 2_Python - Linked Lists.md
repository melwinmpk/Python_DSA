# Python - Linked Lists

## Creation of Linked list

A linked list is created by using the node class we studied in the last chapter. We create a Node object and create another class to use this ode object. We pass the appropriate values thorugh the node object to point the to the next data elements. The below program creates the linked list with three data elements. In the next section we will see how to traverse the linked list.


```
class Node:
    def __init__(self, dataval=None):
        self.dataval = dataval
        self.nextval = None

class SLinkedList:
    def __init__(self):
        self.headval = None
```


```
mainSlinkList = SLinkedList()
mainSlinkList.headval = Node("Mon")
list1.headval = Node("Mon")
e2 = Node("Tue")
e3 = Node("Wed")
# Link first Node to second node
list1.headval.nextval = e2

# Link second Node to third node
e2.nextval = e3

        

```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    <ipython-input-6-9e421c6e4fc6> in <module>
          1 mainSlinkList = SLinkedList()
          2 mainSlinkList.headval = Node("Mon")
    ----> 3 list1.headval = Node("Mon")
          4 e2 = Node("Tue")
          5 e3 = Node("Wed")
    

    NameError: name 'list1' is not defined


### Automated One


```
mainSlinkList = SLinkedList()
topNode = mainSlinkList
while 1:
    print("To Exit type 'Exit' ")
    Value = input("Enter your values for the Node: ") 
    if Value == "exit":
        break  
    try:
        if a1.nextval is None:
            a1.nextval = Node(Value)
    except NameError:
        a1 = Node(Value) # for the first time when the value is not defined we set the node
        topNode.headval = a1  
        
```

## Traversing a Linked List


```
class Node:
    def __init__(self, dataval=None):
        self.dataval = dataval
        self.nextval = None

class SLinkedList:
    def __init__(self):
        self.headval = None

    def listprint(self):
        printval = self.headval
        while printval is not None:
            print (printval.dataval)
            printval = printval.nextval
```


```
list = SLinkedList()
list.headval = Node("Mon")
e2 = Node("Tue")
e3 = Node("Wed")

# Link first Node to second node
list.headval.nextval = e2

# Link second Node to third node
e2.nextval = e3

list.listprint()
```

    Mon
    Tue
    Wed
    


```
mainSlinkList = SLinkedList()
topNode = mainSlinkList
while 1:
    print("To Exit type 'Exit' to display the list give input as 1 ")
    Value = input("Enter your values for the Node: ") 
    if Value == "exit":
        break 
    if Value == "1":
        topNode.listprint() 
        continue
    try:
        if a1.nextval is None:
            a = Node(Value)
            a1.nextval = a
            a1 = a
#             topNode.listprint() 
    except NameError:
        a1 = Node(Value) # for the first time when the value is not defined we set the node
        topNode.headval = a1  
topNode.listprint()        
```

    To Exit type 'Exit' to display the list give input as 1 
    Enter your values for the Node: Mon
    To Exit type 'Exit' to display the list give input as 1 
    Enter your values for the Node: tue
    To Exit type 'Exit' to display the list give input as 1 
    Enter your values for the Node: wed
    To Exit type 'Exit' to display the list give input as 1 
    Enter your values for the Node: thurs
    To Exit type 'Exit' to display the list give input as 1 
    Enter your values for the Node: exit
    Mon
    tue
    wed
    thurs
    

## Insertion and Deletion in a Linked List


```
class SLinkedList:
    def __init__(self):
        self.headval = None

# Print the linked list
    def listprint(self):
        printval = self.headval
        while printval is not None:
            print (printval.dataval)
            printval = printval.nextval
            
    def AtBegining(self,newdata):
        NewNode = Node(newdata)
        NewNode.nextval = self.headval # Update the new nodes next val to existing node
        self.headval = NewNode
        
    def AtEnd(self, newdata):
        NewNode = Node(newdata)
        if self.headval is None:
            self.headval = NewNode
            return
        laste = self.headval
        while(laste.nextval):
            laste = laste.nextval
        laste.nextval=NewNode 
        
    def Inbetween(self,middle_node,newdata):
        if middle_node is None:
            print("The mentioned node is absent")
            return

        NewNode = Node(newdata)
        NewNode.nextval = middle_node.nextval
        middle_node.nextval = NewNode

    # Function to remove node
    def RemoveNode(self, Removekey):

        HeadVal = self.head

        if (HeadVal is not None):
            if (HeadVal.data == Removekey):
                self.head = HeadVal.next
                HeadVal = None
                return

        while (HeadVal is not None):
            if HeadVal.data == Removekey:
                break
            prev = HeadVal
            HeadVal = HeadVal.next

        if (HeadVal == None):
            return

        prev.next = HeadVal.next

        HeadVal = None        
```

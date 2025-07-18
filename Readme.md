Subject:

importing math
math.radians(), math.cos(), math.sin()
math.sqrt(), math.degrees(), math.tan()
math.ceil(), 

The use of two underscores before an attribute name triggers name mangling in Python. 
This means the attributes are not directly accessible from outside the class using their given names
Example Code:
```
    __speed, __height, __angle
```

The class variable __slots__ has a special usage in Python classes. 
Declaring __slots__ and assigning it a sequence of strings restricts the creation of attributes to those included in that sequence. 
Also, it prevents the creation of the __dict__ special attribute and it allows for more efficient attribute access.

Step 8

















































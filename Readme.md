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


It's time to talk about encapsulation and getters. 
You have written the three instance attributes to be private using a leading double underscore. 
Note that these attributes are called private by convention: although they can still be accessed from outside, it is agreed upon to not do that.

Getters are what can be used to get the values from outside. 
To define a getter, you define a method that returns the value of the desired attribute and give it a @property decorator:
Example Code:
```
    class Nest:
        ...
        @property
        def number_of_eggs(self):
            return self.__number_of_eggs
```

The decorator changes the method into a property, meaning that the method is not called like a regular method, but it's used like an attribute:
Example Code:
```
    n = Nest()
    print(n.number_of_eggs)
```


Once you have the getters, you can write the setters, which allow you to set the value of an attribute in an indirect manner. 
Following the example of the last step, a setter would be written as:
Example Code:
```
    class Nest:
        ...
        @number_of_eggs.setter
        def number_of_eggs(self, new_value):
            self.__number_of_eggs = new_value
```

Same as the getter, a setter is not called like a method but used like an attribute:
Example Code:
```
    nest = Nest()
    nest.number_of_eggs = 12
```
This way of writing calls the setter and set the new value.


It's good practice to give a representation to the class by using the __repr__ special method. 
While the __str__ method returns a readable string representation that's intended to be user friendly, __repr__ is intended for programmers. 
Often __repr__ provides a string that can be used to recreate the object.


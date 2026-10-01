## Operator Overridding

```py
# there eat and exercise function overridden in the class of Crickter
class Person:
    def __init__(self,name,height,weight):
        self.name=name
        self.height=height
        self.weight=weight
    def __repr__(self):
        return f'name of the person is {self.name}'
    
    def eat(self):
        print("As Person i am eating rise and meet")
    
    def exercise(self):
        raise NotImplementedError


class Crickter(Person):
    def __init__(self,name,height,weight,team):
        self.team=team
        super().__init__(name,height,weight)
    def eat(self):
        print("As a crickter nighter eat rise and meet")

    def exercise(self):
        print("gym e gasi ame")


shakib=Crickter("Shakib",12,60,"BD")
shakib.eat()
print(shakib)
shakib.exercise()

````

## Overloading
## in there add , mul is calling dender method in python

```python
class Person:
    def __init__(self,name,height,weight):
        self.name=name
        self.height=height
        self.weight=weight
  
    

class Crickter(Person):
    def __init__(self,name,height,weight,team):
        self.team=team
        super().__init__(name,height,weight)
    
    def __add__(self, other):
       return self.height+other.height
    
    def __mul__(self,other):
        retun self.height * other.height


shakib=Crickter("Shakib",12,60,"BD")
mushi=Crickter("Mushi",2,36,"Bd")
print(shakib+mushi)
print(shakib * mushi)
```

## Static attribute, Static method ,Class method

### class method
```py
class Person:
    def __init__(self,name,age):
        self.name=name
        self.age=age
    def eat(self,item):
        self.item=item
        print("i am hungry")

        # now hug is the class method
    @classmethod 
    def hug(self,how):
        self.how
        print(" hi ")

Mehedi=Person("Mehedi",25)
Mehedi.hug()

Mehedi.eat(2)

#  in there have to provide 2 argument self must have to provide
# or have have to add decorator like add {@classmethod}
Person.eat()
```

+ if we are using Static Method (**for the decorator**) in these function we are not able to use instance any variable because of these function not maintain self parameter

## Getter & Setter

+ if we are useing (**@property**) of any function then the function is like behave of attribute
+ every setter function must have **getter attribute** 


```py
class Bank:
    def __init__(self,balance,name):
        self.name=name
        self.__balance=balance

    @property
    def balance(self):
        return self.__balance

    @balance.setter
    def balance(self,amount):
        if amount > 100:
           self.__balance += amount
        
Mehedi=Bank(125,"meheid")
Mehedi.balance=500
print(Mehedi.balance)

```

## Composition Vs Inheritence

+ Inheritence ( is a relation )
+ Composition ( has a relation )

## UML ( unified Modeling Language)

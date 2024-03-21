# Reto 3
## Restaurant Scenario
Restaurant scenario: You want to design a program to calculate the bill for a customer's order in a restaurant.
* Define a base class MenuItem: This class should have attributes like name, price, and a method to calculate the total price.
* Create subclasses for different types of menu items: Inherit from MenuItem and define properties specific to each type (e.g., Beverage, Appetizer, MainCourse).
* Define an Order class: This class should have a list of MenuItem objects and methods to add items, calculate the total bill amount, and potentially apply specific discounts based on the order composition.
```python
class MenuItem:
    def __init__(self, name, price):
        self.name = name
        self.price = price
    
    def calculate_total_price(self):
        return self.price
    
class Berevarage(MenuItem):
    def __init__(self, name, price, alcohol_content:bool):
        super().__init__(name, price)
        self.alcohol_content = alcohol_content
    
    def calculate_total_price(self):
        return self.price
    
class Appetizer(MenuItem):
    def __init__(self, name, price):
        super().__init__(name, price)
    
    def calculate_total_price(self):
        return self.price
    
class MainCourse(MenuItem):
    def __init__(self, name, price):
        super().__init__(name, price)
    
    def calculate_total_price(self):
        return self.price
    
class Salad(MenuItem):
    def __init__(self, name, price):
        super().__init__(name, price)
    
    def calculate_total_price(self):
        return self.price
    
class Dessert(MenuItem):
    def __init__(self, name, price):
        super().__init__(name, price)
    
    def calculate_total_price(self):
        return self.price
    
class Sauces(MenuItem):
    def __init__(self, name, price):
        super().__init__(name, price)
    
    def calculate_total_price(self):
        return self.price
    
class Order:
    def __init__(self):
        self.items = []
    
    def add_item(self, item):
        self.items.append(item)
    
    def calculate_total_price(self):
        total = 0
        for item in self.items:
            total += item.calculate_total_price()
        return total
    
menu_items = [
    Berevarage("Soda", 5000, False),
    Berevarage("Beer", 7000, True),
    Berevarage("Water", 3000, False),
    Appetizer("Empanadas", 3000),
    Appetizer("Nachos", 4000),
    Appetizer("Shrimp Rolls", 5000),
    MainCourse("Meat", 25000),
    MainCourse("Fish", 23000),
    MainCourse("Chicken", 20000),
    Salad("Florentina", 8000),
    Salad("Mediterrenean", 9000),
    Salad("Mexican", 10000),
    Dessert("Ice Cream", 5000),
    Dessert("Brownie", 6000),
    Dessert("Banan Split", 7000),
    Sauces("Ketchup", 1000),
    Sauces("Mayo", 1000),
    Sauces("Mustard", 1000)
]

order = Order()
order.add_item(menu_items[1])
order.add_item(menu_items[3])
order.add_item(menu_items[7])
order.add_item(menu_items[9])
order.add_item(menu_items[11])

for item in menu_items:
    order.add_item(item)

print(order.calculate_total_price())
```
Create a class diagram with all classes and their relationships. The menu should have at least 10 items. The code should follow PEP8 rules.
```mermaid
classDiagram
    Order <|-- MenuItem
    MenuItem <|-- Beverage
    MenuItem <|-- Appetizer
    MenuItem <|-- MainCourse
    MenuItem <|-- Salad
    MenuItem <|-- Dessert
    MenuItem <|-- Sauces

    Order : +List of Items
    Order : +List of Prices
    Order : +Order Items
    Order : +Calculate Total Price

    class MenuItem{
      +Names
      +Prices
    }
    class Beverage{
      +Name
      +Price
      +Alcohol_content
    }
    class Appetizer{
      +Name
      +Price
    }
    class MainCourse{
      +Name
      +Price
    }
    class Salad{
      +Name
      +Price
    }
    class Dessert{
      +Name
      +Price
    }
    class Sauces{
      +Name
      +Price
    }
```

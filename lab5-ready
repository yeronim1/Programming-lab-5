"""
importing enum and shuffle
"""
import enum
from random import shuffle

class Taste(enum.Enum):
    """
    Enumeration for taste
    """
    SWEET = 1
    SOUR = 2
    NEUTRAL = 3

class Topping(enum.Enum):
    """
    Enumeration for topping
    """
    SWEET = 1
    SOUR = 2
    NEUTRAL = 3

# pylint: disable=too-few-public-methods
class Fruit:
    """
    creating instances of class Fruit
    """
    def __init__(self, name, size, color, taste):
        self.name = name
        self.size = size
        self.color = color
        self.taste = taste

class FruitSalad:
    """
    this class creating instances of mixed salades
    """
    def __init__(self):
        self.ingredients = []
        self.topping = None

    def add_fruit(self, fruit):
        """
        this method add a fruit to our salad
        :param fruit: a fruit which we add to ingredients
        :return: None
        """
        self.ingredients.append(fruit)

    def choose_topping(self):
        """
        this method choose topping for salad
        :return: None
        """
        sweet_count = sum(1 for fruit in self.ingredients if fruit.taste == Taste.SWEET)
        sour_count = sum(1 for fruit in self.ingredients if fruit.taste == Taste.SOUR)
        neutral_count = sum(1 for fruit in self.ingredients if fruit.taste == Taste.NEUTRAL)

        if sweet_count >= sour_count and sweet_count >= neutral_count:
            self.topping = Topping.SWEET
        elif sour_count >= sweet_count and sour_count >= neutral_count:
            self.topping = Topping.SOUR
        else:
            self.topping = Topping.NEUTRAL

    def mix_ingredients(self):
        """
        this method mixing ingredients
        """
        shuffle(self.ingredients)

apple = Fruit("Apple", "Medium", "Red", Taste.SWEET)
lemon = Fruit("Lemon", "Small", "Yellow", Taste.SOUR)
banana = Fruit("Banana", "Large", "Yellow", Taste.SWEET)

salad = FruitSalad()
salad.add_fruit(apple)
salad.add_fruit(lemon)
salad.add_fruit(banana)

salad.choose_topping()
print(f"Chosen topping: {salad.topping}")

salad.mix_ingredients()
print("Mixed ingredients:")

for one_fruit in salad.ingredients:
    print(f"{one_fruit.name} ({one_fruit.taste})")

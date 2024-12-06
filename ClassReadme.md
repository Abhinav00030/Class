class Car:
# Class variable
    number_of_cars = 0

# Constructor method
    def __init__(self, make, model, year, color):
        self.make = make
        self.model = model
        self.year = year
        self.color = color
        self.speed = 0
        Car.number_of_cars += 1

# Instance method
    def accelerate(self, speed_increase):
        self.speed += speed_increase
        print(f"{self.make} {self.model} is now going {self.speed} km/h")

# Instance method
    def brake(self, speed_decrease):
        if self.speed - speed_decrease < 0:
            self.speed = 0
        else:
            self.speed -= speed_decrease
        print(f"{self.make} {self.model} has slowed down to {self.speed} km/h")

# Static method
    @staticmethod
    def honk():
        print("Beep beep!")

  # Class method
    @classmethod
    def total_cars(cls):
        return cls.number_of_cars

  # String representation of the object
    def __str__(self):
        return f"{self.year} {self.make} {self.model} ({self.color})"

# Creating instances of the Car class
car1 = Car("Toyota", "Corolla", 2020, "Blue")
car2 = Car("Tesla", "Model 3", 2021, "Red")

# Using instance methods
car1.accelerate(50)
car1.brake(20)

# Using static method
Car.honk()

# Using class method
print(f"Total number of cars: {Car.total_cars()}")

# Printing car objects
print(car1)
print(car2)

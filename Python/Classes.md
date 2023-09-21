[[Python]] classes consist of attributes (variables) and methods ([[Functions]]) that define the behavior of the objects created from them. The attributes store the data for each object, and the methods define the operations that can be performed on the object's data.

Example:
```python
class Car: # There are defined in Pascal Case

	def __init__(self, make, model): 
		self.make = make 
		self.model = model 
		
	def start_engine(self): 
		print(f"{self.make} {self.model} engine started")
```

Then with the class you can define a object, you can think of classes being the blueprint and the object the actual element that you make out of the blueprint:

```python
my_car = Car("Toyota", "Corolla")
my_car.start_engine() # output: Toyota Corolla engine started
```

You can use all the arguments available for functions to classes: [[Functions#Arguments|Arguments]]


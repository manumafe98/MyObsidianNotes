[[Python]] decorators are a way to modify the behavior of a function or class without changing its source code. They are essentially [[Functions]] that take a function as an argument and return a new function that adds some additional behavior to the original function.

Example:
```python
def my_decorator(func): 
	def wrapper(): 
		print("Before the function is called.") 
		func() 
		print("After the function is called.") 
	return wrapper 

@my_decorator 
def say_hello(): 
	print("Hello!") 

say_hello()

# Output
Before the function is called. 
Hello! 
After the function is called.
```
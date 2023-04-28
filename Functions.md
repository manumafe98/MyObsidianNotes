A [[Python]] function is a block of reusable code that performs a specific task. It is a self-contained unit of code that can be called from other parts of a program, making it easy to reuse code and avoid duplication.

You define functions like this: 
``` python 
# Creating the function
def add(x, y): # There are normally defined in snake_case
	return x + y

# Giving parameters for the arguments the function asks
add(1, 2)
```

### Arguments

- <u><b>Positional arguments</b></u>: There are the most common ones. They are passed to the function in the order they appear in the function definition.

- <u><b>Keyword arguments</b></u>: These arguments are passed to the function with a keyword and a corresponding value, allowing the arguments to be passed out of order. example:
``` python
add(y=1, x=2)
```

- <u><b>Default arguments</b></u>: These arguments have default values specified in the function definition. If a value is not provided for the default argument when the function is called, the default value is used. example:
``` python
def add(x=0, y):
	return x + y
```

- <u><b>Variable-length arguments</b></u>: These arguments allow a function to accept an arbitrary number of arguments. 
	- \*args: This allows a function to accept an arbitrary number of positional arguments.
	- \*\*kwargs: This allows a function to accept an arbitrary number of keyword arguments.
	  Example: 
	```python
	def my_function(*args, **kwargs):
		print("args", args)
		print("kwargs", kwargs)
	my_function(4, seven=7)
	# 4 would be printed as an arg
	# and 7 would be printed as a kwarg.
	```


You can also in a function specify the data type that the function is waiting the arguments to be and also the output you will get when you use it.

Example:
```python
def add(x:int, y:int) -> int:
	return x + y
```
[[Python]] docstrings are multi-line strings that are used to document Python [[Python/Functions]], methods, classes, and modules. They are enclosed in triple quotes and placed immediately after the function, method, class, or module definition.

```python
def fibonacci(n): 
	""" 
	Return the nth Fibonacci number. 

	Parameters: n (int): The index of the Fibonacci number to return. 

	Returns: 
	int: The nth Fibonacci number. 
	""" 
	if n <= 1: 
		return n 
	else: 
		return fibonacci(n-1) + fibonacci(n-2)
```

This is helpful so when you are going to declare the function you have a brief explanation of how it works.
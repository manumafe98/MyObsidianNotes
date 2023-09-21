An API, or Application Programming Interface, is a set of protocols, routines, and tools for building software applications. APIs specify how software components should interact with each other, providing a way for different applications to communicate and share data.

## RESTFUL API
Representational State Transfer is a type of API that follows a set of architectural principles or constraints for building web services. RESTful APIs use HTTP requests (GET, POST, PUT, PATCH, DELETE) to perform [[Flask SQLAlchemy#CRUD|CRUD]] operations on resources.
- <u><b>GET</b></u> : This method is used to retrieve data or resources from a server.
- <u><b>POST</b></u> : This method is used to submit data or information to a server to create a new resource.
- <u><b>PUT</b></u> : This method is used to update an existing resource on the server.
- <u><b>PATCH</b></u> : This method is used to update a specific part of an existing resource on the server.
- <u><b>DELETE</b></u> : This method is used to delete an existing resource from the server.


## Using API's with [[Python]]

We can use the requests library to send http requests to the api we specify.
Importing the module that previously we need to install with [[Pip]]:
```python
import requests
```

Normally the API's need certain metadata so when you make the request you get a response.
- <u><b>Header</b></u>: refers to the metadata that accompanies a request or response. Headers are used to provide additional information about the request or response, such as the content type, authorization credentials, or caching directives.
```python
api_endpoint = "https://example.com/v1/api"

api_header = {
	"api_id": "123adfaa4",
	"api_key": "6868fssfser4556",
}

r = requests.get(api_endpoint, headers=api_header)
```

- <u><b>Parameter</b></u>: are used to send data in an HTTP request, but they are used for different purposes.
	- json: is used to send data in JSON format in the body of an HTTP request.
	- params: is used to send data as query string parameters.
```python
# Im using random parameters, normally you can see them in the api documentation what are the required ones and the optional ones.

# ------params use case------
api_endpoint = "https://example.com/v1/api"

api_parameters = {
	"example": "hello",
	"example_in_num": 1,				  
}

r = requests.get(api_endpoint, params=api_parameters)

# ------json use case------
api_parameters = {
	"example": "hello",
	"query": "hi",			  
}

r = requests.get(api_endpoint, params=api_parameters)
```
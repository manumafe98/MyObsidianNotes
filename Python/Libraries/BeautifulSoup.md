is a [[Python]] library used for web scraping purposes to extract data from HTML and XML files. It provides a simple way to navigate, search, and modify the parse tree (the data structure representing the HTML/XML document) by wrapping the HTML/XML content in Python objects.
[Official Doc](https://beautiful-soup-4.readthedocs.io/en/latest/)

### Installation with [[Pip]]
```bash
pip install beautifulsoup4

# we somethimes could need lxml
pip install lxml
```

### Quickstart

What modules we need imported
```python
from bs4 import BeautifulSoup

# If we are going to scrape a web page
import requests
```

Make the soup
```python
website = "https://example.com"
r = requests.get(website)

soup = BeautifulSoup(r.text, "html.parser")
```
The first parameter is the html element, if we have it locally could be index.html for example, and the second one is the parser as i said before we could use lxml, html.parser, etc

### Functionalities

```python
# Finds the first element that matches that criteria
span = soup.find("span", class="example")

# If you want the text of that span
span.getText()

# Finds all the anchor tags in the html code
soup.find_all("a")

# Perform a CSS selection operation on the current element.
# Uses CSS_SELECTOR like Selenium
soup.select("li ul li h3")
```

For more functionalities consult the official Doc.
Selenium is a popular open-source library in [[Python]] used for automating web browsers. It provides a way to control and automate web browsers through a programming interface.
[Oficcial Docs](https://selenium-python.readthedocs.io/)

###  Installation with [[Pip]]
```bash
pip install selenium
```

### Quickstart

Basic modules to import:
```python
from selenium import webdriver  
from selenium.webdriver.common.by import By  
from selenium.webdriver.chrome.options import Options  
from selenium.webdriver.common.keys import Keys
```

Initiate a chrome windows to scrape:
```python
chrome_options = Options()
chrome_options.add_experimental_option("detach", True)
driver = webdriver.Chrome(options=self.chrome_options)
```

To open the proper webpage:
```python
driver.get("https://example.com")

# Interesting functionalities
driver.switch_to.new_window() # Opens a new tab
driver.maximize_window() # Maximize the window
```

### Find elements

If we use find_element it will outputs the first elemetn that matchs our criteria but if we want to find all the elements we can use find_elements.
There are multiple ways to find elements, first we have to inspect the proper webpage with F12 in the browser and check which [[HTML]] element we want to find with selenium.
We can use the following methods of the **By** module:
- <u><b>By.CLASS_NAME</b></u>: and then specify the class name of the element
	```python
	driver.find_element(By.CLASS_NAME, "class_name")
	```
- <u><b>By.XPATH</b></u>: XPath is a language used for selecting and navigating elements within an XML or HTML document. If you right click the element in the devtool you can copy the xpath or the full xpath, exmaple: <span style="color: green;">"/html/body/div/ul/li"</span>
- <u><b>By.CSS_SELECTOR</b></u>: css selector is a pattern used to select and target specific HTML elements on a web page, example: <span style="color: green;">"div ul li"</span>
- <u><b>By.NAME</b></u>
- <u><b>By.ID</b></u>
- <u><b>By.TAG_NAME</b></u>

### Actions to perform to elements

When you find the element you can asign it to a variable and perform a certain action with it, for example if the element is of the input type you can write to it
```python
password_input = driver.find_element(By.NAME, "password")
password_input.send_keys("password_example")

```

Another example if the element is a button we can click it
```python
# Also this is a special use of xpath that can check for the text of the element
continue_btn = self.driver.find_element(By.XPATH, '//span[text()="next"]')
continue_btn.click()
```

Sometimes we can use special commands with the **Keys** module.
For example if we entered the user and password in a login form instead of pressing the log in button we can send an ENTER command and get the same result.
```python
variable_example.send_keys(Keys.ENTER)
```

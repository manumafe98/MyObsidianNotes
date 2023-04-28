is a package manager for [[Python]], which allows you to easily install, manage, and uninstall Python packages and their dependencies. It is a command-line tool that interacts with the Python Package Index [PyPI](https://pypi.org/), a repository of Python packages, to download and install packages from PyPI or other indexes.

Example :
```bash
pip install requests
```

If you are installing an external library that does not come with the python package you also should import it in your code. 

Example:
```python
import requests
```

Another good feature when you are working with big projects that require lots of external packages is that you can make a <u><b>requirements.txt</b></u> file that contains all the packages that are required so you projects works correctly executing this pip command:

```bash
pip freeze > requirements.txt
```

To install the packages from requirements.txt
```bash
pip install -r requirements.txt
```
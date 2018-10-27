# Python-package upload-template 

All the code present in this repository can be used as a starting point to build one's python package.
That is, all the code present can be copied and altered to suits user needs.

The following modifications (at least) must be applied:
- Change the project name
- Change the author name
- Change the github url
- Change the author email address
- Add dependencies if needed

## Upload the package on test.pypi

```python3 setup.py sdist```
This creates a distribution archive (tar file) in the generated 'dist' folder. 
This folder can directly be installed using `pip3 install`.

Execute the following commands to upload the package to `test.pypi`
```
pip3 install twine
twine upload --repository-url https://test.pypi.org/legacy/ dist/<package_name>
```

## Download the package from test.pypi

To install locally do:
```pip3 install --extra-index-url https://test.pypi.org/pypi <package_name> ```

To install using pipenv, add a `[[source]] section` to your Pipfile as showed below:

```
[[source]]
url = "https://testpypi.python.org/pypi"
verify_ssl = true
name = "testpypi"
```

Then lock the file and install your package as would do with any others:
```
pipenv lock
pipenv install <package_name>
```


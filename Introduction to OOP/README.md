from .Gaussianddistribution import GaussianDistribution



```
python package
|
|--distributions
|   |--Gaussiandistribution.py
|   |--Generaldistribution.py
|   |--__init__.py
|--setup.py
```
```
cd python package
pip install .

import distribution
distribution.__file__ # where it install
```

### Object-Oriented Programming and Python Packages
A Python package does not need to use object-oriented programming. You could simply have a Python module with a set of functions. However, most if not all of the popular Python packages take advantage of object-oriented programming for a few reasons:



*   Object-oriented programs are relatively easy to expand especially because of inheritance
*   Object-oriented programs obscure functionality from the user. Consider scipy packages. You don't need to know how the actual code works in order to use its classes and methods.

---

### Conda 
Conda does two things: manages packages and manages environments.

```
conda create --name environmentname
source activate environmentname
conda install numpy
```

### Pip

Pip is a package manager.

```
python3 -m venv environmentname
source environmentname/bin/activate
pip install numpy
```

### PyPi
Note that pypi.org and test.pypy.org are two different websites. You'll need to register separately at each website. If you only register at pypi.org, you will not be able to upload to the test.pypy.org repository

Also, remember that your package name must be unique. If you use a package name that is already taken, you will get an error when trying to upload the package.


**Pypi.org**

1.Test PyPi
2.PyPi 

* Create Account
* cd dirpackage
* Create license.txt
* Create README.txt
* Create setup.cfg
```
[metadata]
description-file = README.md
```
* Content of setup.py
```
from setuptools import setup

setup(
    name='dsnd_probability',
    version='1.2',
    description='Gaugassian and Binomial distributions',
    packages=['dsnd_probability'],
    author='Andrew Paster',
    author_email='myemail@something.com',
    zip_safe=False
)
```

* Upload to pypi

```
cd dirpackage
python setup.py sdist
pip install twine

# commands to upload to the pypi test repository
twine upload --repository-url https://test.pypi.org/legacy/ dist/*
pip install --index-url https://test.pypi.org/simple/ dsnd-probability


# command to upload to the pypi repository
twine upload dist/*

# pip install/uninstall
pip uninstall dsnd_probability
pip install dsnd-probability
$ python
>> from dsnd_probability import Gaussian,Binomial
```

* More PyPi Resources
[Distributing Packages](https://packaging.python.org/tutorials/packaging-projects/)
[Open Source License](https://opensource.org/licenses/MIT)
```
python3 setup.py sdist bdist_wheel
```
output a folder called dist. The difference is that you will get both a .tar.gz file and a .whl file. The .tar.gz file is called a source archive whereas the .whl file is a built distribution. The .whl file is a newer type of installation file for Python packages. When you pip install a package, pip will first look for a whl file (wheel file) and if there isn't one, will then look for the tar.gz file.

A tar.gz file, ie an sdist, contains the files needed to compile and install a Python package. A whl file, ie a built distribution, only needs to be copied to the proper place for installation. Behind the scenes, pip installing a whl file has fewer steps than a tar.gz file.




```
binomial_package_files
|-setup.py
|-dsnd_probability
|  |-Binomialdistribution.py
|  |-Gaussiandistribution.py
|  |-Generaldistribution.py
|  |-README.md
|  |-__init__.py
|  |-license.txt
|  |-setup.cfg
```

```
cd 5_exercise_upload_to_pypi
python setup.py sdist
pip install twine

# commands to upload to the pypi test repository
twine upload --repository-url https://test.pypi.org/legacy/ dist/*
pip install --index-url https://test.pypi.org/simple/ distributions

# command to upload to the pypi repository
twine upload dist/*
pip install distributions
```


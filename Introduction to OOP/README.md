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



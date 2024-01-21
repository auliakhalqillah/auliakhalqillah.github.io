---
layout: post
title: "How to Write Setup File for Python Module?"
description: How to setup file for Python
tags: Python
---
![tree_setup](/img/tree_setup_file.png)

## How to Write Setup File for Python Module?
### Introduction
Setup file as known setup.py is used to install external Python modules into the Python library in the computer. The advantage of a setup file is, that we can call
the module every time without putting the module file in the same directory as the main program.

### Setup File (setup.py)
The simple `setup.py` file is written as follows

```
import setuptools
 
with open("README.md","r") as fh:
    long_description = fh.read()
 
setuptools.setup(
    name="file name of module",
    version="0.0.1",
    author="Author Name",
    author_email="Author Email",
    description="Describe about your program,shortly",
    long_description=long_description,
    long_description_content_type="text/markdown",
    url="Repository link that you have,e.g. git,github,etc",
    packages=setuptools.find_packages(),
    classifiers=[
        "Programming Language :: Python :: 3",
        "License :: OSI Approved :: MIT License",
        "Operating System :: OS Independent",
    ],
    python_requires='>=3.7',
)
```
The meaning of each variable is described as follows:

1. The name is a module name
2. The version is a module version. The version number is written in three-digit numbers (e.g., 0.0.1)
3. The author is the module owner's name (e.g., individual name or team name)
4. The author_email is the owner’s email
5. The description is the short description of the module
6. The long_description is the long description of the module that saved in the README.md file
7. URL is the repository link (e.g., git/GitHub)
8. The packages is the variable to find the package of the module
9. The classifiers are the information about the version of Python, License, Operating System, and other [information](https://pypi.org/classifiers/) that is used in the module
10. The python_requires is the requirement of the Python version to use this module

Next, we create a simple module/function to add two numbers called `myadd`. The simple module is written as follows:

```
def myadd(var1,va2):
        x = var1+var2
        return x
```

### Creating README.md file
Next, we write information to the README.md file. We can write about how to install, how to operate, and anything important to drive this module properly in the README.md file.
The `.md` extension file is for a markdown file format that can be visited [here](https://guides.github.com/features/mastering-markdown/) for more information.

```
# MAIN TITLE
Describe the main information about your module/package
# REQUIRED
Describe the what required library for support your module/package
# INSTALL
Describe how to install your module/package
# USAGE
Describe how to use your package
```
Write the code if you need
```
# MORE INFORMATION
Describe another piece of information that you want to share
```

Overall, we should organize the file structure as follows:
```
Calculate-Module                                    [Main-folder]
  test                                              [sub-folder]
    run_myadd.py                                    [file]      
  calculate                                         [sub-folder]
    __init__.py                                     [initial file]
    calculate.py                                    [module file]
  README.md                                         [file]
  setup.py                                          [file]
```

### Install the Module Using the Setup file
Go to the folder where the setup.py is, through the terminal, and type:
```
python3 setup.py install –-record installpath.txt
```
To check the module has been successfully installed, you can run the test file that you have.


# Packages

## What is a package?

For big programs, it is useful to divide up the code among several directories. These are called packages. Technically, a package is a directory containing Python files. To import a package from outside, there needs to be a file *__init__.py* (it may be empty).

## Where does Python look for modules and packages?

When importing modules or packages, their directory needs to be in the Python search path.

Python looks for modules and packages in:

* The current directory.
* The site-packages folder (where Python is installed).
* In directories in the PYTHONPATH environment variable.

You can see all directories from within Python by checking the *sys.path* variable:

    import sys
    print sys.path

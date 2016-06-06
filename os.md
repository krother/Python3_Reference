

# Working with directories

## Importing the os module

Here, we will for the first time use a function that is not readily available in Python - it needs to be imported:

    import os

`os` is the name of a module that is automatically installed with Python. It is simply not kept in memory all the time. This is why we need to import it.


## Listing files in a directory:

The function 
    
    y = os.listdir("my_folder")

gives you a list of all files in the directory `my_folder` and stores it in the variable `y`.


## Changing directories

With the os module, you can change the current directory:

    import os
    os.chdir(''..\\python'')


## Check whether a file exists

    print(os.path.exists('my_file.txt'))


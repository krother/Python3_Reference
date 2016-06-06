
# Reading text files

## Opening a file for reading

Text files can be accessed using the `open()` function. `open()` gives you a *file object* that you can use in a `for` loop. The loop processes the contents of the file line by line:

    f = open('my_file.txt')
    for line in f:
        print(line)

Alternatively, you can write both commands in one line:

    for line in open('my_file.txt'):
        print(line)


## Reading an entire file to a string variable.

You can read the entire content of a file to a single string:

    f = open('my_file.txt')
    text = f.read()


## Reading a table with multiple columns

Frequently you have data in text files separated into multiple columns, like this:

    Emily;Smith;23
    Charlie;Parker;45

This file can be read with the following simple pattern:

    for line in open('my_file.txt'):
        columns = line.strip().split(';')
        first = columns[0]
        last = columns[1]
        age = int(columns[2])


More sophisticated ways to read tabular information is offered by the Python modules `csv` and `pandas`.


## Writing file and directory names

When opening files, you often need to specify a directory name as well. You can use both full or relative directory names. A full file name contains the entire path from the root directory, e.g.:

    C:/Python3/python.exe

A relative directory name starts from the current working directory, often the directory in which your program is started:

    data/my_file.txt

or go one directory level up, then move into the folder below:

    ../data/my_file.txt

On Windows, getting directory names right is a bit cumbersome, because the directory names easily become long easily. Note that you can use forward slashed to separate between directories. If you use the backslash `\`, you need to write a double backslash `\\` (because `\` is also used for escape sequences like `\n` and `\t`).

    f = open('..\\my_file.txt')
    f = open('C:\\Python\\my_file.txt')


## Closing files

Closing files in Python is not mandatory but good practice. If you open too many files at the same time this can be a problem.

    f.close()



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

This pattern goes through a file line by line (the `for` line). It then chops off the newline character from each line (`strip`) and finally breaks the line into a list of items at the `;` character (`split`).

### The `str.strip()` function

With the string function `strip()`, you chop off whitespace characters (spaces, newline characters and tabs) from both ends of a string. The code:

    text = "  this is text   "
    s = text.strip()

produces:

    print(s)

    "this is text"

## The `str.split()` function

With the string function `split(x)`, you can divide a string into a list of strings. `x` is the character at which you want to separate the columns (by default it splits on whitespace).

    s = "this is text"
    t = s.split(" ")
    print(t)

    ["this", "is", "text"]

Both `strip()` and `split()` perfectly complement each other.

More sophisticated ways to read tabular information can be found in the Python modules `csv` and `pandas`.


## Writing file and directory names

When opening files, you often need to specify a directory name as well. You can use both full or relative directory names. A full file name contains the entire path from the root directory, e.g.:

    C:/Python3/python.exe

A relative directory name starts from the current working directory, often the directory in which your program is started:

    data/my_file.txt

or go one directory level up, then move into the folder below:

    ../data/my_file.txt

### Slashes versus Backslashes

On Windows, getting directory names right is a bit cumbersome, because the directory names easily become long easily. Note that you can use forward slashed to separate between directories. If you use the backslash `\`, you need to write a double backslash `\\` (because `\` is also used for escape sequences like `\n` and `\t`).

    f = open('..\\my_file.txt')
    f = open('C:\\Python\\my_file.txt')


## Closing files

Closing files in Python is not mandatory but good practice. If you open too many files at the same time this can be a problem.

    f.close()

## Reading files with a Context Manager

The modern way to open files in Python is using a **Context Manager** (a code block started by `with`). The `with` statement takes care of closing the file automatically:

    with open('my_file.txt') as f:
        text = f.read()

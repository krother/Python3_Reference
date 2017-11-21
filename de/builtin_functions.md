
# Builtin functions

In Python, there is a basic set of about 70 functions called **builtin functions**. Many of them are shortcuts that make your everyday programming a lot easier. Here, the 24 most important ones are given. This is your basic vocabulary, knowing these is a must to write Python efficiently!

| function | | | | 
|----------|-|-|-|
| int | float | str | list |
| bool | dict | tuple | set |
| print | input | open | range |
| len | sum | abs | round |
| min | max | sorted | reversed |
| enumerate | zip | dir | help |

See the topic **introspection** to find out about the other functions.

## Type Conversions

The **type conversion functions** convert one data type into another. Examples for them are in an earlier section:

    int(x)        str(x)        dict(x)        bool(x)
    float(x)      list(x)       tuple(x)       set(x)


## Input and output

Basic reading and writing data requires just three functions:

    print(s)       input(s)     open(filename, mode) 


## Mathematical functions

With `abs()` you can calculate the absolute value of a number:

    >>> abs(-42)
    42

With `round()` you can round numbers to a given number of digits:

    >>> round(3.14159, 2)
    3.14

The `divmod()` function calculates a division and a modulo at the same time:

    >>> divmod(23, 5)
    (4, 3)

The `pow` function does the same as the `**` operator:

    >>> pow(3, 3)
    27


## Working with sequences

There are tons of functions that help with **Python sequences** (lists, dictionaries, tuples and *iterators*). The most common ones are:

    len(x)        min(x)        sorted(x)        enumerate(x)
    sum(x)        max(x)        reversed(x)      zip(x)
    range(x)


I will explain them one by one

### Determining the length of sequences

The `len()` function returns an integer with the length of an argument. It works with strings, lists, tuples, and dictionaries.

    >>> data = [0, 1, 2, 3]
    >>> len(data)
    4

## Summing up numbers

The sum of a list of integer or float numbers can be calculated by the `sum()` function.

    >>> data = [1, 2, 3, 4]
    >>> sum(data)
    10


## Smallest and largest value

The functions `min()` and `max()` determine the smallest and largest value of a list:

    >>> data = [3, 5, 1, 7]
    >>> min(data)
    1
    >>> max(data)
    7

### Creating lists of integer numbers

The `range()` function allows to create lists of numbers on-the-fly. There are two optional parameters for the start value and the step size.

    >>> list(range(4))
    [0, 1, 2, 3]
    >>> list(range(1, 5))
    [1, 2, 3, 4]
    >>> list(range(2, 9, 2))
    [2, 4, 6, 8]
    >>> list(range(5, 0, -1))
    [5, 4, 3, 2, 1]

Note that because `range()` returns an **iterator** (a kind of lazy on-demand list), you need to convert it to a list to see the data.


### Enumerating list elements

The `enumerate()` function helps with counting elements. It creates tuples consisting of an integer number starting from zero and the elements of the list. 

    >>> fruits = ['apple', 'banana', 'orange']
    >>> list(enumerate(fruits))
    [(0, 'apple'), (1, 'banana'), (2, 'orange')]

Note that `enumerate()` produces an iterator. To obtain a list, you need to convert it.

`enumerate()` is a great shortcut to loops with counter variables:

    i = 0
    for elem in data:
        print(i, elem)
        i += 1

becomes simply:

    for i, elem in enumerate(data):
        print(i, elem)


### Sorting data

The `sorted()` function sorts a list or the keys of a dictionary, but does not change the original data.

    >>> sorted(data)
    [1, 3, 5, 7]


### Reversing data

The `reversed()` function reverses the order of list elements, but does not change the original data. It returns an iterator.

    >>> data = [3, 5, 1, 7]
    >>> list(reversed(data))
    [7, 1, 5, 3]


### Merging two lists

The `zip()` function associates the elements of two lists to a single list or tuple. Excess elements are ignored.

    fruits = ['apple','banana','orange']
    prices = [0.55, 0.75, 0.80, 1.23]
    for fruit, price in zip(fruits, prices): 
        print(fruit, price)


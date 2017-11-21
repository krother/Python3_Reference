
# Dictionaries

Dictionaries are an unordered, associative array. They have a set of key/value pairs. They are very versatile data structures, but more difficult to use than lists if you are new to Python. As the name implies, dictionaries are good for looking up things, or **searching** in general.

## Creating dictionaries

Python dictionaries are defined with winged brackets. On the left side of each entry is the **key**, on the right side the **value**:

    ratios = {
        'Alice': 0.75,
        'Bob': 0.55,
        'Charlie': 0.80
        }

## Accessing elements in dictionaries

By using square brackets and a key, you can retrieve the values from a dictionary. At least if the key is present:

    ratios['Alice']    # 0.75
    ratios['Ewing']    # KeyError!


## Retrieving values in a fail-safe way:

With the `get()` method you can assign an alternative value if the key was not found.

    ratios.get('Alice')
    ratios.get('Ewing', 'sorry not found')


## Changing values in a dictionary

The contents of a dictionary can be modified. For instance if you start with an empty dictionary:

    persons = {}

Now you can add values one key/value pair at a time:

    persons['Emily'] = 1977


## Setting values only if they dont exist yet:

    persons.setdefault('Alice', 1980)
    persons.setdefault('Emily', 1898)
    # for 'Emily', nothing happens


## Getting all keys or values:

    ratios.keys()
    ratios.values()
    ratios.items()


## Checking whether a key exists

The `in` operators checks whether a key exists in the dictionary.

    if 'Bob' in ratios:
        print('found it')

Note that you can use `in` for the same with a list as well. The dictionary is **much faster**!


## Loops over a dictionary

You can access the keys of a dictionary in a `for` loop. 

    for name in ratios:
        print(name)

However, there is no stable order unless you sort the keys explicitly:

    for name in sorted(ratios):
        print(name)    


#### What data can I use as keys?

Valid types for keys are strings, integers, floats, and tuples. You may mix keys of different type in one dictionary. However, **mutable** data types such as lists and other dictionaries are not allowed as keys.


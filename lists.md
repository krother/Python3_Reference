
# Lists

A list is a Python data type representing a sequence of elements. You can have lists of strings:

    :::python
    names = ['Hannah', 'Emily', 'Madison', 'Ashley', 'Sarah']

and also lists of numbers:

    :::python
    numbers = [25952, 23073, 19967, 17994, 17687]


## Accessing elements of lists

Using square brackets, any element of a list and tuple can be accessed. The first character has the index 0.

    :::python
    print(names[0])    
    print(numbers[3])

Negative indices start counting from the last character.

    :::python
    print(names[-1])


## Creating lists from other lists:

Lists can be sliced by applying square brackets in the same way as strings.

    :::python
    names = ['Hannah', 'Emily', 'Sarah', 'Maria']
    names[1:3]      
    names[0:2]      
    names[:3]
    names[-2:]

## Copying a list

You can use slicing to create a copy:

    :::python
    girls = names[:]

## Adding elements to a list

Add a new element to the end of the list:

    :::python
    names.append('Marilyn')


## Removing elements from a list

Remove an element at a given index:

    :::python
    names.remove(3)

Remove the last element:

    :::python
    names.pop()


## Replacing elements of a list

You can replace individual elements of a list by using an index in an assignment operation:

    :::python
    names[4] = 'Jessica'


## Sorting a list

    :::python
    names.sort()

The `itemgetter` module allows you to sort lists by a specific column.
E.g. to sort names by the 3rd  character:

    :::python
    from operator import itemgetter

    cities.sort(key=itemgetter(2))

You can give a tuple of indices to sort first by one, then the other column:

    :::python
    cities.sort(key=itemgetter((1, 0)))


## Counting elements

    :::python
    names = ['Hannah', 'Emily', 'Sarah', 'Emily', 'Maria']
    names.count('Emily')

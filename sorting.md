
# Sorting

## Sorting a list

Let us consider sorting the following data:

    cities = [
        ['Berlin', 1977],
        ['Helsinki', 1983],
        ['Warsaw', 2006],
        ['Poznan', 2008],
        ['Berlin', 2011]
    ]

There are two ways to sort a Python list. First, you can sort the values *in-place*, that means the list gets changed in the process:

    cities.sort()

Second, the `sorted()` function returns an iterator without modifying the initial list:

    for city, year in sorted(cities):
        print(city, year)

## Sorting by a specific column

Generally, the **pandas** library is the better choice for sorting by specific columns.
If you don't want to use any libraries, you can sort by the second column (index 1) with the `itemgetter` module:

    from operator import itemgetter

    column = 1
    cities.sort(key=itemgetter(column))

    for row in interfaces:
        print(row)

## Sorting by two columns:

When we give a tuple of indices, we can sort first by one, then the other column:

    cities.sort(key=itemgetter((1, 0)))

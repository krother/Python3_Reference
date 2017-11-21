
# Short functions and lambda functions

A Python function does not have to be long to be useful. Many functions are one-liners.
For instance, we can define functions identifying odd and even values:

    def odd(x): return x % 2
    def even(x): return not odd(x)

When we want to filter a list of numbers, the function makes our code more readable:

    # create 100 random numbers
    from random import randint
    numbers = [randint(1, 100) for x in range(100)]

    # filter
    e = [x for x in numbers if even(x)]
    o = [x for x in numbers if odd(x)]

## Lambda functions

A different way to express the same are anonymous or **lambda functions**. These are essentially throwaway functions. Their use is discouraged in most situations, because they impede code readability.

    odd = lambda x: x % 2
    even = lambda x:not odd(x)

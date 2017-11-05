
# Decorators

In general, **decorators are functions that manipulate functions**. 
More specifically, a decorator wraps a function to manage a function call.

Imagine you have the following Python function:

    def addition(a, b):
        do_something_before()
        result = a + b
        do_something_after()
        return result


The same can be written as a Python decorator:

    def deco(func):
        def wrapper(*args):
            do_something_before()
            result = func(*args)
            do_something_after()
            return result
    return wrapper

    @deco
    def addition(a, b):
        return a + b

You can argue that this does not simplify the code in the first place. Using decorators pays off in bigger programs, when they are used often, or imported from different modules.


## The functools Module

The `functools` module contains a couple of ways to manipulate functions.

The **`wraps`** decorator copies documentation strings, so that the decorated function looks like the original one. It is useful when writing your own decorators

    import functools

    def deco(func):
        @functools.wraps(func) 
        def wrapper(*args):
            ...


The `lru_cache` decorator caches results, so that the second call with the same parameters is faster. It is useful when your function is fully deterministic.

    @functools.lru_cache(maxsize=128, typed=False) 

The `partial` fills in a part of the parameters, resulting in a new function:

    add5 = functools.partial(addition, 5)
    print(add5(8))  # results in 13


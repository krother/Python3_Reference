
# Generators

Generators are *"lazy functions"*. They produce results like normal Python functions, but only when they are needed. The main purpose of using generators is to save memory and calculation time when processing big datasets.

A Python generator is indicated by the `yield` keyword. You cannot have `yield` and `return` in the same function. An example:

    def count():
        i = 0
        print('checkpoint A')
        while i < 20:
            yield i
            i += 1

    gen = count()
    print('checkpoint B')
    print(next(gen))
    print(next(gen))

The first call of the generator does nothing yet. Only when `next()` requests the next value, the generator function is executed until the `yield` statement. Then it pauses until the next `yield` and so on.

You can use generators in a `for` loop:

    for x in gen:
         print(x,)


## Iterators

The thing returned by a generator is called an **iterator**. Many functions in Python 3 return iterators (e.g. `range()`, `enumerate()`, `zip()`). 

Among the things you can do to iterators are:

* request values with `next`.
* use them in a `for` loop.
* convert them to lists with `list()`.



# Type conversions

## Converting numbers to strings

If you have an integer or float number `i`, you can make a string out of it with `str(i)`:

    text = str(2000)

Alternatively, you can use a format string:

    text = "{}".format(2000)"

Format strings pay off very quickly when converting floats:

    text = "{:4.2f}".format(3.14159)


## Converting strings to numbers

If you have a string `s`, you can make an integer out of it with `int(s)`:

    number = int("2000")

The same works for a float:

    number = float("3.14159")


## Other type conversions

The functions `int()`, `float()` and `str()` change the type of the given data. They are therefore called **type conversions**. There is a *conversion functions* for each Python data type. Try the following:

    int('5.5')
    float(5)
    str(5.5)
    list("ABC")
    tuple([1, 2, 3])
    dict([('A', 1), ('B', 2)])
    set([1, 2, 2, 3])



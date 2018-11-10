
# String formatting

Variables and strings can be combined, using formatting characters. This works also within a print statement. In both cases, the number of values and formatting characters must be equal. Here are some examples:

    print('Hello {}%!'.format('Roger'))
    print('Result: {4i}'.format(42))
    print('{1:5s} {1:>5s}'.format('one', 'two'))
    print('{2} {1}'.format('one', 'two'))
    a = 5.099999
    b = 2.333333
    print('{:6.3f}/{:6.3f}'.format(a, b))

The winged brackets are placeholders for the parameters in the `format` function. They may contain special instructions for formatting, consisting of two parts `{a:b}`. Part `a`. Both parts are optional. Options include:

* `{:xd}` – an integer with x digits.
* `{:<xd}` – a left-formatted integer with x digits.
* `{x}` – the x-th parameter.
* `{:>5s}` – a right-aligned string of width 5.
* `{:6.2f}` – a float number with 6 digits (2 after the dot).

### Remark

There are two other modes for string formatting:

* strings using a `%` sign - the oldschool way
* format strings that only exist since Python 3.6

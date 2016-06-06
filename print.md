
# Writing to the Screen

The command `print()` Writes textual output to the screen. It accepts one or more arguments in parentheses - all things that will be printed. You can print both strings and integer numbers. You can also provide variables as arguments to `print()`.

We need print because typing a variable name in a Python program does not give you any visible output.

The Python print statement is very versatile and accepts many combinations of strings, numbers, function calls, and arithmetic operations separated by commas.

### Examples for print statements: 

    print('Hello World')
    print(3 + 4)
    print(3.4)
    print("""Text that 
    stretches over 
    multiple lines.
    """)
    print('number', 77)
    print()
    a = "7"
    print(a * 7)
    print(int(a) * 7)
    print("Hello", end=" ")
    print("World")

### String formatting

Variables and strings can be combined, using formatting characters. This works also within a print statement. In both cases, the number of values and formatting characters must be equal. Here are some examples:

    print('Hello {}%!'.format('Roger'))
    print('Result: {4}'.format(42))
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

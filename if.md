

# Conditional statements with `if`

The `if` statement is used to implement decisions and branching in a program. One or more instructions are only executed if a condition matches:

    :::python
    if name == 'Emily':
        studies = 'Physics'

There must be an `if` block, zero or more `elif`'s and an optional `else` block:

    :::python
    if name == 'Emily':
        studies = 'Physics'
    elif name == 'Maria':
        studies = 'Computer Science'
    elif name == 'Sarah':
        studies = 'Archaeology'
    else:
        studies = '-- not registered yet --'


## Code blocks

After an `if` statement, all indented commands are treated as a code block, and are executed in the context of the condition.

The next unindented command is executed in any case.


## Comparison operators

An `if` expression may contain comparison operators like:

    :::python
    a == b
    a != b
    a < b
    a > b
    a <= b
    a >= b

On lists and strings you can also use:

    :::python
    a in b

Multiple expressions can be combined with boolean logic (`and`, `or`, `not`):

    :::python
    a or b
    a and b
    not a
    (a or b) and not (c or d)


## Boolean value of variables

Each variable can be interpreted as a boolean (`True`/`False`) value. All values are treated as `True`, except for:

    :::python
    False
    0
    []
    ''
    {}
    set()
    None


# Collection Types

Python oofers 

## namedtuple

Namedtuples are helpful to group together items with names.

    from collections import namedtuple

    City = namedtuple('City', ('name', 'country'))

    berlin = City('Berlin', 'Germany')

    print(berlin.name)
    print(berlin.country)

Which is much easier to read than `berlin[0]` of a normal tuple.

Namedtuples become more useful if you have a lot of them:

    cities = [
        City('Berlin', 'Germany'),
        City('Warsaw', 'Poland'),
        City('Poznan', 'Poland')
    ]
Namedtuples are a cheap replacement for classes.


## Counter

The `Counter` is a special dictionary for counting things.

    from collections import Counter

    # generate 100 random names
    names = ["Adam", "Bea", "Charlie", "Danielle", "Eve", "Frantz", "Gustav", "Helena"]
    from random import choice
    data = [choice(names) for i in range(100)]

You create a `Counter` by giving it an iterable:

    c = Counter(data)

The most important new method is `most_common`. The rest works like a normal dictionary.

    print(c)
    print(c.most_common(3))
    print(c.get('Adam'))


## OrderedDict

OrderedDict is a special kind of dictionary that preserves the insertion order.

    from collections import OrderedDict

    od = OrderedDict()

    names = ["Adam", "Bea", "Charlie", "Danielle", "Eve", "Frantz", "Gustav", "Helena"]
    for i, name in enumerate(names):
         od[i] = name

With an OrderedDict, you have a guarantee that the output of the following command is always the same (which you don't have with a normal dictionary):

    print(od)

You have an additional method for changing the order:

    od.move_to_end(2)
    print(od)

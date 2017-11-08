
# Typumwandlungen

## Zahlen in Strings umwandeln

Eine Integer- oder Fließkommazahl `i` kannst Du mit `str(i)` in einen String umwandeln:

    text = str(2000)

Ein Formatstring erledigt das gleiche:

    text = "{}".format(2000)"

Floats lassen sich mit Formatstrings schnell und elegant auf eine bestimmte Anzahl Stellen formatieren:

    text = "{:4.2f}".format(3.14159)


## Strings in Zahlen umwandeln

Einen String `s` kannst Du mit `int(s)` in einen Integer umwandeln - falls er eine Zahl enthält:

    number = int("2000")

Das Gleiche funktioniert mit Floats:

    number = float("3.14159")


## Andere Typumwandlungen

Es gibt für jeden grundlegenden Datentyp eine Funktion zur Typumwandlung:

| Funktion | Beschreibung |
|----------|--------------|
| `str()`  | wandelt alles in einen String um |
| `int()` | Float oder String zu Integer |
| `float()` | Integer oder String zu Float |
| `list()` | Aufzählbarer Typ zu Liste |
| `tuple()` | Aufzählbarer Typ zu Tupel |
| `dict()` | Aufzählbare Wertpaare zu Dictionary |
| `set()` | Aufzählbarer Typ zu Set |
| `bool()` | allles in `True` oder `False` |

Probiere folgende Typumwandlungen aus:

    list("ABC")
    tuple([1, 2, 3])
    dict([('A', 1), ('B', 2)])
    set([1, 2, 2, 3])

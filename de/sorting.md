
# Sortieren

## Sortieren einer Liste

Betrachten wir das Sortieren der folgenden Daten:

    cities = [
        ['Berlin', 1977],
        ['Helsinki', 1983],
        ['Warsaw', 2006],
        ['Poznan', 2008],
        ['Berlin', 2011]
    ]

Es gibt zwei Möglichkeiten, eine Liste in Python zu sortieren. Erstens, kannst Du die Liste *verändern*:

    cities.sort()

Zweitens, liefert die Funktion `sorted()` einen Iterator, wobei die ursprüngliche Liste nicht verändert wird:

    for city, year in sorted(cities):
        print(city, year)


## Nach einer Spalte sortieren

Du kannst mit dem Modul `itemgetter` nach der zweiten Spalte (Index 1) sortieren:

    from operator import itemgetter

    column = 1
    cities.sort(key=itemgetter(column))

    for row in interfaces:
        print(row)

## Nach zwei Spalten sortieren
 
Mit einem Tupel aus mehreren Indizes kannst Du zuerst nach der ersten, dann nach der zweiten Spalte sortieren:

    cities.sort(key=itemgetter((1, 0)))

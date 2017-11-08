
# Tupel

Ein Tupel ist eine nicht modifizierbare Folge von Elementen. Sie sind oft nützlich, um Daten unterschiedlichen Typs zu gruppieren.

    person = ('Emily', 'Smith', 23)

Im Gegensatz zu Listen, lassen sich Tupel als Schlüssel eines Dictionary verwenden.


## Tupel indizieren

Elemente von Tupeln lassen sich genauso wie Listen indizieren:

   person[0]
   person[-2]
   person[1:]


## Über Tupel iterieren

Auch die `for`-Schleife funktioniert mit einem Tupel:

    for elem in person:
        print(elem)


## Tupel verpacken und entpacken

Eine Aufzählung mehrerer Elemente lässt sich unmittelbar einem Tupel zuweisen:

    person = 'Emily', 'Smith', 23


Umgekehrt lassen sich Tupel in mehrere Variablen entpacken:

    erster, zweiter, alter = person


Es ist sogar möglich, die Werte von Variablen auf diese Weise zu vertauschen:

    erster, zweiter = zweiter, erster


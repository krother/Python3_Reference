
# Stringformatierung

Variablen und Strings lassen sich mit Platzhaltern in einen String einsetzen. Dabei muss es genauso viele Platzhalter wie eingesetzte Werte geben. Dies geht auch innerhalb einer `print`-Anweisung:

    print('Hello {}%!'.format('Roger'))
    print('Result: {4i}'.format(42))
    print('{1:5s} {1:>5s}'.format('one', 'two'))
    print('{2} {1}'.format('one', 'two'))
    a = 5.099999
    b = 2.333333
    print('{:6.3f}/{:6.3f}'.format(a, b))

Die geschweiften Klammern `{}` sind die Platzhalter für die hinten angegebenen Parameter in der Funktion `format`. Die Platzhalter können die Art der Formatierung genauer beschreiben. Ein Platzhalter besteht aus zwei Teilen `{x:y}`. Dabei steht `x` für den x-ten Parameter. Für `y` sind u.a. folgende Werte möglich:

* `{:yd}` – ein Integer mit y Ziffern.
* `{:<yd}` – ein linksbündig formatierter Integer mit y Ziffern.
* `{:>5s}` – ein rechtsbündig formatierter String der Länge 5.
* `{:6.2f}` – eine Kommazahl mit 6 Stellen (3 vor dem Komma, 1 für das Komma selbst, 2 Nachkommastellen).

### Anmerkung

Es gibt drei andere Möglichkeiten Strings zu formatieren:

* Das Umwandeln mit `str()` und Verbinden mit `+` ist recht unflexibel
* Strings mit einem nachgestellten `%`-Zeichen - dies ist die altertümliche Methode
* Spezielle *format strings* gibt es erst seit Python 3.6

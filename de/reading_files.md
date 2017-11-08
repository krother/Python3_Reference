
# Lesen von Textdateien

## Eine Datei zum Lesen öffnen

Textdateien lassen sich mit der Funktion `open()` öffnen. `open()` liefert ein *Dateiobjekt*, das sich in einer `for`-Schleife verwenden lässt. Die Schleife geht den Inhalt der Datei Zeile für Zeile durch:

    f = open('meine_datei.txt')
    for zeile in f:
        print(zeile)

Beide Befehle lassen sich in eine Zeile schreiben:

    for zeile in open('meine_datei.txt'):
        print(zeile)


## Die ganze Datei in einen String lesen

Du kannst auch den gesamten Dateiinhalt in einen einzigen String lesen:

    f = open('meine_datei.txt')
    text = f.read()

oder 

    text = open('meine_datei.txt').read()


## Eine Tabelle mit mehreren Spalten einlesen

Textdateien bestehen oft aus mehreren Spalten, etwa:

    Emily;Smith;23
    Charlie;Parker;45

Diese Datei lässt sich nach folgendem einfachen Muster einlesen:

    daten = []
    for line in open('meine_datei.txt'):
        columns = line.strip().split(';')
        vorname = columns[0]
        nachname = columns[1]
        alter = int(columns[2])
        eintrag = vorname, nachname, alter
        daten.append(eintrag)

Das Programm geht die Datei Zeile für Zeile durch (in der Zeile mit `for`). Dann schneidet es den Zeilenumbruch von jeder Zeile ab (`strip`) und unterteilt die Zeile an den `;`, so dass sich eine Liste ergibt.

Nach Umwandeln des Alters in einen Integer werden alle Elemente in einer weiteren Liste gesammelt.

### Die Methode `str.strip()`

Die Methode `strip()` schneidet *whitespace* (Leerzeichen, Zeilenumbrüche, Tabulatoren) von beiden Enden eines Strings ab. Der Code:

    text = "  dies ist Text   "
    print(text.strip())

gibt aus:

    dies ist Text

## Die Methode `str.split()`

Die Methode `split(x)` teilt einen String in eine Liste von Strings. Dabei ist `x` das Trennzeichen für die Spalten (voreingestellt sind Leerzeichen/Tabs).

    s = "dies ist Text"
    t = s.split(" ")
    print(t)

    ["dies", "ist", "Text"]
    
Die Methoden `strip()` und `split()` ergänzen einander hervorragend.

Die Module `csv` und `pandas` bieten effizientere Möglichkeiten zum Einlesen von Tabellen.


## Schreiben von Dateinamen und Verzeichnissen

Beim Öffnen von Dateien musst Du häufig auch den Namen des Verzeichnisses angeben. Dabei kannst Du einen vollständigen oder einen relativen Verzeichnisnamen angeben. Der vollständige Name enthält den gesamten Pfad (vom *root-Verzeichnis* oder *Laufwerksbuchstaben*), z.B.:

    C:/Python3/python.exe

Ein relativer Verzeichnisname beginnt beim Arbeitsverzeichnis, meist dem Verzeichnis, in dem das Programm ausgeführt wird:

    daten/meine_datei.txt

Mit dem `..` kannst Du in ein höher gelegenes Verzeichnis wechseln und dann in ein Unterverzeichnis wechseln:

    ../daten/meine_datei.txt

Auf Windows werden die Verzeichnisnamen oft etwas lang. Durch Klicken in die Adresszeile im Windows-Explorer kann man diese sehen und kopieren.

### Slashes

Verzeichnis- und Dateinamen werden durch normale Slashes `/` getrennt. Den unter Windows ebenfalls möglichen Backslash `\` musst Du durch einen doppelten Backslash `\\` ersetzen (weil `\` in Python verschiedene Sonderzeichen wie `\n` und `\t` einleitet).

    f = open('..\\meine_datei.txt')
    f = open('C:\\Python\\meine_datei.txt')


## Dateien Schließen

Das Schließen von Dateien in Pythonn ist nicht zwingend, aber empfohlen. Wenn Du zu viele Dateien auf einmal geöffnet hast, kann dies ein Problem darstellen.

    f.close()

## Dateien mit einem Context Manager einlesen

Modernes Python sieht zum Lesen das Verwenden eines **Context Managers** vor (ein Codeblock, der mit `with` beginnt). Der `with`-Befehl kümmert sich automatisch um das Schließen der Datei:

    with open('meine_datei.txt') as f:
        text = f.read()

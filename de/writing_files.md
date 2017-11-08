
# Textdateien schreiben

## Dateien zum Schreiben öffnen

Das Schreiben von Text in Dateien ist zum Lesen sehr ähnlich. Ein Hauptunterschied ist, dass Du den Parameter `'w'` wie *write* hinzufügen musst:

    f = open('meine_datei.txt','w')
    f.write(text)
    f.close()

## Eine Liste von Strings schreiben

Wenn Du eine Liste von Strings has, kannst Du diese mit einer Zeile in eine Datei schreiben. Du musst nur daran denken, am Ende jeder Zeile einen Zeilenumbruch hinzuzufügen:

    zeilen = ['Erste Zeile\n', 'Zweite Zeile\n']
    open('meine_datei.txt','w').writelines(zeilen)


## Eine Tabelle in eine Textdatei schreiben

Mit einer `for`-Schleife kannst Du mehrere Spalten mit Trennzeichen und Zeilenumbrüchen schreiben:

    names = ['Emily', 'Bob', 'Charlie']
    ages = [23, 45, 67]

    f = open('meine_datei.txt', 'w')
    for name, age in zip(names, ages):
        line = "{};{}\n".format(name, age)
        f.write(line)
    f.close()

Wie beim Lesen, lassen sich Tabellen mit den Modulen `csv` und `pandas` deutlich einfacher schreiben.


## Anhängen an eine Datei

Es ist auch möglich, einer bestehenden Datei etwas hinzuzufügen:

    f = open('meine_datei.txt','a')
    f.write('neue Zeile am Ende\n')
    f.close()


## Schließen einer Datei nach dem Schreiben

Beim Schreiben von Daten *puffert* Python diese im Speicher. Sie werden mit einer kleinen Verzögerung physikalisch geschrieben, oder sobald die Datei geschlossen wird. Durch Aufruf von `close()` schließt Du die Datei sofort.

    f.close()

## Dateien mit einem Context Manager schreiben

Der `with`-Befehl erzeugt einen **Context Manager**, der sich automatisch um das Schließen einer Datei kümmert. Dies ist die sauberste Variante:

    with open('meine_datei', 'w') as f:
        f.write('Noch eine Zeile\n')

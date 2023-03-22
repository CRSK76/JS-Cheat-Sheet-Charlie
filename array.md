# Array

## Definition

-> Ein Javascript Array ist eine Datenstruktur, die mehrere Werte (auch unterschiedlicher Datentypen und / oder Objekte) unter einem gemeinsamen Namen speichert. Auf diese Werte kann mit einem ganzzahligen Index zugegriffen werden. Die Reihenfolge der hinterlegten Daten wird durch deren Position im Array bestimmt. Das Array zählt zu Objekten in JS und der Zugriff auf die Werte erfolgt über den Index des Arrays (sichtbar über **console.table()** im Terminal).

-> eine Art "Setzkasten" mit Schubladensystem
-> auch Arrays können inneneinander geschachtelt werden

    //Das ist die Struktur eines Arrays
    const empty = [];
    // empty array

    // Folder kann mit let oder const Variablen ausgezeichnet werden. Const hat hier aber den Nachteil, dass man den Hauptfolder dann nicht mehr neu definieren kann (im nachhinein).

    let folder = [
        'one',
        2,
        ['three', 3.1],
        4.1
    ];

    console.log('typeof array -', typeof folder);
    console.log('typeof array fach 0 -', typeof folder[0]);
    console.log('fach 0 vor Änderung -', folder[0]);

    // Ich kann mit folder [] auf die einzelnen Schubfächer im Array zugreifen. Das System ist null-basiert. Sprich wir fangen bei Null an zu zählen


-> **console.table()** gibt das array so aus

    ┌─────────┬────────────────────────────┐
    │ (index) │           Values           │
    ├─────────┼────────────────────────────┤
    │    0    │ 'ich habe keine haustiere' │
    │    1    │         'wolfgang'         │
    │    2    │           'inge'           │
    │    3    │           'egal'           │
    │    4    │           'piep'           │
    │    5    │         'schnurz'          │
    └─────────┴────────────────────────────┘

-> Man kann einzelne Elemente im Array auch umbenennen

    folder[0] = 'zero';

-> **let** oder **const** bei array

    const folder = [
            'one',
         2,
         ['three', 3.1],
         4.1
     ];
    //folder = ['neu'];

-> führt zum Datenfehler und Absturz. Da const ja eine konstante "Variable" ist. Das ist der Nachteil. -> eher **let** verwenden

    //folder = ['neu'];
    //console.log(folder);

    // Hier mal die Ausgabe mit Nodemon:
    //[nodemon] starting `node arrays.js`
    //typeof array - object
    //typeof array fach 0 - string
    //fach 0 vor Änderung - one
    //fach 0 - zero
    //fach 2 - 3.1
    //['neu']

## Properties / Eigenschaften

### length()

    console.log('length of folder -', folder.length);

-> Über die length-Eigenschaft kann die Anzahl der im Array definierten Elemente abgefragt und auch gesetzt werden. Sie enthält einen positiven Zahlwert.

## Methods / Methoden

### indexOf()

-> durchsucht alle Elemente in einem Array, **[ein Element im Array]**

    array.indexOf([ein Element im Array],[Beginn])

->**[Beginn]** ist optional von dem aus der Index im Array durchsucht werden soll. Standart ist der **Index [0]**

-> funktioniert aber eindimensional

### push()

-> fügt ein oder mehrere Elemente / Werte an das Ende eines Arrays an

    folder.push('four', 5, 'six');
    console.log('folder complete -', folder);
    console.log('index of value 5 -', folder.indexOf(5));

### unshift()

-> fügt ein oder mehrere Elemente / Werte am Anfang des array ein und gibt die neue Gesamtlänge zurück

    const lAferUnschift = folder.unshift('zero');
    console.log('value index o -', folder[0])

-> gibt das hinzugefügte Element aus

    console.log('folder complete -', folder);

-> zeigt den Inhalt des Arrays komplett an

    console.log('new length afer unshift -', lAferUnschift);

-> das wirft nodemon aus

    value index o - zero
    folder complete - [ 'zero', 'zero', 2, [ 'three', 3.1 ], 4.1, 'four', 5, 'six' ]
    new length afer unshift - 8

### pop()

-> entfernt das letzte Element aus dem Array
-> Die Anzahl der Elemente im Array verändert sich, die Reihenfolge und die Position der verbleibenden Elemente allerdings nicht

    const popped = folder.pop();
    console.log('popped value -', popped);
    console.log('folder afert pop -', folder);

-> **nodemon wirft folgendes aus**

    folder complete - [ 'zero', 'zero', 2, [ 'three', 3.1 ], 4.1, 'four', 5, 'six' ]
    new length afer unshift - 8
    popped value - six
    folder afert pop - [ 'zero', 'zero', 2, [ 'three', 3.1 ], 4.1, 'four', 5 ]

### shift()

-> entfernt das erste Element im Array

    const shifted = folder.shift();
    console.log('shifted value -', shifted);
    console.log('folder after shift -', folder);


-> **nodemon wirft folgendes aus**

    folder afert pop - [ 'zero', 'zero', 2, [ 'three', 3.1 ], 4.1, 'four', 5 ]
    shifted value - zero
    folder after shift - [ 'zero', 2, [ 'three', 3.1 ], 4.1, 'four', 5 ]

### reverse()

-> kehrt die Reihenfolge der Elemente innerhalb eines Arrays um

    folder.reverse();
    console.log('reverted folder -', folder);

-> im **nodemon**

    folder after shift - [ 'zero', 2, [ 'three', 3.1 ], 4.1, 'four', 5 ]
    reverted folder - [ 5, 'four', 4.1, [ 'three', 3.1 ], 2, 'zero' ]

### concat()

-> vereint zwei oder mehre Arrays zu einem neuen und lässt die Orginal-Arrays aber unverändert

    const folder2 = ['blabla', 10, 'Alex'];
    const folder3 = folder.concat(folder2);
    console.log('folder3 concat folde and folder2 -', folder3);
    console.log('folder after concat-', folder);
    console.log('folder2 after concat -', folder2);

-> Ausgabe im **nodemon**

    reverted folder - [ 5, 'four', 4.1, [ 'three', 3.1 ], 2, 'zero' ]
    folder3 concat folde and folder2 - [ 5, 'four', 4.1, [ 'three', 3.1 ], 2, 'zero', 'blabla', 10, 'Alex' ]
    folder after concat- [ 5, 'four', 4.1, [ 'three', 3.1 ], 2, 'zero' ]
    folder2 after concat - [ 'blabla', 10, 'Alex' ]

### splice()

-> **entfernt** Elemente aus einem Array und **fügt** neue Elemente **ein**.

-> Syntax: **Array.splice(position [, anzahl [, element0, ..., elementN] ])**

->**position:** die Position im Array, an der Elemente gelöscht und eingefügt werden sollen. Ist dieser Wert negativ, dann wird vom Ende des Arrays aus gezählt.

-> **anzahl:** die Anzahl der zu löschenden Elemente

-> **element0, ..., elementN:** die neuen Elemente, die an der Position eingefügt werden sollen

### slice()

-> liefert einen Teil aus einem Array aus (Im Terminal), verändert aber das Array nicht. Wenn keine Endposition angegeben wurde, dann werden alle Elemente ab der Anfangsposition bis zum Ende zurückgeliefert.

-> Syntax: **Array.slice(anfang [, ende])**

-> **anfang** ist die Position des ersten Eintrags im Array, der extrahiert werden soll. 

-> **ende** ist die Position des letzten Eintrags im Array, der nicht mehr extrahiert werden soll. 

-> Die Parameter anfang und ende beziehen sind auf einen auf 0 (Null) basierenden Index vom Array. Das bedeutet, das erste Element im Array hat die Position 0 (Null). 

-> **Beachten Sie:**

-> Der Parameter **ende** _zeigt_ nicht auf das letzte Element, das extrahiert werden soll, sondern **auf das Element davor**.

### join()

-> verbindet alle Elemente eines Arrays zu einer Zeichenkette

-> Syntax: **join([Trennungstext])**

-> join erwartet einen Parameter (Trennungstext), der zwischen die einzelnen Elemente eingefügt wird, wenn sie in Strings umgewandelt werden. 

-> ausgegeben wird eine Zeichenkette mit allen Elementen aus dem Array, die duch den Parameter (Trennungstext) miteinander verbunden sind.

-> **Beachten Sie:** Wird kein Trennungstext übergeben, werden die Elemente mit einem Komma (",") ohne weiteres Leerzeichen verbunden.

    let stringworldcities = worldCities.join(", ");

    console.log(stringworldcities);

-> **nodemon** wirft aus:

    //vor dem join

    ┌─────────┬───────────────┐
    │ (index) │    Values     │
    ├─────────┼───────────────┤
    │    0    │  'Kuchumba'   │
    │    1    │  'Pion Jang'  │
    │    2    │ 'Waschington' │
    │    3    │   'Toronto'   │
    │    4    │ 'Phnom Penh'  │
    │    5    │   'Bangkok'   │
    │    6    │  'Budapest'   │
    │    7    │    'Prag'     │
    │    8    │  'Valletta'   │
    │    9    │   'London'    │
    │   10    │   'Berlin'    │
    └─────────┴───────────────┘

    //nach dem join

    Kuchumba, Pion Jang, Waschington, Toronto, Phnom Penh, Bangkok, Budapest, Prag, Valletta, London, Berlin



# Array

## Definition

-> Ein Javascript Array ist eine Datenstruktur, die mehrere Werte (auch unterschiedlicher Datentypen und / oder Objekte) unter einem gemeinsamen Namen speichert. Auf diese Werte kann mit einem ganzzahligen Index zugegriffen werden. Die Reihenfolge der hinterlegten Daten wird durch deren Position im Array bestimmt. Das Array zählt zu Objekten in JS und der Zugriff auf die Werte erfolgt über den Index des Arrays (sichtbar über console.table() im Terminal).

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


-> console.table() gibt das array so aus

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

-> let oder const bei array

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

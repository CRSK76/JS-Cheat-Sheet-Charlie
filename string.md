# String

-> Zeichenkette, Abfolge von Zeichen

-> einfasst mit 

    `` = Backticks
    '' = Singlequotes
    "" = Doublequotes

**-> _`` / Backticks_ haben die Besonderheit, man kann in ihnen weitere Variablen mit _${Wert}_ in den Code schreiben und somit mit dem ausgewiesenen String kombinieren kann und Strings mit Backticks können _über Zeilenumbrüche hinweg_ geschrieben werden**

## Zeichenketten verknüpfen / string concatenation

    const n = 'Charlie\'s';
    const strInclVar = n + ' Nase ' +
        'ist ' + n + ' lang';
    console.log('strInclVar -', strInclVar);


    const firstName = 'Charlie'
    const templateString = `Willkommen ${firstName}`; console.log('templateString -', templateString);


    const templStr2 = `Erste Zeile
            a a a  \${n}   ${n}     Zweite Zeile
    Dritte Zeile!`;
    console.log('templStr2 -', templStr2);

## Zeilenumbruch

    const lineBreak = 'Hallo\n\rWelt';
    console.log('lineBreak -', lineBreak);

## String-Eigenschaften / String-Properties

### lenght (Anzahl der Zeichen)

-> speicher die Anzahl der Zeichen einer Zeichenkette

-> **blaString.length**

    const hallo = 'Carsten'; console.log('cStr -', hallo.length, typeof hallo);
    console.log('raw string -', 'meinString'.length);


## String-Methods - Methoden & Funktionen

### _charAt()_ oder bracket notation (Zeichen an einer Position ermitteln)

-> **charAt_(index)_** -> gewünscht Position, an der das Zeichen ausgelesen werden soll

    const charAt = 'test'.charAt(1); console.log('charAt -', charAt);
    const charAtBracket = 'test'[2]; console.log('charAtBracket -', charAtBracket);

### substring () (Teilzeichenkette ermitteln)

-> gibt die Zeichenkette aus, die **ab einer** bestimmten Zeichenposition **bis zu einer** bestimmten Zeichenposition markiert wurde

    const substr = 'Der ist etwas länger, damit wir was zum extrahieren haben'.substring(2, 15);
    console.log('substr -', substr);

-> **String.substring(indexAnfang, indexEnde)**

oder 

    const substr = 'Der ist etwas länger, damit wir was zum extrahieren haben'.substring(15);
    console.log('substr -', substr);

-> **String.substring(indexEnde)**

oder

-> **String.substring(indexAnfang)**

### upper-/lowerCase() - Umwandlung der Zeichenkette in Groß- oder Kleinbuchstaben

    const upper = 'alles klein';
    console.log('upper -', upper.toUpperCase())
    const lower = 'ALLES GROSS';
    console.log('lower -', lower.toLowerCase());

-> die Orginalzeichenkette bleibt dabei unverändert

### trim(), trimstart(), trimend() - entfernt alle whitespaces (Leerzeichen, Tabs, Zeilenumbrüche) am Anfang und Ende eines Strings

    console.log('trim -', '   alks    askdfa  kl asf af      '.trim(), '.');
    console.log('trimStart -', '   alks    askdfa  kl asf af      '.trimStart(), '.');
    console.log('trimEnd -', '   alks    askdfa  kl asf af      '.trimEnd(), '.');

-> die ursprüngliche Zeichenkette bleibt aber erhalten

-> Anwendung bei der Passwort-Eingabe z.b.

    var elem = document.getElementById('button');
    elem.addEventListener('click', LeerstellenEntfernen);	
 
    function LeerstellenEntfernen() {
        var Eingabe = '     mein Passwort    ';
        var Passwort = '-' + Eingabe.trim() + '-';
        var ausgabe = document.getElementById('ausgabe');
        ausgabe.innerHTML = Passwort;
    }

### includes('') - Prüfen ob eine bestimmte Zeichenkette im Wert / in diesem Falle String einer Variable enthalten ist

-> optional kann mit der Hilfe einer positiven Ganzzahl (Integer-Zahl) die Startposition für die Suche angegeben werden

-> das Suchergebnis ist true oder false

    console.log('includes -', 'Einen lange Satz.'.includes('Satz'));
    console.log('includes -', 'Einen lange Satz.'.toLowerCase().includes('einen', 7));

### padEnd / padStart() - Zeichenkette am Ende und am Anfang auffüllen

    const pad = 'Mehr';
    console.log('padEnd -', pad.padEnd(7, '.'));
    console.log('padStart -', pad.padStart(7, '.'));


### Index - Notation

    let programmingLanguage = 'JavaScript';

    let isFun = true;

    console.log(programmingLanguage + ' is fun: ' + isFun);

    //10. Gib das "J" und "S" von "JavaScript" aus der Variable "Programmiersprache" auf der Konsole aus. 

    Mittels Index-Notation.

    console.log(programmingLanguage[0] + ' ' + programmingLanguage[4]);

-> zeigt die Buchstaben J und S in der Konsole / im Terminal an. **Variable[Nummer des Buchstabens]** 
-> wird mit eckiger Klammer geschrieben

### Weitere String-Properties

-> **slice()** <https://wiki.selfhtml.org/wiki/JavaScript/Objekte/String/slice>

-> **Übersicht aller:** <https://wiki.selfhtml.org/wiki/JavaScript/Objekte/String>
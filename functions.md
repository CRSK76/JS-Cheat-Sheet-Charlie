# Funktionen

-> "Unterprogramme" -> helfen große Programm(abläufe) zu gliedern, ihnen Namen zu geben und diese wiederzuverwenden

-> ein gesamtes Programm -> Zerlegung in einzelen Aufgaben -> weitere Zerlegungn in einzelne Schritte => das sind dann die Funktionen

->Aufruf der Funktion mit ihren unterschiedlichen Parametern -> die Parameter geben Aufschluss darüber, welche Aufgaben die Funktion erfüllt -> die Ergebnisse gibt sie dann zurück

## Aufbau einer Funktion

    function funktionsname(Parameterliste) {
        // Anweisungen
    }   

-> Namen, Parameter (einer oder mehrere Variablennamen), Rückgabewert
-> **Paramerte** = Eingabewerte für die Funktion -> stehen innerhalb der Funktion als lokale Variablen zur Verfügung
-> über die Parameter werden Werte = Argumente in die Funktion gegeben -> Verarbeitung in der Funktion -> Rückgabewert = Verarbeitungsergebnis

-> **definition** der Funktion

    function multiplySelf(x) {
        const result = x * x;
        console.log(result);
    }

-> **aufruf** der Funktion mit ()

    multiplySelf();
    multiplySelf(3);

-> **referenzieren** der Funktion **ohne** ()

    const referenceMultiplySelf = multiplySelf;
    referenceMultiplySelf(7);

    for (let i = 0; i < 3; i++) {
        multiplySelf(i);
    }

    console.log('--------- def assignment ----------');

-> **definiton** per Zuweisung

    const addSelf = function (y) {
        const result = y + y;
        console.log(result);
    }

    console.log(typeof addSelf);
    addSelf(6);

    const referenceAddSelf = addSelf;
    referenceAddSelf(2);

## Funktion als Objekt

-> man kann ihr neue Eigenschaften geben

-> kann sie an Variablen zuweisen

-> anderen Funktionen als Argument übergeben

-> oder als Rückgabewert einer anderen Funktion erhalten

-> können auch Eigenschaft eines anderen Objektes sein => dann sind sie eine Methode

-> selbst definierte und / oder auch objektunabhängige vordefinierte Funktionen

## objektunabhängige Funktionen

-> bereits im JS vordefiniert

-> jederzeit aufrufbar, ohne sie vorher selbst definieren zu müssen

## selbstdefinierte Funktionen

-> Keyword / Schlüsselwort function definiert die Funktion

### Funktionsdeklaration als Statement

-> **function declaration statement** = 1. Keyword (**function**) 2. **Funktionsname** 3. **(Parameter** möglich mit Komma getrennt**)** 4. **{ Funktionskörper mit Anweisungsblock};**

    function color(farbe1, farbe2, farbex, ...) {
        Anweisungsblock -> tue etwas
        und
        otionale Rückgabe mit return
    };

-> Deklaration erzeugt einen **Gültigkeitsbereich = Scope** -> in dem die Variable mit dem Namen Funktion steht

-> entsteht ein **Funktionsobjekt** -> **Instanz des Function-Kunstruktors** **mit** angegebenen **Argumenten** **und** dem gegebenen **Körper**

-> Zuweisung des Objektes an die Variablen

-> **automatisches Heben** an den Beginn des Scopes (Gültikeitsbereiches) = **hoisting** durch das Funktionsdeklarations-Statement (genauso wie bei der Variablendeklaration)

-> Vorteil vom hoisting -> Aufruf der Funktion auch vor dem Funktionsdeklarations-Statement möglich

    color();

    function color(farbe1, farbe2, farbex, ...) {
            Anweisungsblock -> tue etwas
            und
            otionale Rückgabe mit return
    };

### Achtung! Möglichst keine Funktionen innerhalb von Anweisungsblöcken anderer Funktionen deklarieren (strict mode)

### Funktionsausdruck (function expression) = Funktionsliteral

-> Deklaration einer Funktion **in Abhängigkeit einer bestimmten Bedingung** -> **Funktionsausdruck**

    let col = function (farbe1, farbe2, farbex, ...) {
            Anweisungsblock -> tue etwas
            und
            otionale Rückgabe mit return
    };

-> **kein autarkes Statement** -> Funktionsausdruck also bitte nicht am Beginn eines Statemens stehen -> sonst Missdeutung von JS als Funktionsdeklarations-Statements

-> Das **Semikolon** **am Ende** des Funktionsausdruckes ist **erforderlich**

-> Ein Funktionsausdruck = eine **anonyme Funktion** = hat keinen Funktionsnamen

-> Funktionsausdruck **normalerweise ohne Funktionsnamen ** (der in einem Funktionsdeklarations-Statement Variablen erzeugen würde)

-> kann dennoch einen Namen enthalten, um den Funktionsausruck zu referenzieren -> um sich selbst aufrufen zu können

-> Funktionsausdrücke können die Variablen einer übergeordneten Funktion separieren, sprich enthalten 

    tuwas(3);       // Funktioniert
    machwas(5);     // Error: machwas ist keine Funktion

    function tuwas(q) {
       return q*3;
    }

    let machwas = function(q) {
         return q*5;
         }

    machwas(17);    // Hier funktioniert es.

## Pfeilfunktionen (Arrow) / Lambda-Ausdruck

-> 

    const isString = (input) => {

       return typeof input === 'string';

    }

    isString("word");

    console.log(isString("word"));

## Funktionen mit Parameter

    var summe = function (summand1, summand2) {     // (1)
        var summe = summand1 + summand2;            // (2)
        return summe;                               // (3)
    };
    alert(summe(40, 2));                            // (4)

    -> 1. erzeugt eine Funktion, die 2 **Argumente** erwartet, weißt sie der Variablen "summe" zu

    -> 2. Funktionskörper Notierung der Logik der Funktion
    
    -> 3. ein Wert wird zurückgegeben, die Summe einer Addition (return)
    
    -> 4. Aufruf der Funktion alert -> Übergabe des Rückgabewertes der Funktion Summe als **Paramter** an die Funktion allert

-> **Parameter und Argumente? Was ist was?**

-> **Argumente** sind die Werte, die man beim Aufrufen einer Funktion übergibt

-> die Variablen, in denen dann die Argumente innherhalb einer Funktion zur Verfügung stehen = **Parameter**

-> zu **wenige Argumente** -> es **bleiben Parameter frei** -> werden mit **undefinded** initialisiert

-> bei **zuvielen Argumenten** -> nur soviele Argumente in Parameter übertragen, wie definiert sind -> Zugriff mittesl arguments

-> **Definition** eines **Rest-Parameters**, wobei dieser die restlichen Parameter als **Array** aufnimmt -> wird mi **drei vorangestellten Punkten notiert** **...**

    //4. Schreibe eine Funktion mit dem Namen `largestNumInArray` die ein Array von Zahlen als Parameter entgegennimmt. Sie soll die größte Zahl in dem Array zurückgeben. Für die Eingabe `[1,6,83,91,0,-4,1337,5]` sollte sie `1337` zurückgeben

    function largestNumInArray(ar) {
        // console.log(ar)
        return Math.max(...ar)
    }
    largestNumInArray([1, 6, 83, 91, 0, -4, 1337, 5]);

    console.log(largestNumInArray([1, 6, 83, 91, 0, -4, 1337, 5]));

## Parameterbindung

-> **wie Funktionsargumente mit Funktionsparameter verbunden sind (_call-by-reference_, _call-by-value_ sind die häufigsten)
**

-> **call by reference**

-> **Parameter zeigt direkt auf die Variable, die sich im Funktionsargument befindet**

-> **Vorteil**: man kann leicht mehrere Werte aus einer Funktion zurückerhalten, -> Die Werte, die die Funktion in ihre Parameter schreibt, dort landen, wo der Aufrufer sie hergeholt hat

-> **Nachteil**: kann unbeabsichtigt geschehen, Funktionsargumente können ausschließlich Variablen sein (Formelergebnisse + Programmconstanten sind so nicht referenzierbar)

-> **call by value** 

-> **in den Parametern befinden sich Kopien der Argumente**

-> **Vorteil**: kann nicht unbeabsichtigt überschrieben werden, Konstanten + Ausdrücke können ebenso als Argumente übergeben werden

-> **Nachteil**: benötigt bei großen Arrays / Objekten viel Speicherplat, kann ein Programm merklich verlangsamen

-> **Javascript arbeitet mit einer Mischform** (entscheidend ist, um welche Datenformm es sich handelt)

-> primitive Daten (null, undefined, Zahlen, Strings, boolesche Werte) können problemlos mit call-by-value gebunden werden  -> benötigen nur wenig Speicherplatz

-> anders Objekte wie Arrays -> sind eigenständige Einheiten im Speicher -> sie werden genaugenommen nicht in einer Variablen gespeichert, sondern in den Variablen befindet sich lediglich ein Verweis auf dieses Objekt

-> weißt man genau diese Variable einer anderen zu, weißen dann beide Variablen auf das gleiche Objet (ähnlich verhält es sich, wenn das Objekt als Argument an eine Funktion übergeben wird. Sprich also ein Verweis auf das Objekt übergeben wird)

-> **bei Objekten ähnelt das einem call-by-sharing **

## Funktionen mit Rückgabewert

-> mit **einem Return** kann genau **ein Wert** an die aufrufende Instanz zurückgegeben werden

-> eine Funktion kann aber **mehrere return-statements** enthalten -> sie **beenden** die **Funktion** und **definieren** den **Rückgabewert**

-> **Rückgabewert** kann (genau wie die Funktionsargumente) ein **primitiver Wert** oder auch ein **Objekt** sein

-> **wenn kein return** innerhalb einer Funktion aufgerufen wird - > wird die Funktion nach dem letzten Statement verlassen und als **undefined** zurückgegeben

### Achtung zwischen return und Rückgabewert dürfen keine Zeilenumbrüche stehen, JS glaubt sonst, da würde ein ; fehlen und fügt eins automatisch in Semikolon ein

->**mehr als ein Wert** kann man nur an eine Funktion zurückgeben, wenn es sich um ein **Array** bzw. ein **Objekt** handelt bzw. die Werte dort drin stehen und auf diese Weise verkapselt als ein Wert zurückgegeben werden

## Variablen Scope

-> Scope = Gültigkeitsbereich und Bereich, in dem die Variable sichtbar ist

-> globaler Scope = dort befinden sich alle Variablen, die außerhalb einer Funktion definiert wurden

-> innerhalb einer definierten Funktion -> eigener Scope gütlig -> Funktionsscope -> für die Parameter der besagten Funktion und alle Variablen, die innerhalb der Funktion definiert wurden

-> globaler Scope dem Funktionsscope übergeordnet

-> wird innerhalb des Funktionsscopes eine Variable genutzt, die im inneren Scope nicht definiert wurde wird auf die Variable im äußeren Scope zurückgegriffen

-> wird im Funktionsscope eine Variable angelegt, die es im globalen Scope schon gibt wird die im globalen Scope von der im inneren Scope überdeckt

```
var bar = 1;
var baz = 17;
var foo = function () {
    var baz = 2;             // Erzeugt eine neue Variable im inneren Scope
    var zap = 9;             // Noch eine neue Variable
    return bar + baz + zap;
  };
foo();                       // Gibt 12 zurück
bar + zap;                   // Erzeugt einen Ausführungsfehler, da zap nicht definiert wurde.
```
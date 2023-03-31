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

    
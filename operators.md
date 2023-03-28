# Operatoren

-> <a href="https://wiki.selfhtml.org/wiki/JavaScript/Operatoren">Die Gesamte Übersicht der Operatoren-Arten</a>

## Zuweisungsoperator

-> **=** Dieser Operator weißt der Variable einen Wert zu

    let blah = 42;

## Rechenoperatoren

-> benötigen wir für nummerische Berechnungen im JS

-> **+** zum Addieren

-> **-** zum Subtrahieren 

-> __*__ zum Multiplizieren

-> **/** zum Dividieren

-> **%** für den Rest einer Division (Modulo) 

-> __**__ zum Potenzieren

-> **Reihenfolge der Rechenoperatoren** wenn in Ausdrücken mehrer Operatoren enthalten sind 

-> JS hat eine Reihenfolge festgelegt, in der die Operatoren berechnet werden (Grundregeln der Mathematik)

-> zuerst __**__, 
dann __*__, **%** und **/**,
danach **+** und **-** 

-> beim Abweichen von der Reihenfolge -> mit Klammern arbeiten

-> code-Beispiele:

    const plus = 1 + 1; console.log('plus - ', plus);
    const plusString = 'str1' + 'str2'; console.log('plusString - ', plusString);

    const minus = 2 - 1; console.log('minus - ', minus);
    const minStr = 'str1' - 'str2'; console.log('minstr - ', minStr);

    const multiply = 2 * 2; console.log('multi - ', multiply);
    const divide = 4 / 2; console.log('divide - ', divide);

    const calc = 1 + 2 * 3; console.log('calc - ', calc);

-> JS ignoriert das Assoziationsgesetz der Mathematik, stattdessen strenge Auswertungsreihenfolge der Operatoren, wenn sie in einem Ausdruck hintereinander stehen (außer bei der Potenz, ansonsten immer von links nach rechts ausgewertet)

-> **Rechenoperation mit Zuweisung**

    let a = 1;
    a += 3; console.log('addition assign - ', a);
    // same as a = a + 3;

    a -= 2;
    a *= 2;
    a /= 2;

    console.log('result', a);

-> Verwendet man, wenn man den Wert von Variablen umrechnen will und das Rechenergebnis wieder in der selben Variable speicher will -> mit automatischer Neuzuweisung des Wertes an die Variable

    var zahl = 0;

    zahl +=  3; //  3
    zahl -=  2; //  1
    zahl *= 18; // 18
    zahl /=  3; //  6 
    zahl %=  5; //  1

    Addition:           a += b -> a = a + b
    Subtraktion:        a -= b -> a = a - b
    Multiplikation:     a *= b -> a = a * b
    Division:           a /= b -> a = a / b
    Rest bei Division:  a %= b -> a = a % b


## Vergleichende Operatoren / comparision operators

    let less = 2 < 1; console.log('less - ', less);
    let lessOrEqual = 2 <= 1; console.log('lessOrEqual - ', lessOrEqual);

    let greater = 2 > 1; console.log('greater - ', greater);
    let greaterOrEqual = 2 >= 2; console.log('greaterOrEqual - ', greaterOrEqual);

    let equal = 'äpfel' == 'birnen'; console.log('equal', equal);
    let equalTwo = 1 == '1'; console.log('equal two', equalTwo);

-> Vergleichoperatoren vergleichen zwei Werte, werden oft in **bedingten Anweisungen (if-Abfrage) und Schleifen** verwendet -> liefern als Ergebnis **boolesche Werte aus (true oder false)** von **Datentyp boolean** aus

-> entweder true (wahr) oder false (falsch)

-> **Weiterführendes:** <a href="https://wiki.selfhtml.org/wiki/JavaScript/Operatoren/Vergleichsoperatoren">Alles über Vergleichsoperatoren</a>

## strict equal und strict notEqual Operatoren

    let strictEqual = 1 === '1'; console.log('strict equal -', strictEqual);

    let notEqual = 'äpfel' != 'birnen'; console.log('notequal', notEqual);
    let strictNotEqual = 1 !== 2; console.log('strict notequal', strictNotEqual);

-> **===** ->	**istgleich** -> true, wenn beide Werte gleich und außerdem gleichen Typs sind, sonst false.
-> **!==** -> **ungleich** -> true, wenn die Werte 
ungleich oder nicht gleichen Typs sind, sonst false.

## logische Operatoren (logical operator)

-> Anwendung in Abbruchbedingungen von Schleifen und bedingten Anweisungen, ...
-> nicht nur auf true und false beschränkt, sondern auch Werte-Eigenschaften **truthy = true** und **falsy = false**

-> **&&** - Operator (**logisches und, logical and**): -> Verknüpfung 2 oderer mehrere Bedingungen durch und -> d.h. beide oder alle Bedingungen müssen erfüllt sein, damit die komplette Bedingung erfüllt ist

-> findet den ersten ungültigen / ungesetzten Wert oder nehme den letzten gültigen

-> findet den ersten gültigen / gesetzten Wert

        const or = dataFromServer || x || def; console.log('or -', or);
        if (set || unset) { }


-> **||** - Operator (**logisches oder, logical or**): -> Verknüpfung 2 oderer mehrere Bedingungen durch oder -> es genügt wenn eine der Bedingen erfüllt ist, damit die gesamte Bedingung erfüllt ist

-> findet den ersten gültigen / gesetzten Wert

    const or = dataFromServer || x || def; console.log('or -', or);
    if (set || unset) { }


-> **!** - Operator: ->prüft, ob ein Ausdruck unwahr ist (bei falsy, Leerstring, null, undefiniert oder 0)

    let not = !false;
    // logical not ! (logische nicht)
    // kehrt den Wert eines boolean um
    not = !not; console.log('not -', not);
    not = !not; console.log('not -', not);

    // umwandlung in einen bool 
    const bool = !!y; console.log('doubleNot -', bool);

    // ternary () ? : operator - assignment

    const ternary = (1 < 0) ? z : y; console.log('tern assign -', ternary);

    // if else
    // ternary - condition
    (1 < 0) ? console.log('wahr') : console.log('unwahr');


    // wert 1 - operator - wert 2
    // 1 + 5 * 7
    const wert1 = 5;
    const wert2 = 1;
    const operator = '+';

    let result;
    (operator == '*') ? result = wert1 * wert2 : null;
    (operator == '/') ? result = wert1 / wert2 : null;
    (operator == '+') ? result = wert1 + wert2 : null;
    (operator == '-') ? result = wert1 - wert2 : null;

    console.log('calc -', result);

## ternarey Operator = ternärer Operator

-> Ternary wird bei einfachen if then else Bedingungen eingesetzt, **wenn das Ergebnis der Bedingung true oder false ist**.

-> ist eine kompakte Schreibweise für **eine** bedingte Zuweisung

-> besteht aus 3 Operanten (Variable **=** *Bedingung* **?** *wenn true* **:** *wenn false*;)

    // Das ist die Einfache If-Else-Anweisung

    if (let age < 18) {            // Bedingung
        schockenOhneEnde ();    // true
    } else {                    // Bedingung trifft nicht zu
        noZiggies ();           // false
    }

    // oder eben der Ternäre Operant
    // in Anfänger-Schreibweise

    vernunft =               // Variable
    age < 18                // Bedingung (Operant I)
    ? schockenOhneEnde ()   // wenn true (Operant II)
    : noZiggies ();         // wenn false (Operant III)

    // Schreibweise für Fortgeschrittene

    vernunft = age < 18 ? schockenOhneEnde () : nochZiggies ();




-> **Weiteres:** <a href="https://wiki.selfhtml.org/wiki/JavaScript/Operatoren/Logische_Operatoren">Alles über Vergleichsoperatoren</a>">
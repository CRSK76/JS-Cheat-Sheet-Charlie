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
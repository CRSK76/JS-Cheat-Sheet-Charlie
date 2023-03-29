# If-Bedingungen

-> Die Ausführung von Anweisungen wird von Bedingungen abhängig gemacht. Es sind dann bedingte Anweisungen (Verzweigungen). 

-> Es wir dein Anweisungsblock durchlaufen, wenn eine bestimmte Bedingung erfüllt ist. (**einfaches if**) Alternativ dazu kann bei Nichterfüllung der Bedingung ein zweiter Anweisungsblock durchlaufen werden (**if-else**)

## allgemeines Schema

        if (Bedingung) {
           //Anweisungsblock des True-Zweigs (wird ausgeführt, wenn Bedingung erfüllt ist)
            Anweisung;
            Anweisung;
        } else {
            //Anweisungsblock des False-Zweigs (wird ausgeführt, wenn Bedingung nicht erfüllt ist)
            Anweisung;
            Anweisung;
        }

-> Zum Formulieren der Bedingungen **(if())** benötigt man oft Vergleichsoperatoren und auch Variablen. Anweisungsblöcke stehen in geschweiften Klammern **{}**

## Beispiele

    // if -abfrage

    let today = `Thursday`;
    if (today === `Thursday`) {
        //Bedingung = today = Datentyp String + Donnerstag => stricktly equal
        // Anweisung ...
        console.log(`Today is ` + today);
    }


    // da hier nur eine Bedingung, kann man das auch so schreiben

    if (today === 'Thursday') console.log('true');

-> Bedingungen können aber auch logischem && (und) bzw. logischem || (oder) kombiniert werden

    // komplexere Bedingung mit oder

    today = 'Sunday';
    if (
        today.toLowerCase() === 'saturday' ||
        today.toLowerCase() === 'sunday'
    ) {
        //sleep long
        // have breakfast in bed
        console.log('Yeah its weekend');
    }

    // komplexe Bedingung mit und (&&)

    today = 'Thursday';
    if (
        today.toLowerCase() !== 'saturday' &&
        today.toLowerCase() !== 'sunday'
    ) {
       //meine ausdrücke
       console.log('Uhaaah its weekly Workday');
    }

    today = null;
    if (
        //today !== null &&
        //today !== undefined &&
        typeof today === 'string' &&
        // ist die Abkürzung für null / undefined, verhindert einen unbehandelten Error, sonst wäre das Programm abgestürzt
        today.toLowerCase() !== 'saturday' &&
        today.toLowerCase() !== 'sunday'
    ) {
        //meine ausdrücke
        console.log('Uhaaah its weekly Workday');
    }

## if-else 

-> wenn die Bedingung (if()) nicht erfüllt ist, kann ein zweiter Anweisungsblock durchlaufen werden

    today = 'sunday'
    if (
        today === 'monday') {
        console.log('Its monday')
    }
    else {
        // können n ausdrücke stehen
        console.log('else - Its ' + today);

    }

## if-kette

-> enthält **mehrere if-bedingungen**

    if (today === 'monday') {
        console.log('Monday');

    } else if (today === 'tuesday') {
        console.log('Tuesday');

    } else if (today === 'wednesday') {
        console.log('Wednesday');

    } else {
        console.log('Weekend')
    }

-> eine if-Ketten kann auch durch den **switch-Befehl** ersetzt werden: -> <a href="switch.md">Alles über switch</a>

## ternary-Operator / ternärer Operator

-> für einfache If-Else-Bedingungen kann man auch den ternary-Operator verwenden

    // ternary operator
    (true) ? 'wahr' : 'falsch';

    // assign a variable
    const tern = (true) ? true : false;

    // same as above
    let ifVar;
    if (true) {
        ifVar = true;
    } else {
        ifVar = false;
    }

    (true) ? console.log('true') : console.log('false');

    (today === 'sunday')
        ? console.log('Sunday')
        : today === 'tuesday'
            ? console.log('Tuesday')
            : console.log('Neither Sonday or Tuesday');

    // same as

    if (today === 'sunday') {
        console.log('Sunday')

    } else if (today === 'tuesday') {
        console.log('Tuesday');

    } else {
        console.log('Neither Sonday nor Tuesday')
    }

-> Ein ternary-Operator kann nur **eine** mögliche Bedingung mit **2 klaren** Ergebnissen abbilden **(true / false, wahr / falsch)**, wohingegen ein if-else mehrer Bedingungen mit mehreren Ergebnissen beinhalten kann, also für komplexere If-Bedingungen verwendet wird

-> ??? für **ternary** kann ich die *const-Variable* verwenden, für **if-Bedingungen** nicht?

-> Assignment 14 -> 6. Prüfe, ob die folgenden Zahlen gerade Zahlen sind. Verwende einen Ternär und wenn die Zahl gerade ist (z.B. `30`), gib `30 is even` aus. Wenn nicht (z.B. `31`), gib `31 is odd` aus.
num1 = 30
num2 = 939
num3 = 40.9

    const nr1 = 30;
    const nr2 = 31;

    //modulo (%) Operator -> Er liefert den verbleibenden Rest bei der Division zweier Zahlen. Ungerade Zahlen -> % -> Dezimalzahl wird ausgeliefert. Ein Float. 

    const nr = 9;
    const result = nr % 2;
    (result === 0) ? console.log(`${nr} is even`) : console.log(`${nr} is odd`);

    if (result === 0) {
        console.log(`Ergebnis mit if-else: ${nr} is even`);
    } else if (result !== 0) {
        console.log(`Ergebnis mit if-else: ${nr} is odd`);
    }

-> <a href="opertors.md">tenary versus if</a>
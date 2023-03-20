# String

-> Zeichenkette, Abfolge von Zeichen

-> einfasst mit 

    `` = Backticks
    '' = Singlequotes
    "" = Doublequotes

**-> _`` / Backticks_ haben die Besonderheit, man kann in ihnen weitere Variablen mit _${Wert}_ in den Code schreiben und somit mit dem ausgewiesenen String kombinieren kann und Strings mit Backticks können _über Zeilenumbrüche hinweg_ geschrieben werden**

## Zeichenketten verknüpfen / string concatenation

    const n = 'Carsten\'s';
    const strInclVar = n + ' Nase ' +
        'ist ' + n + ' lang';
    console.log('strInclVar -', strInclVar);

    const firstName = 'Carsten'
    const templateString = `Willkommen ${firstName}`; console.log('templateString -', templateString);

    const templStr2 = `Erste Zeile
            a a a  \${n}   ${n}     Zweite Zeile
    Dritte Zeile!`;
    console.log('templStr2 -', templStr2);

## Zeilenumbruch

    const lineBreak = 'Hallo\n\rWelt';
    console.log('lineBreak -', lineBreak);

## String-Eigenschaften


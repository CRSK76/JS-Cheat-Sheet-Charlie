# Arten von Variablen im JS

## Was ist eine Variable überhaupt?

-> Variable = **Name für einen String**

-> varmessage = **'Hello World!'**

-> vergleichbar mit einem leeren Karton, der verschiedenartig **deklariert** wird **(const, let, var)** und **genau _einen Wert_ / String** aufnehmen / beinhalten kann

-> Der **Name** einer Variable ist **unveränderlich**, wohingegen **ihr Wert verändert** werden kann

## Var - der Vater der Variablem

-> Variable unabhängig von ihrem Gültigkeitsbereich (Scope, Z.b. innerhalb einer Funktion), global

-> sehr allgemeine Variable

-> gleichlautende Variablen unterschiedlicher Scripte können sich leicht überschreiben und zu Programmfehlern führen

-> Falschreibung der Var -> ursprüngliche Var bleibt leer und eine neue wird erstellt

**-> Var zu ungenau, wird nicht mehr verwendet, stattdessen _const_ und _let_**

## Const

-> symbolische Konstante, deklariert eine unveränderliche Variable

-> const wird an einen Wert gebunden, der im Code-Verlauf nicht verändert werden kann (immutable)

-> und kann nicht mit gleichem Namen zweimal im code auftauchen

-> ist also nicht überschreibbar

## Let

-> ist eine lokale Variable im Block Skope (innerhalb einer Funktion)
-> sie ist veränderbar
-> muss nicht gleich deklariert werden

## Zu beachten

-> Referenzen auf DOM-Elemente in ihrer Ein- und Ausgabe unveränderlich -> werden als const im Script angelegt, ebenso die Zahl PI

> Das DOM (Document Object Model) ist die Schnittstelle 
> zwischen HTML und dynamischem JavaScript. Alle Elemente 
> werden zu Objekten, die dynamisch aufgerufen, 
> verändert, hinzugefügt und gelöscht werden können.

Zitat: <https://tinyurl.com/84zjya8h>

-> Variablen text und alter werden mit let angelegt -> aufgrund veränderliche Werte im Scriptverlauf

    **Variablendeklaration am Anfang eines Scripts.**

    const button = document.querySelector('#interaktiv'),
        output = document.querySelector('output'),
        PI     = 3.14; 
    let   text   = 'Hallo Welt!';
    let   alter;

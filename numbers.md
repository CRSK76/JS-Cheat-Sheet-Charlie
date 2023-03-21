# Numbers

## 3 verschiedene Definitionen

-> **Datentyp für Zahlenwerte** (im Normalfall findet dies Aufgabe meist Anwendung)

-> **Funktion**, die beliebige Werte in Zahlenwerte konvertiert

-> **vordefiniertes Objekt**, dass dazu dient, Zahlenwerte als Objekt zu kapseln


## Number Objekt

-> Zugriff au die Eigenschaften numerischer Werte

### Methoden

-> isFinite() prüft einen Wert, ob er Number ist und eine gültige Zahl darfstellt 

-> **globale isNaN-Funktion** im Gegensatz ur **Number.isNaN** keie Typkonvertierung

-> Syntax: Number.isNan(wert); -> Wert = der zu Prüfen ist, prüft auf ist der Wert keine Number? mit doppelter Verneinung -> ja, Wert ist eine Number

    const eingabe = 124400
    // Prüfen, ob Wert eine Zahl ist
    const istZahl = !isNaN(eingabe)
    //doppelte Verneinung

    console.log(istZahl)
    // Wenn ja, ausgeben im exponent-Format
    // Wenn nein, 'Ist keine Zahl' ausgeben
    const ausgabe = istZahl ? eingabe.toExponential() : 'keine Zahl'
    console.log(ausgabe)

-> **parseIn-Funktion** 

-> wandelt eine übergebende Zeichenkette in eine Ganzzahl um und gibt diese als Ergebnis aus -> bei Anwenderangaben, mit denen man später noch rechnen möchte

-> Syntax: **var ergebnis = parseInt(string, radix);** (*string* = Zeichenkette, die umgewandelt wird. *radix* = optionaler Parameter, der die Basis des Zahlensystems angibt)

-> Weitere Infos: <https://wiki.selfhtml.org/wiki/JavaScript/parseInt>

-> **parseFloat() - globabe Funktion**

-> wandelt den Wert der Funktion (eine Zeichenkette) in eine Zahl um und gibt diese als numerischen Wert zurück 

-> Kommazahlen werden berücksichtigt

-> Punkt wird als Dezimalzeichen interpretiert

-> findet Anwendung bei der Anwendereingabe, die in Zahlen umgewandelt werden, damit man anschließend mit ihnen rechnen kann

-> Syntax: **var ergebnis = parseFloat(string)** (String = zu überprüfende Zeichenkette)

    const product = 'Banana'
    const price = '2.50€'
    const priceNum = parseFloat(price)

    console.log('priceNum', priceNum)

    const weight = 0.75;

    const sum = weight * priceNum

    console.log(isNaN(sum) ? 'Preis kann nicht berechnet werden' : 'Summe zu zahlen: ' + sum.toFixed(2) + '€')

-> **toFixed()** 

-> erwingt eine bestimmte Anzahl an Nachkommastellen

-> Syntax: zahl.toFixed(digits); 

-> digits -> Standardwert = 0, max. Nachkommastellen = 20

-> **toExponential()**

-> erzwingt die Exponentialschreibweise einer Zahl

    //                         40 x 1000000
    const earthCircumference = 40e6

    console.log(`Halb um die Welt: ${earthCircumference / 2}`)

    //                  8 / 1000
    const widthOfHair = 8e-3

    console.log(`Zwei Haar breit ${widthOfHair * 2}`)

    console.log(10928323463325 * 12039432468510)

    const distanceToSun = 148000000

    console.log(`Entfernung zur Sonne: ${distanceToSun.toExponential()}`)

    const pi = 3.1415926535897932384626433832795028841971693993751058209749445923078164062862089986280348253421170679821480865132823066470938446095505822317253594081284811174502841027019385211055596446229489

    console.log(pi.toFixed(5))






































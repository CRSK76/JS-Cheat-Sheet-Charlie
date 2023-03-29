# Schleifen
-> sind eine kontrollstruktur / programmierkonstrukt -> erfüllen den Zweck, eine Anweisung oder eine Gruppe von Anweisungen so lange auszuführen, bis eine bestimmte Bedingung erfüllt ist oder nicht mehr erfüllt ist

-> **Schleifenrumpf** = wiederholende Anweisungen

-> **Schleifenbedingung** = ist die Bedingung, die die Schleife steuert / einleitet

-> **Kopfgesteuerte Schleife (While-Schleife)** = Auswertung der Schleifenbedingung erfolgt vor der Ausführung des Anweisungsblockes / des Schleifenrumpfes

-> **fußgesteuerte Schleife (Do-While-Schleife)** = Auswertung der Schleifenbedingung erfolgt nach der Ausführung des Anweisungsblockes / des Schleifenrumpfes

-> werden oft mit Arrays kombiniert oder if-else, 

-> durchlaufen oft eine vordefinierte Anzahl 

-> for in-Schleife / for of-Schleife => zusätzlicher Kompfort

-> continue + break-Anweisungen

## Kopfgesteuerte Schleifen mit while

-> bevor die Anweisungen ausgeführt werden, werden die Schleifenbedingungen im "Kopf" der Schleife ausgewertet -> Ergebins = true oder true-artig -> Ausführung des Schleifenrumpfes -> Wiederholung der Schleife

### wann wird sie eingesetzt?

-> wenn man im Vorraus nicht weiß, wieviele Wiederholungen nötig sind
-> wenn es beabsichtigt wird dass der Schleifenrumpf evtl. gar nicht durchlaufen wird

-> **Syntax**

    while ( Bedingung )
      {
        Anweisungen
      }

-> Beginn mit Schlüsselwort **while (= solange)** -> dahinter dann in **()** die **Schleifenbedingung**

-> für Schleifenbedingungen werden z.B. Vergleichoperatoren oder logische Operatoren benötigt

-> danach folgt der **Schleifenrumpf**, der in **{}** eingefasst ist und die **Anweisungen bzw. Anweisungsblöcke enthält**

-> bei nur einer Anweisung kann man die {} auch weglassen, ist allerdings nicht ratsam (schmählert sonst die Lesbarkeit)

-> **Achtung!** -> Die Endlichkeit einer Schleife MUSS in den Schleifenbedingungen verankert werden. Sonst kann das zum Programmabsturz führen.

## fußgesteuerte Schleifen mit do-while

-> verhält sich ähnlich wie die While-Schleife, wertet die Schleifenbedingungen aber erst nach Ausführung des Schleifenrumpfes aus

-> gut, wenn der Schleifenrumpf einmal komplett durchlaufen wird, damit dann entschieden werden kann, ob der Rumpf wiederholt werden muss oder nicht

-> **Syntax** 

    do
      {
        Anweisungen
      }
      while ( Bedingung );

-> beginnt mit do (= tue etwas), gefolgt von einer einzelnen Anweisung oder einem Anweisungslblock in gescheiften Klammern {}

-> dann folgt das Schlüsselwort while und in runden Klammern () die Schleifenbedingung

## Schleifen mit for

-> wenn eine bestimmte Anzahl an Durchläufen benötigt wird

-> **Schleifenkopf** = Zusammenfassung aus Vorbereitung der Schleife, Schleifenbedingung und Berechnung der Fortsetzung der Schleife

-> **Syntax**: 

    for ( Initialisierung; Schleifenbedingung; Fortsetzung)
      {
        Anweisungen
      }

-> Die **3 Bestandteile** des **Schleifenkopfes** innerhalb der runden Klammer *()* wird durch **Semikolon ;** voneinander getrennt

-> **Initialisierung** = geschieht nur 1 mal, einen Zähler, eine Variable auf den Anfangswert setzen, z.b. am häufigsten die Zählervariable

-> **Schleifenbedingung** -> Auswertung vor dem Schleifendurchlauf -> muss true sein, damit es zur Ausführung des Schleifenrumpfes kommt. auch Prüfung, ob der Endwert des Zählers / der Variable schon erreicht ist

-> **Fortsetzung** -> Auswertung nach jedem Schleifendurchlauf -> der Zähler kann sich hier dann um 1 erhöhen

-> ähnelt sehr stark der while-Schleife

-> **Ersatzschreibweise**

    Initialisierung;
      while (Schleifenbedingung)
      {
        Anweisungen;
        Fortsetzung;
      }

### Unterschied zwischen For- und While-Schleife

-> Die Deklaration der Zählervariable mit dem Variablentypen (const, let, var) findet bei einer for-Schleife innerhalb der for-Klammern statt -> die Gültigkeit dieser Deklaration ist auf den Schleifenrumpf beschränkt  -> außerhalb dieser Schleife kann nicht mehr auf diese Zählervariable zugegriffen werden

->while kann diesen Effekt nicht. 

-> Soll die Zählervariable außerhalb der Schleife auch gelten, so muss die Deklaration  vorgezogen werden, dann ist die Variable auch außerhalb gültig

## weitere For-Schleifen

-> **Enumerationsschleifen mit for in**

-> keine Konstruktion allgemeiner Schleifen, sondern eine **Auflistung aller Eigenschaften eines Objekts** -> zu **enumerieren**

-> **Syntax**:

    for( Variable in Objekt )
      {
        Anweisungen
      }

-> und **Iterationsschleifen mit for of**

-> durchläuft alle Elemente eines iterierbaren Objektes (Objekte, die einen Iterator bereitstellen -> Arrays, Strings, NodeList (Objekt des DOM))

-> **Syntax**:

    for( Variable of iterierbares Objekt )
    {
        Anweisungen
    }

## break und continue (Kontrolle innerhalb von Schleifen)

-> **break**:

-> Schleife wird sofort abgebrochen

    let i = 0;
    while (i < 6) {
      if (i == 3) {
        break;
      }
      i++;
      console.log("i = " + i);
    }

-> bedingt vor dem break allerdings eine if-abfrage (also auch im Schleifenkörper drin), davon abhängig dann das Wort break als Anweisung notiert

    let i = 0;
    Ende: while (i < 6) {
      if (i == 3) {
        alert("Das war's, denn i ist gleich " + i);
        break Ende;
      }
      i++;
    }

-> besondere Form von break

-> vor der Schleife (hier while) steht ein Lable (selbst vergebener Name mit Doppelpunkt dahinter

-> hinter dem break kann dann der Name des Labels anggeben werden)

-> besser Zuordenbarkeit der break-Anweisung auf die richtige Schleife

-> **continue**:

-> der nächste Schleifendurchlauf wird sofort erzwungen

-> nachfolgende Anweisungen innerhalb der Schleife werden bie diesen Schleifendurchlauf nicht mehr ausgeführt

    let i = 0, 
        j = 0;
    while (i < 6) {
      i++;
      if (i == 3) {
        continue;
      }
      j++;
    }

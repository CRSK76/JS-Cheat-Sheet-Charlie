# Switch

-> ist die elegentere Lösung für eine If-Kette

-> In JavaScript kann eine switch Anweisung verwendet werden, wenn eine Variable auf eine bestimmte Anzahl von Werten geprüft werden soll. Eine switch Anweisung kann sehr nützlich sein, wenn es viele mögliche Werte gibt, die geprüft werden müssen, da es die Lesbarkeit des Codes verbessern kann.

    let dayOfWeek = 3;

    switch (dayOfWeek) {
       case 1:
            console.log("Montag");
           break;
        case 2:
            console.log("Dienstag");
            break;
        case 3:
            console.log("Mittwoch");
            break;
        case 4:
            console.log("Donnerstag");
            break;
        case 5:
            console.log("Freitag");
            break;
        default:
            console.log("Wochenende");
            break;
    }

-> Hier wird die Variable dayOfWeek auf ihren Wert überprüft, und je nachdem, welcher Wert vorliegt, wird eine bestimmte Aktion ausgeführt. **Der Wert muss === (absolut stricktly) vorliegen (und nicht nur ==)**

-> Die Anweisungen für einen Fall werden durch die Anweisung break **(break = abbrechen)** abgeschlossen. Wenn Sie diese Anweisung nicht notieren, läuft die Programmausführung einfach in den nächsten case hinein oder fällt sozusagen durch (fall through) 

-> Das kann man nutzen, wenn für verschiedene Werte, die selbe Aktion / der selbe code ausgeführt werden soll.

var Eingabe = window.prompt('Geben Sie eine Zahl von 1 bis 6 ein:', ''),
    Text = 'Ihre Eingabe ist ';

    switch (Eingabe) {
        case "1":
            Text += 'weder eine Prim- noch eine zusammengesetzte Zahl.';
	    break;
        case "2":
        case "3":
        case "5":
	    Text += 'eine Primzahl.';
	    break;
        case "4":
        case "6":
	    Text += 'eine zusammengesetzte Zahl.';
	    break;
        default:
	    Text += 'ungültig.';
	    break;
    }

-> Für den Fall, dass keiner der definierten Fälle zutrifft, kann man am Ende der Fallunterscheidung den Fall **default:** notieren **(ohne einen Wert)**. Die darunter stehenden Anweisungen werden ausgeführt, wenn keiner der anderen Fälle zutrifft

## mit Wertebereichen 

-> hinter switch kann auch eine Konstante notiert werden und hinter switch anstelle einer Konstanten auch ein Ausdruck geschreiben werden. Das dient dazu, die switch-Anweisung sozusagen auf den Kopf zu stellen. Statt einen berechneten Wert mit einer Liste von Konstanten zu vergleichen, können Sie auch eine Konstante mit einer Liste von berechneten Werten vergleichen.

-> Im einfachsten Fall schreiben Sie in die switch-Anweisund den Prüfwert true und verwenden in den case-Klauseln Ausdrücke, die einen Wahrheitswert liefern. JavaScript geht die case-Klauseln von oben nach unten durch und wertet die Ausdrücke soweit aus, bis es eine Übereinstimmung mit dem Prüfwert findet. Die weiteren case-Klauseln bleiben unbeachtet.

-> switch statt if-Kette
    var Eingabe = window.prompt('Geben Sie eine Zahl zwischen 50 und 100 ein:', ''),
        EingabeWert = parseInt(Eingabe),
        Text;

    switch (true) {
        case EingabeWert < 50:
             Text = 'Die Zahl ' + Eingabe + ' ist sicher zu klein.';
             break;
        case EingabeWert > 100:
             Text = 'Die Zahl ' + Eingabe + ' ist eindeutig zu groß.';
             break;
        default:
             Text = 'Na bitte, Sie haben die Aufgabe verstanden!';
            break;
    }

-> Sie können die Ausdrücke hinter case für bessere Lesbarkeit in Klammern setzen - syntaktisch notwendig ist das nicht. Und Sie sind nicht auf einen switch (true) beschränkt, da kann jeder Wert stehen. Interessant könnte ein switch (false) sein, wenn Sie eine Liste von Prüfungen durchlaufen möchten und einen Fehler erzeugen wollen, sobald eine dieser Prüfungen nicht erfüllt ist. Oder ein switch (5), wenn Sie mehrere Variablen mit Werten haben und eine finden wollen, deren Wert 5 ist. Es hängt ganz von Ihrer Problemstellung ab.

-> Eine if-else Anweisung wird verwendet, **wenn eine Bedingung erfüllt sein muss, _bevor_ eine Aktion ausgeführt wird**. Hier ist ein Beispiel für die Verwendung einer if-else Anweisung:

    let age = 18;

    if (age < 18) {
       console.log("Du bist minderjährig");
    } else {
        console.log("Du bist volljährig");
    }

-> In diesem Beispiel wird die Variable age auf ihren Wert überprüft, und wenn sie kleiner als 18 ist, wird eine Aktion ausgeführt, andernfalls wird eine andere Aktion ausgeführt.

-> In der Regel können sowohl switch als auch if-else Anweisungen in JavaScript verwendet werden, um Bedingungen abzudecken.Die Wahl hängt von der spezifischen Situation ab und von der Lesbarkeit und Effizienz des Codes.

-> <a href="ifelse.md">Alles über if-Bedingungen:</a>

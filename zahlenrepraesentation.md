# Zahlenrepräsentation

Es gibt unterschiedliche Repräsentationen *wow*

Im Dezimalsystem 123,456 bedeutet eigentlich

`1 * 10^2 + 2 * 10^1 + 3 * 10^0 + 4 * 10^-1 + 5 * 10^-2 + 6 * 10^-3`

## Umrechnung ins Dezimalsystem

1. Zahl wie oben zerlegen
2. Ausrechnen

*Beispiel*: 45,4 im Oktalsystem

1. `4 * 8^1 + 5 * 8^0 + 4 * 8^-1`
2. = `4 * 8 + 5 + 4 * 1/8` = `37,5`

## Umrechnung aus Dezimalsystem in ein anderes System
1. `b = Basis des anderen Zahlensystems`
2. `n1` ist die Zahl vor dem Komma
3. `n2` ist 0,die Zahl nach dem Komma
4. Vor dem Komma
   1. Teile `n1` durch `b`
   2. Nimm den Rest dieser Division als Stelle (ganz rechts) der neuen Zahl
   3. Wiederhole mit dem Ergebnis der Division, bis das Ergebnis der Division 0 ist
5. Hinter dem Komma
   1. Multipliziere `n2` mit `b`
   2. Notiere die Zahl **vor** dem Komma und setze sie auf 0
   3. Wiederhole, bis es keine Nachkommastelle mehr gibt


*Beispiel*: 4,625 von Dezimaldarstellung zu Binärdarstellung

`b = 2`

`n1 = 4`

`4 / 2` = `2` Rest `0`

`2 / 2` = `1` Rest `0`

`1 / 2` = `0` Rest `1` <- Ergebnis der Division ist 0, also aufhören

Reste von unten nach oben: `100`

`n2 = 0.625`

`n2 * 2 = 1.25` 1 vor dem Komma behalten

`0.25 * 2 = 0.5` 0 vor dem Komma behalten

`0.5 * 2 = 1.0` 1 vor dem Komma behalten

Vor-Komma-Zahlen von oben nach unten: `101`

Ergebnis: `4,625` im Dezimalsystem entspricht `100,101` im Binärsystem

___
[Vorheriges: Modulo](modulo.md) | [Nächstes: Diskrete Exponentialfunktion](diskrete-exponentialfunktion.md)
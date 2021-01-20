# Modulo

## Division mit Rest

Satz: Für jedes `a ∈ Z` und `m ∈ N` gibt es eindeutige Zahlen `q ∈ Z` und `r ∈ N0` mit `0 ≤ r < m`, so dass

`a = m * q + r`

`a` = Divident (Das Zu-teilende), `m` = Divisor (Durch was geteilt wird)

`q` = Quotient (Ergebnis der Teilung), `r` = Rest

Mit anderen Worten: Bei einer Teilung gibt es immer genau ein Ergebnis, welches aus Quotient und Rest besteht.

Für feste `m` werden die Funktionen `div` und `mod` so definiert:

`r = a mod m`

`q = a div m`

## Kongruenz

Wenn 2 ganze Zahlen `a` und `b`, die durch `m` geteilt werden, den gleichen Rest haben, dann sind sie zueinander __kongruent__ für diesen Divisor.

Schreibweise: 

Kongruenz: `a ≡ b (mod m)`

Nicht-Kongruenz: `a /≡ b (mod m)` (das Kongruenzsymbol durchstreichen)

Diese Schreibweise beschreibt ein Verhältnis, im Gegensatz zur Funktion `r = a mod m`

*Beispiele:*

`22 ≡ 17 (mod 5)`, da `22 mod 5 = 2` und `17 mod 5 = 2`

`22 /≡ 17 (mod 54)`, da `22 mod 4 = 2` und `17 mod 4 = 1`

___
[Vorheriges: Ganzzahlige Division](ganzzahlige-division.md) | [Nächstes: NOCH UNKLAR](unklar.md)
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

*Beispiele:*
`17 mod 5: 3 * 5 + 2 also 2`

`-17 mod 5: -4 * 5 + 3 also 3`

`3 mod 5: 0 * 5 + 3 also 3`

`-3 mod 5: -1 * 5 + 2 also 2`

[Guter Onlinerechner für ganzzahlige Division und Rest](https://www.symbolab.com/solver/modulo-calculator)

## Kongruenz

Wenn 2 ganze Zahlen `a` und `b`, die durch `m` geteilt werden, den gleichen Rest haben, dann sind sie zueinander __kongruent__ für diesen Divisor.

Schreibweise: 

Kongruenz: `a ≡ b (mod m)`

Nicht-Kongruenz: `a /≡ b (mod m)` (das Kongruenzsymbol durchstreichen)

Diese Schreibweise beschreibt ein Verhältnis, im Gegensatz zur Funktion `r = a mod m`

*Beispiele:*

`22 ≡ 17 (mod 5)`, da `22 mod 5 = 2` und `17 mod 5 = 2`

`22 /≡ 17 (mod 54)`, da `22 mod 4 = 2` und `17 mod 4 = 1`

2 ganze Zahlen `a` und `b` und die natürliche Zahl `m` sind nur kongruent, wenn es eine ganze Zahl `k` gibt, so dass
1. `a`-`b` = `k * m`
2. `a` = `b + k * m`

*Beispiele:*

`a = 17`

`b = 5`

`m = 6`

`17 - 5 = k * 6`

= `12 = k * 6` wahr für `k = 2` => kongruent

`a = 24`

`b = 14`

`m = 6`

`24 = 14 + k * 6`

= `10 = k * 6` falsch => nicht kongruent

## Restklassen

Wenn zwei ganze Zahlen `a` und `b` für ein `m` kongruent sind, dann herrscht eine Äquivalenzbeziehung zwischen ihnen, d.h. sie sind
- symmetrisch (man kann sie vertauschen)
- reflexiv (d.h. wenn `a` und `b` die gleiche Zahl ist, ist es immer kongruent)
- transitiv (d.h. wenn `a` und `b` zueinander kongruent sind und `b` und `c` zueinander kongruent sind, dann sind auch `a` und `c` zueinander kongruent).

Durch die Äquivalenz entstehen die Restklassen `Rm`, z.B. für `m = 5`

`[0]5 = {..., -10, -5, 0, 5, 10, ...}`

`[1]5 = {..., -9, -4, 1, 6, 11, ...}`

`[2]5 = {..., -8, -3, 2, 7, 12, ...}`

`[3]5 = {..., -7, -2, 3, 8, 13, ...}`

`[4]5 = {..., -6, -1, 4, 9, 14, ...}`

=> alle ganzen Zahlen `a`, die `a mod m = 0` ergeben.  

Die Menge `Zm` = `{0, 1, 2, ..., m - 1}`
- Repräsentiert die entsprechenden Restklassen, da die Restklassen danach wieder von vorne anfangen, z.B. `[0]5 = [5]5`
- Bildet die Menge der möglichen Restwerte

*Lifehack*: Wenn man Modulorechnung beschleunigen will, kann man sich kleinere Repräsentanten der gleichen Äquivalenzklasse suchen.

## Algebraische Strukturen mit Rest

`(a + b) mod m` = `a (+m) b`

`(a * b) mod m` = `a (*m) b`

bzw.

![](/bilder/modulo-algebra.png)

| `(+3)` |   0   |   1   |          2           |
| :----: | :---: | :---: | :------------------: |
|   0    |   0   |   1   |          3           |
|   1    |   1   |   2   |          0           |
|   2    |   2   |   0   | 1 (da `2 + 2 mod 3`) |

Fun Fact: 0 ist das neutrale Element

Inverses Elemtent: Was uns wieder zur 0 zurückbringt bzw. zu jedem `x` gibt es ein `-x`. Schreibweise auch: `x^-1`

Wenn `d` das additive Inverse von `e` ist, dann gilt:

`e (+m) d = 0`

= `d = m - e` (falls `e != 0`, sonst `d = 0`)

z.B. `2 = 3 - 1`

In diesem Beispiel: 1 und 2

| `(*3)` |   0   |   1   |          2           |
| :----: | :---: | :---: | :------------------: |
|   0    |   0   |   0   |          0           |
|   1    |   0   |   1   |          2           |
|   2    |   0   |   2   | 1 (da `2 * 2 mod 3`) |

Fun Fact: 1 ist das neutrale Element

Inverses Element: Was uns wieder zur 1 zurückbringt z.B. 2 und 2

Existiert immer, wenn `e` und `m` teilerfremd sind (also es keine natürliche Zahl außer 1 gibt, die beide Zahlen teilt, ist bei Primzahlen immer der Fall). 

`(Zm, (+m), (*m))` ist ein Restklassenring aber kein Restklassenkörper, da die inversen Elemente der Multiplikation fehlen. Anderer Zahlenring sind die ganzen Zahlen.

Ein Restklassenring befolgt teilweise die gewohnten Rechenregeln, aber nicht alle. Befolgt:
- Assoziativgesetz für + und * (z.B. `(a * b) * c` = `a * (b * c)`)
- Distributivgesetz (`a * b + a * c` = `a * (b + c)`)
- Neutrales Element existiert
- Additives Inverses existiert, aber kein Multiplikatives Inverses für jede Zahl.

Befolgt nicht manche Eindeutigkeitssätze.

Ist `m` eine Primzahl, dann ist es darüber hinaus ein Restklassenkörper.

Ein Restklassenkörper ist eine Menge, in der alle Rechengesetze wie gewohnt gelten. Andere Beispiele sind Reele Zahle, Komplexe Zahlen etc.

`5 (+7) 3` = `(5 + 3) mod 7` = `1`

`3 (*7) 5` = `(3 * 5) mod 7` = `1`

## Verschiebealgorithmus

Um Multiplikatives Inverses zu finden.

Was ist das Inverse von `4` in `Z9`?

`1/4` ist keine ganze Zahl, also Zähler `+ 9`

`10/4` = `2,5` ist keine ganze Zahl, also Zähler `+ 9`

`19/4` = `4,75` ist keine ganze Zahl, also Zähler `+ 9`

`28/4` = `7` ist **eine** ganze Zahl, also `4^-1 in Z9` = `7`

Test: `7 (*9) 4` = `28 mod 9` = `1` ⬅️ neutrales Element ✅

Fun Facts:

`0` hat nie ein multiplikatives Inverses.

`1` ist immer sein eigenes multiplikatives Inverses (d.h. für jedes `m` gibt es ein Inverses für die 1, nämlich 1).

Die multiplikativen Inversen sind **immer eindeutig** wenn sie existieren. Das ist gut, wenn man nach dem Inversen sucht, und Zahlen ausschließen kann, weil sie bereits multiplikative Inverse anderer Zahlen in Z sind.

## Rechnen mit kongruenten Zahlen
Wenn `a ≡ b mod m` und `c ≡ d mod m`, dann

`a + c ≡ b + d mod m` bzw. `(a + b) mod m` = `((a mod m) + (b mod m)) mod m`

`a * c ≡ b * d mod m` bzw. `(a * b) mod m` = `((a mod m) * (b mod m)) mod m`

Man kann also bei Addition und Multiplikation auch erst die Bestandteile Modulorechnen und dann die Ergebnisse miteinander addieren/multiplizieren und dann nochmal Modulorechnen.

*Beispiel*:

`7 ≡ 2 mod 5` und `11 ≡ 1 mod 5`

=> `2 + 1 mod 5` = `3 mod 5` = `3`

oder für Multiplikation

=> `2 * 1 mod 5` = `2 mod 5` = `2`

Die Formel stimmt allerdings **nicht**, wenn `a`, `b`, `c` oder `d` ≡ 0 sind. Dann würde man durch 0 teilen, was nicht erlaubt ist.
___
[Vorheriges: Ganzzahlige Division](ganzzahlige-division.md) | [Nächstes: Zahlenrepräsentation](zahlenrepraesentation.md)